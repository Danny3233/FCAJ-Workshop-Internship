---
title: "Cấp quyền cho Amazon Bedrock"
date: 2026-05-16T11:44:49+07:00
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Đính kèm Permissions

1. Truy cập [Bảng điều khiển IAM](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-1#/home).

    - Chọn **IAM users**

    - Nhấp vào **bedrock-ai-chatbot-user**

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0001.png)

2. Chọn **Add permission** trong menu thả xuống.

    - Chọn **Add permission**

    - Chọn **Attach policies directly**

    - **Permissions policies**: nhập ``AmazonDynamoDBFullAccess``

    - Nhấp vào **Next**

    - Nhấp vào **Add permissions**

    - Xem lại **Policy name**

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0002.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0003.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0004.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0005.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0006.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0007.png)

3. Sau khi thêm permissions.

    - **Permissions policies**: nhập ``AmazonAPIGatewayAdministrator``

    - **Permissions policies**: nhập ``AmazonOpenSearchServiceFullAccess``

    - **Permissions policies**: nhập ``AmazonS3FullAccess``

    - **Permissions policies**: nhập ``AWSCloudFormationFullAccess``

    - **Permissions policies**: nhập ``AWSLambda_FullAccess``

    - **Permissions policies**: nhập ``IAMFullAccess``

    - Nhấp vào **Next** và **Add permissions**

    - Xem lại **Policy name**

![Đính kèm quyền](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0008.png)

4. Chọn **Create inline policy** trong menu thả xuống.

    - Chọn **JSON**

    - **Policy editor**: Sao chép JSON này

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

    - Dán vào **Policy editor** và Nhấp vào **Next**

    - **Policy name**: nhập ``OpenSS-Policy``

    - Nhấp vào **Create policy**

    - Xem lại **Policy name**

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/0009.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00010.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00011.png)

![Attach permissions](/images/3-Amazonbedrock/3.2-attach-permissions-for-bedrock/00012.png)