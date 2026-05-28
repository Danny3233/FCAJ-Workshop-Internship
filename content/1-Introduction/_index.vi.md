---
title: "Giới thiệu"
date: 2026-05-14T13:38:56+07:00
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

## Amazon Route 53

Amazon Route 53 quản lý định tuyến tên miền tùy chỉnh, cho phép các ứng dụng truy cập Cổng API thông qua tên miền dành riêng cho công ty thay vì điểm cuối Cổng API mặc định.

### Amazon API Gateway

Amazon API Gateway đóng vai trò là điểm truy cập chính cho các yêu cầu và cung cấp các tính năng như:

- Định tuyến yêu cầu
- Quản lý vòng đời API
- Giới hạn tốc độ và throtting
- Giám sát và ghi log
- Tích hợp phân quyền/uỷ quyền 

### Bộ uỷ quyền Lambda 

Bộ ủy quyền Lambda xác thực các yêu cầu đến trước khi chúng đến Amazon Bedrock. Các phương thức ủy quyền phổ biến bao gồm:

- Xác thực mã thông báo JWT
- Tích hợp Amazon Cognito
- OAuth 2.0
- Logic xác thực tuỳ chỉnh

### Chức năng tích hợp Lambda 

Chức năng tích hợp Lambda tự động chuyển tiếp các yêu cầu đến Amazon Bedrock trong khi vẫn giữ nguyên cấu trúc API gốc. Nó ký các yêu cầu bằng thông tin xác thực AWS và hỗ trợ nhiều API Bedrock mà không cần thay đổi phía máy khách.

### Amazon Bedrock
Amazon Bedrock cung cấp quyền truy cập vào các mô hình nền tảng và khả năng trí tuệ nhân tạo như:

- Mô hình ngôn ngữ quy mô lớn (LLM)
- Cơ sở tri thức
- Thế hệ tăng cường truy xuất (RAG)
- Các tác nhân AI
- Lan can bảo vệ

Hãy bắt dầu bằng cách thiết lập các bước chuẩn bị ở bước tiếp theo!