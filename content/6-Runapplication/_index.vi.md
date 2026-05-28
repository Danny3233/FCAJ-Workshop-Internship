---
title: "Chạy Ứng dụng trên VS Code"
date: 2026-05-25T14:33:31+07:00
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Chạy ứng dụng trên VS Code (Run Application on VS Code)

1. Tải file [.zip](/AI-Chatbot.zip) và mở bằng VS Code.

- Chọn thư mục **backend**
- Mở file **.env**

![Run Application](/images/6-Runapplication/0001.png)

![Run Application](/images/6-Runapplication/0002.png)

![Run Application](/images/6-Runapplication/0003.png)

2. Sao chép và dán thông tin vào file **.env**.

- Quay lại **AWS Management Console** để sao chép region **ap-southeast-1**.

![Run Application](/images/6-Runapplication/0004.png)

- Chọn thư mục **Download** trên máy tính và mở file **.csv** từ **IAM** để sao chép **Access key ID** và **Secret access key**.

![Run Application](/images/6-Runapplication/0005.png)

![Run Application](/images/6-Runapplication/0006.png)

- Truy cập **Amazon Cognito** và sao chép **User pool ID**.

![Run Application](/images/6-Runapplication/0007.png)

- Chọn **App client**.

    - Sao chép **Client ID** và **Client secret**

![Run Application](/images/6-Runapplication/0008.png)

- Truy cập **Amazon Bedrock** và chọn **Knowledge Bases** để sao chép **Knowledge Base ID**.

![Run Application](/images/6-Runapplication/0009.png)

- Chọn **Model catalog**.

    - Chọn **Claude 3 Haiku**
    - Sao chép **Model ID**

![Run Application](/images/6-Runapplication/00010.png)

![Run Application](/images/6-Runapplication/00011.png)

- Dán toàn bộ thông tin vào file **.env** trên VS Code.

![Run Application](/images/6-Runapplication/00012.png)

3. Chọn thư mục **frontend**.

- Nhấn chuột phải và chọn **Open in Integrated Terminal**

![Run Application](/images/6-Runapplication/00013.png)

- Nhập lệnh:

```bash
npm run dev
```

![Run Application](/images/6-Runapplication/00014.png)

![Run Application](/images/6-Runapplication/00015.png)

4. Chọn thư mục **backend**.

- Nhấn chuột phải và chọn **Open in Integrated Terminal**
- Nhập lệnh ``node server`` để chạy backend server

![Run Application](/images/6-Runapplication/00016.png)

5. Nhập lệnh `aws configure` để tạo bảng mới trên **DynamoDB** nếu hệ thống yêu cầu access key mới thay cho access key cũ.

- **AWS Access Key ID**: nhập ``your-access-key-ID``
- **AWS Secret Access Key**: nhập ``your-secret-access-key``
- **Default region name**: nhập ``ap-southeast-1`` hoặc region khác nếu muốn
- **Default output format**: nhập ``json``

![Run Application](/images/6-Runapplication/00017.png)

6. Chọn thư mục **scripts** trong backend.

- Nhấn chuột phải và chọn **Open in Integrated Terminal**
- Nhập lệnh:

```bash
node createTables
```

- Sau khi tạo bảng trong **DynamoDB** thành công.

![Run Application](/images/6-Runapplication/00018.png)

- Truy cập **Amazon DynamoDB** và chọn **Tables** để xem danh sách bảng.

![Run Application](/images/6-Runapplication/00019.png)

7. Mở frontend và giao diện đăng nhập.

![Run Application](/images/6-Runapplication/00020.png)

![Run Application](/images/6-Runapplication/00021.png)

![Run Application](/images/6-Runapplication/00022.png)

8. Sau khi đăng nhập vào giao diện chatbot.

![Run Application](/images/6-Runapplication/00023.png)

- Quay lại **Amazon Cognito** và chọn **Users** để kiểm tra email người dùng.

![Run Application](/images/6-Runapplication/00024.png)

10. Bạn có thể nhắn tin với bot, bot có thể phản hồi và đọc tài liệu từ S3.

![Run Application](/images/6-Runapplication/00025.png)