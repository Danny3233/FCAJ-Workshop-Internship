---
title: "Tạo Amazon S3 cho Amazon Bedrock"
date: 2026-05-14T15:12:15+07:00
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

### Tạo Bucket S3
1. Tải xuống tệp [.zip](/docs.zip) và truy cập [AWS Management Console](https://aws.amazon.com/console/).

    - Trong thanh tìm kiếm, tìm **S3**
    - Chọn **S3** từ danh sách dịch vụ

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0001.png)

2. Trong giao diện **Amazon S3** và nhấp vào nút **Create Bucket**.

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0002.png)

3. Trong giao diện **Create Bucket**

    - **Bucket name**: nhập ``tên-bucket-của-bạn`` (vui lòng sử dụng tên khác nếu tên đó đã được sử dụng).
    - Cuộn xuống

{{% notice warning %}}
**Quy tắc đặt tên quan trọng:**
{{% /notice %}}
- Tên bucket phải là duy nhất trên toàn cầu trong tất cả các tài khoản AWS
- Phải dài từ 3 đến 63 ký tự
- Chỉ được chứa chữ cái viết thường, số và dấu gạch ngang
- Không được bắt đầu hoặc kết thúc bằng dấu gạch ngang
- Không được chứa khoảng trắng hoặc chữ cái viết hoa

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0003.png)

4. Nhấp vào **Create Bucket** và chọn **Upload** sau khi tạo bucket.

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0004.png)

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0005.png)

5. Trong giao diện **Upload**.

    - Chọn **Add folder**
    - Chọn **Docs** và nhấp vào **Tải lên**

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0006.png)

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0007.png)

6. Trong giao diện **Files and folders**.

    - Cuộn xuống

    - Nhấp vào **Upload**

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0008.png)

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/0009.png)

7. Quá trình tải lên S3 đã thành công.

![AmazonS3](/images/2-Preparetion/2.1-create-a-s3-for-bedrock/00010.png)