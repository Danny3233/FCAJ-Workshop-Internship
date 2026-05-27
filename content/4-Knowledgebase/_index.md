---
title: "Create a Knowledge base on Amazon Bedrock"
date: 2026-05-19T10:04:38+07:00
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Create a Knowledgebase on Amazon Bedrock

1. In the **AWS Management Console**.
    - Select **Regions** in the dropdown
    - Select **Singapore**
    - Review **Region: Singapore**

![Knowledgebase](images/4-Knowledgebase/0001.png)

![Knowledgebase](images/4-Knowledgebase/0002.png)

![Knowledgebase](images/4-Knowledgebase/0003.png)

2. In the search bar, find ``Amazon Bedrock`` and click **Amazon Bedrock**.

![Knowledgebase](images/4-Knowledgebase/0004.png)

3. In the **Knowledge Bases** interface.

    - Select **Knowledeg Bases** 
    - Select **Create** in the dropdown 
    - Click **Knowlege Base with vector store**

![Knowledgebase](images/4-Knowledgebase/0005.png)

4. In the **Provide Knowledge Base details**.

    - **Knowledge Base name**: enter ``Bedrock-Knowledge-Base``
    - **Knowledge Base description - optional**: enter ``Test knowledge base for ai chatbot``
    - Select **Create and use a new service role**

![Knowledgebase](images/4-Knowledgebase/0006.png)

5. Select **Amazon S3** and click **Next**

![Knowledgebase](images/4-Knowledgebase/0007.png)

![Knowledgebase](images/4-Knowledgebase/0008.png)


6. In the **Configure data source** interface.

    - **Data source name**: enter ``bedrock-data-source-kb``
    - Select **This AWS account**
    - Click **Browse S3**

![Knowledgebase](images/4-Knowledgebase/0009.png)

7. Select **bedrock-aichatbot-bucket** and click **Choose**.

![Knowledgebase](images/4-Knowledgebase/00010.png)

8. **S3 URL**: enter ``s3://bedrock-aichatbot-bucket/docs/`` and click **View** to check S3 URL.

![Knowledgebase](images/4-Knowledgebase/00011.png)

9. View **S3**.

![Knowledgebase](images/4-Knowledgebase/00012.png)

10. Select **Amazon Bedrock default parset** and click **Next**.

![Knowledgebase](images/4-Knowledgebase/00013.png)


11. Select **Select model**.

![Knowledgebase](images/4-Knowledgebase/00014.png)

- Select **Cohere**
- Select **Embed Multilingual**
- Click **Apply**

![Knowledgebase](images/4-Knowledgebase/00015.png)

12. Select **Quick create a new vector store - Recommended** and **Select a vector store**.

![Knowledgebase](images/4-Knowledgebase/00016.png)

- Select **Amazon OpenSearch Serverless**

![Knowledgebase](images/4-Knowledgebase/00017.png)

13. Click **Next**.

![Knowledgebase](images/4-Knowledgebase/00018.png)

14. Click **Create Knowledge Base**.

![Knowledgebase](images/4-Knowledgebase/00019.png)

15. Preparting to create the **Amazon OpenSearch Serverless**, then wait 3-5 minutes for the setup process to complete.

![Knowledgebase](images/4-Knowledgebase/00020.png)

16. Review **Knowledge Base overview** and **Data source**.

![Knowledgebase](images/4-Knowledgebase/00021.png)

![Knowledgebase](images/4-Knowledgebase/00022.png)