---
title: "Clean up Resources"
date: 2026-05-26T19:23:31+07:00
weight: 1
chapter: false
pre: " <b> 9.1 </b> "
---

### Delete Cloud Formation

- Select **Stacks**
- Select **bedrock-llm-gateway**
- **Delete stack**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0001.png)

Type: ``bedrock-llm-gateway`` and click **Delete stack**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0002.png)

### Delete Amazon Bedrock

- Select **Knowledge Bases**
- Select **Knowledge Base Name**
- Click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0003.png)

- Type: ``delete`` and click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0004.png)

### Delete Amazon OpenSearch Service

- Select **Collections**
- Select **Collection name**
- Click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0005.png)

Type: ``confirm`` and click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0006.png)

- Delete **access policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0007.png)

- Delete **encryption policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0008.png)

- Delete **network policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0009.png)

### Delete DynmoDB

- Select **Tables**
- Select **Table name**
- Click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00010.png)

- Select **Delete all CloudWatch alarms for 3 tables tables selected.**, type: ``confirm`` and click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00011.png)

### Delete Amazon S3

- Select **Bucket name**
- Click **Empty**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00012.png)

- Type: ``permanently delete`` and click **Empty**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00013.png)

- Type: ``bedrock-aichatbot-bucket`` and click **Delete bucket**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00014.png)

- Type: ``cf-templates-1aglbst73ckzw-ap-southeast-1`` and click **Delete bucket**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00015.png)

### Delete Identity and Access Management (IAM)

- Select **IAM users**
- Select **User name**
- Click **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00016.png)

- Click **Deactivate access key**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00017.png)

- Type: ``confirm`` and click **Delete user**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00018.png)