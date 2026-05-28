---
title: "Tạo IAM user mới"
date: 2026-05-15T15:25:29+07:00
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Tạo IAM user mới

1. Truy cập [Bảng điều khiển quản lý AWS](https://aws.amazon.com/console/).

    - Trong thanh tìm kiếm, tìm **IAM**
    - Chọn **IAM**

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0001.png)

2. Chọn **IAM user** và nhấp vào **Create user**

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0002.png)

3. Trong giao diện **User details**.

    - **User name**: nhập ``bedrock-ai-chatbot-user``
    - Chọn **Provide user access to the AWS Management Console - optional**
    - Chọn **Custom password**, nhập: ``Password123``
    - Chọn **how password**

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0003.png)

4. Bỏ chọn **Users must create a new password at next sign in - Recommended** và nhấp vào **Next**.

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0004.png)

5. Trong giao diện **Set permissions**.

    - Chọn **Attach policies directly**
    - Tìm ``AmazonBedrockFullAccess``
    - Chọn **AmazonBedrockFullAccess** và nhấn **Next**

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0005.png)

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0006.png)

6. Nhấn **Create user**.

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0007.png)

7. Nhấp vào **Return to user list** và xem lại **bedrock-ai-chatbot-user**

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0008.png)

![IAM user](/images/3-Amazonbedrock/3.1-create-a-new-user/0009.png)