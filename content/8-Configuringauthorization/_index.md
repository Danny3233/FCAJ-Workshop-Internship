---
title: "Configuring Authorization"
date: 2026-05-26T13:23:32+07:00
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

### Configuring Authorization

1. Download the [.yaml](/bedrock-llm-gateway.yaml) file.

- Go back to the <a href="https://console.aws.amazon.com/cloudformation/" target="_blank"> CloudFormation</a> console
- Find anh click **bedrock-llm-gateway**

![Configuring Authorization](/images/8-Configuringauthorization/0001.png)

- Select **Update stack** and click **Make a direct update**

![Configuring Authorization](/images/8-Configuringauthorization/0002.png)

2. In the **Update stack** interface.

- Select **Replace existing template**
- Select **Upload a template file**
- Click **Choose file**

![Configuring Authorization](/images/8-Configuringauthorization/0003.png)

- Select **bedrock-llm-gateway.yaml** from the PC and click **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0004.png)

- Change **EnableAuthorizer** from false to true and click **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0005.png)

- Select **I acknowledge that AWS CloudFormation might create IAM resources** and click **Next**

![Configuring Authorization](/images/8-Configuringauthorization/0006.png)

- Review **Changes** and click **Submit**

![Configuring Authorization](/images/8-Configuringauthorization/0007.png)

![Configuring Authorization](/images/8-Configuringauthorization/0008.png)

3. Navigate to the <a href="https://console.aws.amazon.com/apigateway/" target="_blank"> API Gateway</a> console.

- Find and click **bedrock-llm-gateway**

![Configuring Authorization](/images/8-Configuringauthorization/0009.png)

- Select **Deploy API**

![Configuring Authorization](/images/8-Configuringauthorization/00010.png)

- **Stage** select **v1**

![Configuring Authorization](/images/8-Configuringauthorization/00011.png)

- Click **Deploy**

![Configuring Authorization](/images/8-Configuringauthorization/00012.png)

![Configuring Authorization](/images/8-Configuringauthorization/00013.png)

4. Open the terminao on VS Code.

- Copy and Paste **Login Token** to get **JWT Token**:

```
$response = Invoke-RestMethod -Uri "http://localhost:5000/api/auth/login" `
-Method POST `
-ContentType "application/json" `
-Body '{"email":"your-example@gmail.com","password":"example-password"}'

$response | ConvertTo-Json -Depth 10
```

![Configuring Authorization](/images/8-Configuringauthorization/00014.png)

- See **token** and **accessToken**. Copy **accessToken** into **jwt_token**

![Configuring Authorization](/images/8-Configuringauthorization/00015.png)

5. Copy and Paste **Lambda authorizer** the following code:

{{% notice warning %}}
We will use the Lambda authorizer code in CloudShell to get the authentication result after creating and testing the deployment. If the Lambda authorizer code is not saved before testing the deployment, the authentication result will not be returne
{{% /notice %}}

```py
cat > test_with_auth.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory

# Get configuration from environment variables
api_gateway_url = os.environ['GATEWAY_URL']

# Replace "your-jwt-token" with your actual JWT token
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
# Stream the response as it arrives
for event in response['stream']:
    if 'contentBlockDelta' in event:
        delta = event['contentBlockDelta']['delta']
        if 'text' in delta:
            print(delta['text'], end='', flush=True)  # Print each chunk immediately
    elif 'messageStop' in event:
        print("\n")  # End of stream
        break
EOF
```

![Configuring Authorization](/images/8-Configuringauthorization/00016.png)

- Copy and Paste **python test_with_auth.py** into CloudShell

```
python test_with_auth.py
```

![Configuring Authorization](/images/8-Configuringauthorization/00017.png)