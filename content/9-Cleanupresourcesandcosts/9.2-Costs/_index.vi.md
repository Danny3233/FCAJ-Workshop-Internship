---
title: "Chi phí"
date: 2026-05-26T19:24:43+07:00
weight: 2
chapter: false
pre: " <b> 9.2 </b> "
---

### 1. Chi phí OpenSearch Service 

Chi phí chính đến từ:

- IndexingOCU
- SearchOCU

OCU = OpenSearch Compute Unit.

#### Cách tính chi phí 

- 79.438 OCU-hours cho Indexing
- 79.438 OCU-hours cho Search

#### Giá dịch vụ 

- 0.283 USD cho mỗi OCU-hour

#### Tổng chi phí 

- Indexing ≈ 22.48 USD
- Search ≈ 22.48 USD

#### Tổng chi phí OpenSearch

- Tổng ≈ 44.96 USD

![Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0001.png)

---

### 2. Cognito

Amazon Cognito được sử dụng cho:

- Xác thực người dùng
- Đăng nhập và đăng ký
- Tạo JWT token
- Kiểm soát truy cập cho API và ứng dụng

Chi phí rất nhỏ vì chỉ có một vài request xác thực được thực hiện.

#### Mức sử dụng 

- 4 token requests

#### Tổng chi phí 

- ≈ 0.01 USD

Dịch vụ này vẫn nằm trong AWS Free Tier đối với hầu hết nhu cầu sử dụng.

![Cognito Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0003.png)

---

### 3. API Gateway

Amazon API Gateway được sử dụng để tạo và quản lý API cho các backend service như Lambda function.

#### Mức sử dụng 

- 39 HTTP API requests
- 48 API requests

#### Tổng chi phí 

- 0.00 USD

Mức sử dụng vẫn nằm trong AWS Free Tier.

![API Gateway Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0004.png)

---

### 4. Bedrock

Amazon Bedrock được sử dụng để truy cập các foundation AI models như Claude và Cohere.

#### Các mô hình sử dụng 

- Claude 3 Haiku
- Claude Haiku 4.5
- Claude Sonnet 4.5
- Cohere Embed Model 3 - Multilingual

#### Mức sử dụng 

- Số lượng nhỏ input và output tokens

#### Tổng chi phí 

- Khoảng 0.00 USD

Chi phí sử dụng AI model rất thấp so với OpenSearch Service.

![Bedrock Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0005.png)

---

### 5. DynamoDB

Amazon DynamoDB được sử dụng như dịch vụ cơ sở dữ liệu NoSQL để lưu trữ dữ liệu ứng dụng.

#### Mức sử dụng 

- Read Capacity Units trong Free Tier
- Write Capacity Units trong Free Tier
- Storage usage trong Free Tier

#### Tổng chi phí 

- 0.00 USD

Mức sử dụng dịch vụ vẫn được bao phủ bởi AWS Free Tier.

![DynamoDB Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0007.png)

---

### 6. Lambda

AWS Lambda được sử dụng để chạy các serverless backend functions mà không cần quản lý server.

#### Mức sử dụng 

- 101 requests
- 16.258 Lambda GB-seconds

#### Free Tier

- 1,000,000 requests miễn phí
- 400,000 GB-seconds mỗi tháng

#### Tổng chi phí 

- 0.00 USD

Mức sử dụng Lambda vẫn nằm trong AWS Free Tier.

![Lambda Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0008.png)

---

### 7. Thuế theo dịch vụ 

AWS Billing Dashboard cũng hiển thị các khoản thuế áp dụng cho từng dịch vụ.

#### Tổng hợp thuế 

| Service | Pre-tax Charges | Tax |
|---|---|---|
| OpenSearch Service | USD 44.96 | USD 4.50 |
| WAF | USD 6.59 | USD 0.66 |
| Elastic Compute Cloud (EC2) | USD 2.95 | USD 0.30 |
| Secrets Manager | USD 0.33 | USD 0.03 |
| Relational Database Service (RDS) | USD 0.19 | USD 0.02 |

#### Tổng thuế 

- USD 5.51

![Taxes by Service](/images/9-Cleanupresourcesandcosts/9.2-Costs/00010.png)