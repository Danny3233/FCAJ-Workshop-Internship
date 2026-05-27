---
title: "Run Application on VS Code"
date: 2026-05-25T14:32:59+07:00
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Run Application on VS Code

1. Download the [.zip](/AI-Chatbot.zip) file and Open the VS Code.

- Select **backend**
- Open the **.env**

![Run Application](/images/6-Runapplication/0001.png)

![Run Application](/images/6-Runapplication/0002.png)

![Run Application](/images/6-Runapplication/0003.png)

2. Copy and Paste into the **.env**.

- Go back to **AWS Management Console** to copy **ap-southeast-1**.

![Run Application](/images/6-Runapplication/0004.png)

- Select **Download** on the PC and open the **.csv** from **IAM** to copy **Access key ID** and **Secret access key**.

![Run Application](/images/6-Runapplication/0005.png)

![Run Application](/images/6-Runapplication/0006.png)

- Go to **Amazon Cognito** and copy **User pool ID**.

![Run Application](/images/6-Runapplication/0007.png)

- Select **App client**.

    - Copy **Client ID** and **Client secret**

![Run Application](/images/6-Runapplication/0008.png)

- Go to **Amazon Bedrock** and select **Knowledge Bases** to copy **Knowledge Base ID**.

![Run Application](/images/6-Runapplication/0009.png)

- Select **Model catalog**.

    - Select **Claude 3 Haiku**
    - Copy **Model ID**

![Run Application](/images/6-Runapplication/00010.png)

![Run Application](/images/6-Runapplication/00011.png)

- Paste into the **.env** on VS Code.

![Run Application](/images/6-Runapplication/00012.png)

3. Select **frontend**.

- Right click and select **Open in Integrated Terminal**

![Run Application](/images/6-Runapplication/00013.png)

- Type ``npm run dev``

![Run Application](/images/6-Runapplication/00014.png)

![Run Application](/images/6-Runapplication/00015.png)

4. Select **backend**.

- Right click and select **Open in Integrated Terminal**
- Type ``node server`` to run the backend server

![Run Application](/images/6-Runapplication/00016.png)

5. Type ``aws configure`` to create new tables on **DynamoDB**. If it need your new access key instead of old access key.

- **AWS Access Key ID**: enter ``your-access-key-ID``
- **AWS Secret Access Key**: enter ``your-secret-access-key``
- **Default region name**: enter ``ap-southeast-1`` if you want to choose any region name
- **Default output format**: enter ``json``

![Run Application](/images/6-Runapplication/00017.png)

6. Select **scripts** in the backend.

- Right click and select **Open in Integrated Terminal**
- Type ``node createTables``
- After creating Tables into **DynamoDB**

![Run Application](/images/6-Runapplication/00018.png)

- Go to **Amazon DynmaoDB** and select **Tables** to view tables.

![Run Application](/images/6-Runapplication/00019.png)

7. Open the frontend and login interface.

![Run Application](/images/6-Runapplication/00020.png)

![Run Application](/images/6-Runapplication/00021.png)

![Run Application](/images/6-Runapplication/00022.png)

8. After login into the chatbot interface.

![Run Application](/images/6-Runapplication/00023.png)

- Go back to **Amazon Cognito** and select **Users** to check email.

![Run Application](/images/6-Runapplication/00024.png)

10. You can message the bot, and the bot can reply and read documents from S3.

![Run Application](/images/6-Runapplication/00025.png)