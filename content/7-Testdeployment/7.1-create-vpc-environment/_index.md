---
title: "Create VPC Environment"
date: 2026-05-21T16:05:24+07:00
weight: 1
chapter: false
pre: " <b> 7.1 </b> "
---

### Create VPC Environment

1. Open the [CloudShell Console](https://console.aws.amazon.com/cloudshell/home).

    - Select the **+** icon 
    - Click **Create VPC environment (max 2)**

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0001.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0002.png)

2. In the **CloudShell Region** interface.

    - **Name**: enter ``AIGatewayTest``
    - **VPC** select **bedrock-llm-gateway-vpc**, 10.0.0.0/16

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0003.png)

3. Select **bedrock-llm-gateway-private-subnet-1**.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0004.png)

4. Select **default - default VPC secruity group** and click **Create**.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0005.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0006.png)

5. Please wait a few minutes after creating the VPC environment in CloudShell.

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0007.png)

![Create vpc environment](/images/7-Testdeployment/7.1-create-vpc-environment/0008.png)