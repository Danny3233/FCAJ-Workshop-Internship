---
title: "Deploying with AWS CloudFormation"
date: 2026-05-19T15:33:55+07:00
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

### Launch Stack from AWS CloudFormation

1. Choose the following **Launch Stack** button:

<a href="https://console.aws.amazon.com/cloudformation/home#/stacks/quickcreate?templateURL=https%3A%2F%2Fpomatas-public-blogs.s3.us-east-1.amazonaws.com%2Fdynatrace-api-gateway%2Fbedrock-llm-gateway.yaml&stackName=bedrock-llm-gateway&param_EnableAuthorizer=false&param_EndpointType=PRIVATE"
   target="_blank"
   rel="noopener noreferrer">
  <img src="/images/launch-stack-button.png"
       alt="Launch Stack"
       style="margin:0; display:inline-block; float:left;">
</a>

<div style="clear: both;"></div>

2. In the Quick create stack page, configure the key parameters as follows. For complete parameter descriptions, see the [documentation](https://github.com/aws-samples/sample-ai-gateway-for-amazon-bedrock?tab=readme-ov-file#cloudformation-parameters).

| Parameter | Description | Choose value | Why |
|---|---|---|---|
| **EndpointType** | API Gateway endpoint accessibility (PRIVATE or REGIONAL) | **PRIVATE** | Secure internal access only |
| **EnableAuthorizer** | Enable Lambda Authorizer for API Gateway | **false** | Start without auth for simpler testing |
| **CustomDomain** | Custom domain name for API Gateway | *(leave empty)* | Use default domain initially |
| **HostedZoneId** | Route 53 Hosted Zone ID for custom domain SSL validation | *(leave empty)* | Not needed with default domain |

- Select the capability **I acknowledge that AWS CloudFormation might create IAM resources**.
- Leave all other configurations at their default values and choose **Create Stack**.
- In the stack page, wait until the **Status** of the stack transitions to **CREATE_COMPLETE**.
- Choose **Outputs** and copy the values for **GatewayUrl**, **VpcId**, and **ApiId** – you’ll use these to test your gateway later.

3. In the **Quick create stack** interface.

    - Select **I acknowledge that AWS CloudFormation might create IAM resources.**
    - Click **Create Stack**

![Launch Stack](/images/5-Launchstack/0001.png)

![Launch Stack](/images/5-Launchstack/0002.png)

![Launch Stack](/images/5-Launchstack/0003.png)

4. Review **CREATE_IN_PROGRESS** and click refresh icon to check **CREATE_COMPLETE**

![Launch Stack](/images/5-Launchstack/0004.png)

5. Review **CREATE_COMPLETE** and select **Outputs**.

![Launch Stack](/images/5-Launchstack/0005.png)

6. Review **Outputs**.

![Launch Stack](/images/5-Launchstack/0006.png)