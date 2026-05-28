---
title: "Các bước chuẩn bị"
date: 2026-05-14T14:37:15+07:00
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## Tổng quan (Overview)

Trong bài lab này, chúng ta sẽ xây dựng kiến trúc AI Gateway bằng cách sử dụng Amazon API Gateway, AWS Lambda và Amazon Bedrock. Trước khi triển khai các thành phần của gateway, cần chuẩn bị các dịch vụ AWS, quyền truy cập và cấu hình bảo mật cần thiết.

Giai đoạn chuẩn bị bao gồm việc thiết lập quản lý API, cơ chế xác thực, Lambda execution role và quyền truy cập cho Amazon Bedrock. Việc cấu hình đúng rất quan trọng để đảm bảo giao tiếp an toàn giữa ứng dụng khách và các dịch vụ AI.

⚠️ **Cảnh báo (Warning)**: Cấu hình IAM permission hoặc API Gateway không chính xác có thể khiến request không thể gửi đến Amazon Bedrock hoặc làm lộ API cho các truy cập trái phép.

🔒 **Lưu ý bảo mật (Security Note)**: Xác thực (Authentication) và phân quyền (Authorization) luôn cần được triển khai trước khi công khai AI endpoint cho ứng dụng khách. Việc sử dụng JWT validation, Lambda Authorizer hoặc Amazon Cognito giúp bảo vệ tài nguyên AI khỏi việc sử dụng trái phép.

---

## Tài nguyên cần thiết (Required Resources)

Để cấu hình môi trường AI Gateway, chúng ta sẽ tạo và sử dụng các tài nguyên AWS sau:

| Resource | Purpose |
|---|---|
| Amazon API Gateway | Quản lý API endpoint và điều hướng request |
| AWS Lambda | Xử lý xác thực và chuyển tiếp request |
| Amazon Bedrock | Cung cấp foundation models và khả năng AI |
| AWS IAM | Kiểm soát quyền truy cập và chính sách bảo mật |
| Amazon CloudWatch | Giám sát log và hoạt động API |
| Amazon Cognito | Quản lý xác thực người dùng và JWT token |
| Amazon Route 53 | Cấu hình custom domain cho gateway |
| AWS CLI | Quản lý tài nguyên AWS từ terminal |
| Python hoặc Node.js | Phát triển Lambda function và script |

---

## Môi trường phát triển (Development Environment)

Các công cụ được khuyến nghị để phát triển và kiểm thử:

- Visual Studio Code
- Git
- Postman
- curl
- Python 3.x
- Node.js
- AWS SDK (Boto3)

---

## Quyền cần thiết (Required Permissions)

Tài khoản AWS cần có các quyền sau:

- Quản lý API Gateway
- Triển khai Lambda
- Quản lý IAM role
- Gọi mô hình Amazon Bedrock
- Ghi log CloudWatch

Ví dụ policy quyền cho Amazon Bedrock:

```json
{
  "Effect": "Allow",
  "Action": [
    "bedrock:InvokeModel",
    "bedrock:InvokeModelWithResponseStream"
  ],
  "Resource": "*"
}
```