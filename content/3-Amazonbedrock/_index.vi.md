---
title: "Tạo IAM user cho Amazon bedrock"
date: 2026-05-15T14:33:48+07:00
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Tổng quan (Overview)

Trong phần này, bạn sẽ tạo một IAM user với các quyền cần thiết để truy cập dịch vụ Amazon Bedrock một cách an toàn.

IAM user sẽ được sử dụng để:

- Truy cập AWS Management Console
- Tương tác với Amazon Bedrock
- Tạo Knowledge Bases
- Quản lý tài nguyên S3 cho ứng dụng AI
- Sử dụng AWS CLI hoặc AWS SDK bằng lập trình

> Việc sử dụng IAM user thay vì tài khoản root tuân theo các best practices về bảo mật của AWS và giúp bảo vệ môi trường AWS của bạn.

**⚠️ Cảnh báo (Warning):**

Không nên sử dụng AWS root account cho các hoạt động hằng ngày hoặc phát triển ứng dụng. Việc dùng root account cho Amazon Bedrock, Knowledge Bases hoặc API access có thể làm tăng rủi ro bảo mật nếu thông tin xác thực bị lộ. Luôn tạo IAM user hoặc IAM role riêng với quyền truy cập giới hạn.

**🔒 Lưu ý bảo mật (Security Note):**

Sau khi tạo IAM user:

- Lưu trữ Access Key ID và Secret Access Key ở nơi an toàn
- Không hardcode credentials trong source code hoặc repository
- Bật Multi-Factor Authentication (MFA)
- Thay đổi access key định kỳ
- Tuân theo nguyên tắc least privilege

Các AWS managed policies được khuyến nghị cho môi trường Amazon Bedrock:

```text
AmazonBedrockFullAccess
AmazonS3FullAccess
IAMReadOnlyAccess
```

#### Các nội dung chính trong phần này:

* Tạo IAM user mới
* Gán quyền cho Amazon Bedrock
* Tạo Access Key ID và Secret Access Key
* Đăng nhập IAM user