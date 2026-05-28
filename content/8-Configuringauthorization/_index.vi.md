---
title: "Cấu hình Authorization"
date: 2026-05-26T13:24:19+07:00
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

### Cấu hình Authorization (Configuring Authorization)

1. Tải file [.yaml](/bedrock-llm-gateway.yaml).

- Quay lại giao diện <a href="https://console.aws.amazon.com/cloudformation/" target="_blank">CloudFormation</a>
- Tìm và chọn **bedrock-llm-gateway**

![Configuring Authorization](/images/8-Configuringauthorization/0001.png)

- Chọn **Update stack** và nhấn **Make a direct update**

![Configuring Authorization](/images/8-Configuringauthorization/0002.png)

2. Trong giao diện **Update stack**.

- Chọn **Replace existing template**
- Chọn **Upload a template file**
- Nhấn **Choose file**

![Configuring Authorization](/images/8-Configuringauthorization/0003.png)

- Chọn file **bedrock-llm-gateway.yaml** từ máy tính và nhấn **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0004.png)

- Thay đổi **EnableAuthorizer** từ `false` thành `true` và nhấn **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0005.png)

- Chọn **I acknowledge that AWS CloudFormation might create IAM resources** và nhấn **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0006.png)

- Kiểm tra lại **Changes** và nhấn **Submit**

![Configuring Authorization](/images/8-Configuringauthorization/0007.png)

![Configuring Authorization](/images/8-Configuringauthorization/0008.png)

3. Truy cập giao diện <a href="https://console.aws.amazon.com/apigateway/" target="_blank">API Gateway</a>.

- Tìm và chọn **bedrock-llm-gateway**

![Configuring Authorization](/images/8-Configuringauthorization/0009.png)

- Chọn **Deploy API**

![Configuring Authorization](/images/8-Configuringauthorization/00010.png)

- **Stage** chọn **v1**

![Configuring Authorization](/images/8-Configuringauthorization/00011.png)

- Nhấn **Deploy**

![Configuring Authorization](/images/8-Configuringauthorization/00012.png)

![Configuring Authorization](/images/8-Configuringauthorization/00013.png)

4. Mở terminal trên VS Code.

- Sao chép và dán đoạn code **Login Token** để lấy **JWT Token**:

```powershell
$response = Invoke-RestMethod -Uri "http://localhost:5000/api/auth/login" `
-Method POST `
-ContentType "application/json" `
-Body '{"email":"your-example@gmail.com","password":"example-password"}'

$response | ConvertTo-Json -Depth 10
````

![Configuring Authorization](/images/8-Configuringauthorization/00014.png)

* Xem **token** và **accessToken**. Sao chép **accessToken** vào biến **jwt_token**

![Configuring Authorization](/images/8-Configuringauthorization/00015.png)

5. Sao chép và dán đoạn code **Lambda authorizer** sau:

{{% notice warning %}}
Chúng ta sẽ sử dụng code Lambda authorizer trong CloudShell để lấy kết quả xác thực sau khi tạo và kiểm thử deployment. Nếu code Lambda authorizer không được lưu trước khi test deployment, kết quả xác thực sẽ không được trả về.
{{% /notice %}}

```py
cat > test_with_auth.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory

# Lấy cấu hình từ environment variables
api_gateway_url = os.environ['GATEWAY_URL']

# Thay "your-jwt-token" bằng JWT token thực tế
jwt_token = "your-jwt-token"

bedrock_runtime_client_with_jwt = Boto3ClientFactory.create(
    service_name = "bedrock-runtime",
    endpoint_url = api_gateway_url,
    jwt_token = jwt_token
)

response = bedrock_runtime_client_with_jwt.converse_stream(
    modelId = 'global.anthropic.claude-haiku-4-5-20251001-v1:0',
    messages = [{"role": "user", "content": [{"text": "Who invented the airplane?"}]}]
)

print("Model Response:")

# Hiển thị phản hồi theo dạng stream
for event in response['stream']:
    if 'contentBlockDelta' in event:
        delta = event['contentBlockDelta']['delta']
        if 'text' in delta:
            print(delta['text'], end='', flush=True)
    elif 'messageStop' in event:
        print("\n")
        break
EOF
```

![Configuring Authorization](/images/8-Configuringauthorization/00016.png)

* Sao chép và dán lệnh sau vào CloudShell:

```bash
python test_with_auth.py
```

![Configuring Authorization](/images/8-Configuringauthorization/00017.png)