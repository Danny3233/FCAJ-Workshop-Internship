---
title: "Create a new IAM user"
date: 2026-05-15T15:24:59+07:00
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Creat a new IAM user

1. Navigate to the [AWS Management Console](https://aws.amazon.com/console/).

    - In the search bar, find **IAM**
    - Select **IAM**

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0001.png)

2. Select **IAM user** and click **Create user**

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0002.png)

3. In the ***User details** interface.

    - **User name**: enter ``bedrock-ai-chatbot-user`` 
    - Select **Provide user access to the AWS Management Console - optional**
    - Select **Custom password**, enter: ``Password123``
    - Select **Show password**

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0003.png)

4. Unselect **Users must create a new password at next sign in - Recommended** and click **Next**.

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0004.png)

5. In the **Set permissions** interface.

    - Select **Attach policies directly**
    - Find ``AmazonBedrockFullAccess``
    - Select **AmazonBedrockFullAccess** and click **Next**

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0005.png)

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0006.png)

6. Click **Create user**.

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0007.png)

7. Click **Return to user list** and review **bedrock-ai-chatbot-user**

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0008.png)

![IAM user](/static/images/3-Amazonbedrock/3.1-create-a-new-user/0009.png)