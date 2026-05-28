---
title: "Dọn dẹp tài nguyên"
date: 2026-05-26T19:23:46+07:00
weight: 1
chapter: false
pre: " <b> 9.1 </b> "
---

### Xóa CloudFormation (Delete CloudFormation)

- Chọn **Stacks**
- Chọn **bedrock-llm-gateway**
- Nhấn **Delete stack**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0001.png)

Nhập: ``bedrock-llm-gateway`` và nhấn **Delete stack**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0002.png)

---

### Xóa Amazon Bedrock (Delete Amazon Bedrock)

- Chọn **Knowledge Bases**
- Chọn **Knowledge Base Name**
- Nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0003.png)

- Nhập: ``delete`` và nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0004.png)

---

### Xóa Amazon OpenSearch Service (Delete Amazon OpenSearch Service)

- Chọn **Collections**
- Chọn **Collection name**
- Nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0005.png)

Nhập: ``confirm`` và nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0006.png)

- Xóa **access policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0007.png)

- Xóa **encryption policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0008.png)

- Xóa **network policy**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/0009.png)

---

### Xóa DynamoDB (Delete DynamoDB)

- Chọn **Tables**
- Chọn **Table name**
- Nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00010.png)

- Chọn **Delete all CloudWatch alarms for 3 tables selected.**, nhập: ``confirm`` và nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00011.png)

---

### Xóa Amazon S3 (Delete Amazon S3)

- Chọn **Bucket name**
- Nhấn **Empty**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00012.png)

- Nhập: ``permanently delete`` và nhấn **Empty**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00013.png)

- Nhập: ``bedrock-aichatbot-bucket`` và nhấn **Delete bucket**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00014.png)

- Nhập: ``cf-templates-1aglbst73ckzw-ap-southeast-1`` và nhấn **Delete bucket**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00015.png)

---

### Xóa Identity and Access Management (IAM)

- Chọn **IAM users**
- Chọn **User name**
- Nhấn **Delete**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00016.png)

- Nhấn **Deactivate access key**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00017.png)

- Nhập: ``confirm`` và nhấn **Delete user**

![Clean up Resources](/images/9-Cleanupresourcesandcosts/9.1-Cleanupresources/00018.png)