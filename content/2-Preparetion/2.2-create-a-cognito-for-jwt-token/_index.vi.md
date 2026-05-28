---
title: "Tạo Amazon Cognito cho Jwt Token"
date: 2026-05-15T08:42:20+07:00
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

### Tạo Amazon Cognito 

1. Truy cập vào [AWS Management Console](https://aws.amazon.com/console/).

    - Trong thanh tìm kiếm, nhập ``Amazon Cognito``
    - Chọn **Cognito**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0001.png)

2. Chọn **User pools** và nhấn **Create user pool**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0002.png)

3. Trong giao diện **Define your application**.

    - Chọn **Traditional web application** tại mục **Application type**
    - **Name your application**: nhập ``client-aichatbot-cognito``

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0003.png)

4. Trong giao diện **Configure options**, chọn **Email** và **Select attributes**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0004.png)

- Chọn **name**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0005.png)

5. **Return URL**: nhập ``https://localhost:5000/`` và nhấn **Create user directory**.

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0006.png)

6. Chọn **Go to overview**.

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0007.png)

7. Trong giao diện **Amazon Cognito**.

    - Chọn **App clients**
    - Nhấn vào **App client name**
    - Chọn **Edit**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0008.png)

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0009.png)

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00010.png)

8. Trong giao diện **App client**.

    - Bỏ chọn **ALLOW_USER_AUTH** và **ALLOW_USER_SRP_AUTH**
    - Chọn **ALLOW_USER_PASSWORD_AUTH** và **ALLOW_REFRESH_TOKEN_AUTH**
    - Nhấn **Save changes**

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00011.png)

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00012.png)

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00013.png)

9. App client đã được cập nhật thành công sau khi lưu thay đổi.

![AmazonCoginto](/images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00014.png)