---
title: "Tạo môi trường VPC"
date: 2026-05-21T16:06:43+07:00
weight: 1
chapter: false
pre: " <b> 7.1 </b> "
---

### Tạo môi trường VPC 

1. Mở [CloudShell Console](https://console.aws.amazon.com/cloudshell/home).

    - Chọn biểu tượng **+**
    - Nhấn **Create VPC environment (max 2)**

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0001.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0002.png)

2. Trong giao diện **CloudShell Region**.

    - **Name**: nhập ``AIGatewayTest``
    - **VPC**: chọn **bedrock-llm-gateway-vpc**, 10.0.0.0/16

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0003.png)

3. Chọn **bedrock-llm-gateway-private-subnet-1**.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0004.png)

4. Chọn **default - default VPC security group** và nhấn **Create**.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0005.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0006.png)

5. Vui lòng chờ vài phút sau khi tạo môi trường VPC trong CloudShell.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0007.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0008.png)