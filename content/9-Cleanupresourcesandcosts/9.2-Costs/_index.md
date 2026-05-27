---
title: "Costs"
date: 2026-05-26T19:24:30+07:00
weight: 2
chapter: false
pre: " <b> 9.2 </b> "
---

### 1. OpenSearch Service Costs

The main costs come from:

- IndexingOCU
- SearchOCU

OCU = OpenSearch Compute Unit.

#### Cost Calculation

- 79.438 OCU-hours for Indexing
- 79.438 OCU-hours for Search

#### Pricing

- 0.283 USD per OCU-hour

#### Total Cost

- Indexing ≈ 22.48 USD
- Search ≈ 22.48 USD

#### Total OpenSearch Cost

- Total ≈ 44.96 USD

![Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0001.png)

---

### 2. Cognito 

Amazon Cognito is used for:

- User authentication
- Login and registration
- JWT token generation
- Access control for APIs and applications

The cost is very small because only a few authentication requests were made.

#### Usage

- 4 token requests

#### Total Cost

- ≈ 0.01 USD

This service is still within the free tier for most usage.

![Cognito Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0003.png)

---

### 3. API Gateway

Amazon API Gateway is used to create and manage APIs for backend services such as Lambda functions.

#### Usage

- 39 HTTP API requests
- 48 API requests

#### Total Cost

- 0.00 USD

The usage is still within the AWS Free Tier.

![API Gateway Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0004.png)

---

### 4. Bedrock

Amazon Bedrock is used to access foundation AI models such as Claude and Cohere.

#### Models Used

- Claude 3 Haiku
- Claude Haiku 4.5
- Claude Sonnet 4.5
- Cohere Embed Model 3 - Multilingual

#### Usage

- Small number of input and output tokens

#### Total Cost

- Approximately 0.00 USD

The AI model usage cost is very low compared to OpenSearch Service.

![Bedrock Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0005.png)

---

### 5. DynamoDB 

Amazon DynamoDB is used as a NoSQL database service for storing application data.

#### Usage

- Read Capacity Units within Free Tier
- Write Capacity Units within Free Tier
- Storage usage within Free Tier

#### Total Cost

- 0.00 USD

The service usage is still covered by the AWS Free Tier.

![DynamoDB Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0007.png)

---

### 6. Lambda 

AWS Lambda is used to run serverless backend functions without managing servers.

#### Usage

- 101 requests
- 16.258 Lambda GB-seconds

#### Free Tier

- 1,000,000 free requests
- 400,000 GB-seconds per month

#### Total Cost

- 0.00 USD

The Lambda usage remains within the AWS Free Tier.

![Lambda Costs](/images/9-Cleanupresourcesandcosts/9.2-Costs/0008.png)

---

### 7. Taxes by Service

The AWS billing dashboard also shows taxes applied to each service.

#### Tax Summary

| Service | Pre-tax Charges | Tax |
|---|---|---|
| OpenSearch Service | USD 44.96 | USD 4.50 |
| WAF | USD 6.59 | USD 0.66 |
| Elastic Compute Cloud (EC2) | USD 2.95 | USD 0.30 |
| Secrets Manager | USD 0.33 | USD 0.03 |
| Relational Database Service (RDS) | USD 0.19 | USD 0.02 |

#### Total Tax

- USD 5.51

![Taxes by Service](/images/9-Cleanupresourcesandcosts/9.2-Costs/00010.png)