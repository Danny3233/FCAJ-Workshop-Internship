---
title: "Triển khai bằng AWS CloudFormation"
date: 2026-05-19T15:34:22+07:00
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

### Khởi chạy Stack từ AWS CloudFormation

1. Chọn nút **Launch Stack** bên dưới:

<a href="https://console.aws.amazon.com/cloudformation/home#/stacks/quickcreate?templateURL=https%3A%2F%2Fpomatas-public-blogs.s3.us-east-1.amazonaws.com%2Fdynatrace-api-gateway%2Fbedrock-llm-gateway.yaml&stackName=bedrock-llm-gateway&param_EnableAuthorizer=false&param_EndpointType=PRIVATE"
   target="_blank"
   rel="noopener noreferrer">
  <img src="/images/launch-stack-button.png"
       alt="Launch Stack"
       style="margin:0; display:inline-block; float:left;">
</a>

<div style="clear: both;"></div>

2. Trong trang **Quick create stack**, cấu hình các tham số chính như sau. Để xem mô tả đầy đủ các tham số, tham khảo [documentation](https://github.com/aws-samples/sample-ai-gateway-for-amazon-bedrock?tab=readme-ov-file#cloudformation-parameters).

| Tham số | Miêu tả | Chọn giá trị | Tại sao |
|---|---|---|---|
| **EndpointType** | Kiểu truy cập API Gateway endpoint (PRIVATE hoặc REGIONAL) | **PRIVATE** | Chỉ cho phép truy cập nội bộ an toàn |
| **EnableAuthorizer** | Bật Lambda Authorizer cho API Gateway | **false** | Bắt đầu không cần xác thực để dễ kiểm thử |
| **CustomDomain** | Tên miền tùy chỉnh cho API Gateway | *(để trống)* | Sử dụng domain mặc định ban đầu |
| **HostedZoneId** | Route 53 Hosted Zone ID để xác thực SSL cho custom domain | *(để trống)* | Không cần thiết khi dùng domain mặc định |

* Chọn quyền **I acknowledge that AWS CloudFormation might create IAM resources**.
* Giữ nguyên các cấu hình mặc định khác và chọn **Create Stack**.
* Trong trang stack, chờ đến khi **Status** chuyển sang **CREATE_COMPLETE**.
* Chọn **Outputs** và sao chép các giá trị của **GatewayUrl**, **VpcId** và **ApiId** để sử dụng cho việc kiểm thử gateway sau này.

3. Trong giao diện **Quick create stack**.

   * Chọn **I acknowledge that AWS CloudFormation might create IAM resources.**
   * Nhấn **Create Stack**

![Launch Stack](/images/5-Launchstack/0001.png)

![Launch Stack](/images/5-Launchstack/0002.png)

![Launch Stack](/images/5-Launchstack/0003.png)

4. Kiểm tra trạng thái **CREATE_IN_PROGRESS** và nhấn biểu tượng refresh để theo dõi khi chuyển sang **CREATE_COMPLETE**.

![Launch Stack](/images/5-Launchstack/0004.png)

5. Sau khi trạng thái là **CREATE_COMPLETE**, chọn **Outputs**.

![Launch Stack](/images/5-Launchstack/0005.png)

6. Kiểm tra các giá trị trong **Outputs**.

![Launch Stack](/images/5-Launchstack/0006.png)