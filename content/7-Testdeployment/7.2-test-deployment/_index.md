---
title: "Test Deployment"
date: 2026-05-21T16:11:16+07:00
weight: 2
chapter: false
pre: " <b> 7.2 </b> "
---

### Test Deployment

1. Execute this command in CloudShell.

2. Copy and Paste **boto3** the following code:

```py
cat > boto3_client_factory.py << 'EOF'
import boto3
from botocore import UNSIGNED
from botocore.client import BaseClient
from botocore.config import Config

class Boto3ClientFactory:
    """Utility class for creating boto3 clients."""
    
    @classmethod
    def create(cls, service_name: str, endpoint_url: str, jwt_token: str = None) -> BaseClient:
        """Create a boto3 client instance usable with the sign-and-forward Lambda.
        
        Parameters
        ----------
        service_name : str
            The service name to be used when initiating boto3.client.
        endpoint_url: str
            URL pointing to API gateway invoke endpoint.
        jwt_token: str, optional
            JWT token to include in Authorization header for all requests.
            If provided, adds 'Authorization: Bearer {jwt_token}' header.
        """
        generic_client = boto3.client(
            service_name = service_name,
            endpoint_url = endpoint_url,
            # do not sign the request at the client side; authentication is done
            # in API gateway
            config = Config(signature_version = UNSIGNED),
            # non-None Region_name needs to be passed due to validation logic
            # it is NOT used if we pass endpoint_url above
            region_name="",
        )
        
        def add_client_headers(model, params, **kwargs):
            """Hook to add custom headers each request."""
            headers = params["headers"]
            
            # the header "aws-endpoint-prefix" is used by the Lambda integration
            headers["aws-endpoint-prefix"] = model.service_model.endpoint_prefix
            
            # Add Authorization header if jwt_token is provided
            if jwt_token:
                headers["Authorization"] = f"Bearer {jwt_token}"
        
        # register the hook to add custom headers before each call
        generic_client.meta.events.register("before-call.*.*", add_client_headers)
        
        return generic_client
EOF
```
-  You can now create clients for different Amazon Bedrock services. Set your configuration variables:

```py
# Replace with your actual Gateway URL from CloudFormation Outputs (used in all examples)
export GATEWAY_URL="https://your-api-id.execute-api.region.amazonaws.com/v1"
# Replace with one of your pre-existing Amazon Bedrock Knowledge Bases ID (optional, only needed for knowledge base example)
export KB_ID="your-kb-id"
```

3. Open the <a href="https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks?filteringText=&filteringStatus=active&viewNested=true" target="_blank">CloudFormation</a> console to copy the **GatewayUrl**.

    - Find **bedrock-llm-gateway**
    - Select **bedrock-llm-gateway**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0001.png)

- Select **Outputs**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0002.png)

- Copy and Paste **GatewayUrl** into **export GATEWAY_URL**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0003.png)

4. Open the <a href="https://ap-southeast-1.console.aws.amazon.com/bedrock/home?region=ap-southeast-1#/knowledge-bases" target="_blank">Amazon Bedrock</a> console to copy the **Knowledge Base ID**.

    - Find **Bedrock-Knowledge-base**
    - Select **Bedrock-Knowledge-base**
    - Copy and Paste **Knowledge Base ID** into **export KB_ID**

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0004.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0005.png)

5. Go back to open the <a href="https://ap-southeast-1.console.aws.amazon.com/cloudshell/home?region=ap-southeast-1#" target="_blank">CloudShell</a> console.

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0006.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0007.png)

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0008.png)

7. Copy and Paste **Converse stream API** the following code:

```py
cat > test_converse_stream.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory
import json

# Get configuration from environment variables
api_gateway_url = os.environ['GATEWAY_URL']

# Create client for Bedrock Runtime (model inference)
bedrock_runtime_client = Boto3ClientFactory.create(
    service_name = "bedrock-runtime",
    endpoint_url = api_gateway_url
)

response = bedrock_runtime_client.converse_stream(
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
![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/0009.png)

- Copy and Paste **python test_converse_stream.py** into CloudShell

```
python test_converse_stream.py
```
![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/00010.png)

8. Copy and Paste **Knowledge Bases** the following code:

```py
cat > test_knowledge_base.py << 'EOF'
import os
from boto3_client_factory import Boto3ClientFactory

# Get configuration from environment variables
api_gateway_url = os.environ['GATEWAY_URL']
knowledge_base_id = os.environ['KB_ID']

# Create client for Bedrock Agent Runtime (knowledge bases)
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

- Copy and Paste **python test_knowledge_base.py** into CloudShell

```
python test_knowledge_base.py
```

![Test Deploymet](/images/7-Testdeployment/7.2-test-deployment/00012.png)