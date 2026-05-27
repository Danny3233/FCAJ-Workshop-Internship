---
title: "Attach Permissions for Amazon Bedrock"
date: 2026-05-16T11:44:24+07:00
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Attch Permissions

1. Navigate to the [IAM Console](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-1#/home).

    - Select **IAM users**
    - Click **bedrock-ai-chatbot-user**

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0001.png)

2. Select **Add permission** in the dropdown.

    - Select **Add permissions**
    - Select **Attach policies directly**
    - **Permissions policies**: enter ``AmazonDynamoDBFullAccess``
    - Click **Next**
    - Click **Add permissions**
    - Review **Policy name**


![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0002.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0003.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0004.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0005.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0006.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0007.png)

3. After adding permissions.

    - **Permissions policies**: enter ``AmazonAPIGatewayAdministrator``
    - **Permissions policies**: enter ``AmazonOpenSearchServiceFullAccess``
    - **Permissions policies**: enter ``AmazonS3FullAccess``
    - **Permissions policies**: enter ``AWSCloudFormationFullAccess``
    - **Permissions policies**: enter ``AWSLambda_FullAccess``
    - **Permissions policies**: enter ``IAMFullAccess``
    - Click **Next** and **Add permissions**
    - Review **Policy name**

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0008.png)

4. Select **Create inline policy** in the dropdown.

    - Select **JSON**
    - **Policy editor**: Copy this json
    ```Json
    {
	    "Version": "2012-10-17",
	    "Statement": [
		    {
			    "Effect": "Allow",
			    "Action": [
				"aoss:*"
			    ],
			    "Resource": "*"
		    }
	    ]
    }

    ```
    - Paste into **Policy editor** and Click **Next**
    - **Policy name**: enter ``OpenSS-Policy``
    - Click **Create policy**
    - Review **Policy name**

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0009.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00010.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00011.png)

![Attach permissions](/static/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00012.png)