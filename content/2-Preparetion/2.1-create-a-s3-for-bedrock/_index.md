---
title: "Create a Amazon S3 for Amazon Bedrock"
date: 2026-05-14T15:11:40+07:00
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

### Create a Bucket S3
1. Download the [.zip](/docs.zip) file and Navigate to the [AWS Management Console](https://aws.amazon.com/console/).

    - In the search bar, find **S3**
    - Select **S3** from the servies list

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0001.png)

2. In the **Amazon S3** interface and Click **Create Bucket** button.

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0002.png)

3. In the **Create Bucket** interfece

    - **Bucket name**: enter ``your-bucket-name`` (please use a different name if it's already taken.).
    - Scroll down 

{{% notice warning %}}
**Important Naming Rules:**
{{% /notice %}}
- Bucket names must be globally unique across all AWS accounts
- Must be 3-63 characters long
- Can contain only lowercase letters, numbers, and hyphens
- Cannot start or end with a hyphen
- Cannot contain spaces or uppercase letters

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0003.png)

4. Click **Create Bucket** and select **Upload** after creating the bucket.

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0004.png)

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0005.png)

5. In the **Upload** interface.

    - Select **Add folder**
    - Select **Docs** and click **Tải lên**

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0006.png)

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0007.png)

6. In the **Files and folders** interface.

    - Scroll down 
    - Click **Upload**

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0008.png)

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0009.png)

7. In the upload succeeded after uploading to S3.

![AmazonS3](/static/images/2-Preparetion/2.1-create-a-s3-for-bedrock/00010.png)