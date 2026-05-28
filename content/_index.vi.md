---
title: "Tổng quan"
date: 2024-01-01
weight: 1
chapter: false
---

# Xây dựng một AI Gateway với Amazon Bedrock bằng Amazon API Gateway

### Tổng quan (Overview)

Kiến trúc này tạo một AI Gateway phía trước Amazon Bedrock bằng cách sử dụng Amazon API Gateway và AWS Lambda. Gateway hoạt động như một điểm truy cập trung tâm cho các AI request, cung cấp các chức năng bảo mật, authorization, quản lý request và routing trước khi chuyển tiếp request đến Amazon Bedrock.

Kiến trúc này cho phép các ứng dụng client tương tác với API của Amazon Bedrock một cách minh bạch, trong khi gateway xử lý authentication, quota management, logging và các yêu cầu doanh nghiệp khác phía sau hệ thống.

### Luồng kiến trúc (Architecture Flow)

![AI Gateway](/images/aigateway.png)

### Nội dung (Content)

1. [Giới thiệu](1-Introduction/)
2. [Các bước chuẩn bị](2-Preparetion/)
3. [Tạo IAM user cho Amazon Bedrock](3-Amazonbedrock/)
4. [Tạo Knowledge Base trên Amazon Bedrock](4-Knowledgebase/)
5. [Triển khai với AWS CloudFormation](5-Launchstack/)
6. [Chạy ứng dụng trên VS Code](6-Runapplication/)
7. [Kiểm thử sau triển khai](7-Testdeployment/)
8. [Cấu hình Authorization](8-Configuringauthorization/)
9. [Dọn dẹp tài nguyên và chi phí](9-Cleanupresourcesandcosts/)