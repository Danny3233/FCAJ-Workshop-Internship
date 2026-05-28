---
title: "Kiểm thử sau triển khai"
date: 2026-05-21T16:11:47+07:00
weight: 2
chapter: false
pre: " <b> 7.2 </b> "
---

### Kiểm thử sau triển khai 

1. Thực thi lệnh trong CloudShell.

2. Sao chép và dán đoạn code **boto3** sau:

```py
cat > boto3_client_factory.py << 'EOF'
import boto3
from botocore import UNSIGNED
from botocore.client import BaseClient
from botocore.config import Config

class Boto3ClientFactory:
    """Lớp tiện ích dùng để tạo boto3 clients."""
    
    @classmethod
    def create(cls, service_name: str, endpoint_url: str, jwt_token: str = None) -> BaseClient:
        """Tạo boto3 client dùng với sign-and-forward Lambda.
        
        Parameters
        ----------
        service_name : str
            Tên dịch vụ dùng khi khởi tạo boto3.client.
        endpoint_url: str
            URL trỏ đến API Gateway invoke endpoint.
        jwt_token: str, optional
            JWT token được thêm vào Authorization header cho tất cả request.
        """
        generic_client = boto3.client(
            service_name = service_name,
            endpoint_url = endpoint_url,
            # Không ký request ở phía client; xác thực được xử lý trong API Gateway
            config = Config(signature_version = UNSIGNED),
            # Region_name cần truyền vào do logic validation
            region_name="",
        )
        
        def add_client_headers(model, params, **kwargs):
            """Hook dùng để thêm custom headers cho mỗi request."""
            headers = params["headers"]
            
            # Header này được Lambda integration sử dụng
            headers["aws-endpoint-prefix"] = model.service_model.endpoint_prefix
            
            # Thêm Authorization header nếu có jwt_token
            if jwt_token:
                headers["Authorization"] = f"Bearer {jwt_token}"
        
        generic_client.meta.events.register("before-call.*.*", add_client_headers)
        
        return generic_client
EOF
````

* Bạn có thể tạo client cho các dịch vụ Amazon Bedrock khác nhau. Thiết lập các biến cấu hình:

```py
# Thay bằng Gateway URL thực tế từ CloudFormation Outputs
export GATEWAY_URL="https://your-api-id.execute-api.region.amazonaws.com/v1"

# Thay bằng Knowledge Base ID của Amazon Bedrock (tùy chọn)
export KB_ID="your-kb-id"
```

3. Mở giao diện <a href="https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks?filteringText=&filteringStatus=active&viewNested=true" target="_blank">CloudFormation</a> để sao chép **GatewayUrl**.

* Tìm **bedrock-llm-gateway**
* Chọn **bedrock-llm-gateway**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0001.png)

* Chọn **Outputs**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0002.png)

* Sao chép **GatewayUrl** và dán vào **export GATEWAY_URL**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0003.png)

4. Mở giao diện <a href="https://ap-southeast-1.console.aws.amazon.com/bedrock/home?region=ap-southeast-1#/knowledge-bases" target="_blank">Amazon Bedrock</a> để sao chép **Knowledge Base ID**.

* Tìm **Bedrock-Knowledge-base**
* Chọn **Bedrock-Knowledge-base**
* Sao chép **Knowledge Base ID** và dán vào **export KB_ID**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0004.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0005.png)

5. Quay lại giao diện <a href="https://ap-southeast-1.console.aws.amazon.com/cloudshell/home?region=ap-southeast-1#" target="_blank">CloudShell</a>.

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0006.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0007.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0008.png)

7. Sao chép và dán đoạn code **Converse stream API** sau:

```py
cat > test_converse_stream.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory
import json

# Lấy cấu hình từ environment variables
api_gateway_url = os.environ['GATEWAY_URL']

# Tạo client cho Bedrock Runtime
bedrock_runtime_client = Boto3ClientFactory.create(
    service_name = "bedrock-runtime",
    endpoint_url = api_gateway_url
)

response = bedrock_runtime_client.converse_stream(
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

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0009.png)

* Sao chép và dán lệnh:

```bash
python test_converse_stream.py
```

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/00010.png)

8. Sao chép và dán đoạn code **Knowledge Bases** sau:

```py
cat > test_knowledge_base.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory

# Lấy cấu hình từ environment variables
api_gateway_url = os.environ['GATEWAY_URL']
knowledge_base_id = os.environ['KB_ID']

# Tạo client cho Bedrock Agent Runtime
bedrock_kb_client = Boto3ClientFactory.create(
    service_name = "bedrock-agent-runtime",
    endpoint_url = api_gateway_url
)

response = bedrock_kb_client.retrieve(
    knowledgeBaseId = knowledge_base_id,
    retrievalQuery = {'text': 'Who invented the airplane?'},
    retrievalConfiguration = {
        'vectorSearchConfiguration': {
            'numberOfResults': 5
        }
    }
)

print("Knowledge base retrieval results:")
print(response)
EOF
```

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/00011.png)

* Sao chép và dán lệnh:

```bash
python test_knowledge_base.py
```

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/00012.png)