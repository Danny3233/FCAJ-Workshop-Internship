---
title: "Tạo Knowledge Base trên Amazon Bedrock"
date: 2026-05-19T10:04:21+07:00
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Tạo Knowledge Base trên Amazon Bedrock 

1. Trong **AWS Management Console**.

    - Chọn **Regions** trong menu dropdown
    - Chọn **Singapore**
    - Kiểm tra lại **Region: Singapore**

![Knowledgebase](/images/4-Knowledgebase/0001.png)

![Knowledgebase](/images/4-Knowledgebase/0002.png)

![Knowledgebase](/images/4-Knowledgebase/0003.png)

2. Trong thanh tìm kiếm, nhập ``Amazon Bedrock`` và chọn **Amazon Bedrock**.

![Knowledgebase](/images/4-Knowledgebase/0004.png)

3. Trong giao diện **Knowledge Bases**.

    - Chọn **Knowledge Bases**
    - Chọn **Create** trong menu dropdown
    - Nhấn **Knowledge Base with vector store**

![Knowledgebase](/images/4-Knowledgebase/0005.png)

4. Trong phần **Provide Knowledge Base details**.

    - **Knowledge Base name**: nhập ``Bedrock-Knowledge-Base``
    - **Knowledge Base description - optional**: nhập ``Test knowledge base for ai chatbot``
    - Chọn **Create and use a new service role**

![Knowledgebase](/images/4-Knowledgebase/0006.png)

5. Chọn **Amazon S3** và nhấn **Next**.

![Knowledgebase](/images/4-Knowledgebase/0007.png)

![Knowledgebase](/images/4-Knowledgebase/0008.png)

6. Trong giao diện **Configure data source**.

    - **Data source name**: nhập ``bedrock-data-source-kb``
    - Chọn **This AWS account**
    - Nhấn **Browse S3**

![Knowledgebase](/images/4-Knowledgebase/0009.png)

7. Chọn **bedrock-aichatbot-bucket** và nhấn **Choose**.

![Knowledgebase](/images/4-Knowledgebase/00010.png)

8. **S3 URL**: nhập ``s3://bedrock-aichatbot-bucket/docs/`` và nhấn **View** để kiểm tra S3 URL.

![Knowledgebase](/images/4-Knowledgebase/00011.png)

9. Xem thư mục trong **S3**.

![Knowledgebase](/images/4-Knowledgebase/00012.png)

10. Chọn **Amazon Bedrock default parser** và nhấn **Next**.

![Knowledgebase](/images/4-Knowledgebase/00013.png)

11. Chọn **Select model**.

![Knowledgebase](/images/4-Knowledgebase/00014.png)

- Chọn **Cohere**
- Chọn **Embed Multilingual**
- Nhấn **Apply**

![Knowledgebase](/images/4-Knowledgebase/00015.png)

12. Chọn **Quick create a new vector store - Recommended** và **Select a vector store**.

![Knowledgebase](/images/4-Knowledgebase/00016.png)

- Chọn **Amazon OpenSearch Serverless**

![Knowledgebase](/images/4-Knowledgebase/00017.png)

13. Nhấn **Next**.

![Knowledgebase](/images/4-Knowledgebase/00018.png)

14. Nhấn **Create Knowledge Base**.

![Knowledgebase](/images/4-Knowledgebase/00019.png)

15. Hệ thống sẽ chuẩn bị tạo **Amazon OpenSearch Serverless**, sau đó chờ khoảng 3–5 phút để hoàn tất quá trình thiết lập.

![Knowledgebase](/images/4-Knowledgebase/00020.png)

16. Kiểm tra lại **Knowledge Base overview** và **Data source**.

![Knowledgebase](/images/4-Knowledgebase/00021.png)

![Knowledgebase](/images/4-Knowledgebase/00022.png)