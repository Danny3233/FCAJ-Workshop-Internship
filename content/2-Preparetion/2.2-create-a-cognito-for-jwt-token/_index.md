---
title: "Create a Amazon Cognito for Jwt Token"
date: 2026-05-15T08:42:52+07:00
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

### Create a Amazon Cognito

1. Navigate to the [AWS Management Console](https://aws.amazon.com/console/).

    - In the search bar, find ``Amazon Cognito``
    - Select **Cognito**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0001.png)

2. Select **User pools** and click **Create user pool**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0002.png)

3. In the **Define your application** interface.

    - Select **Traditional web application** on the Appplication type
    - **Name your application**: Enter ``client-aichatbot-cognito``

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0003.png)

4. In the **Configure options** interface, select **Email** and **Select attributes**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0004.png)

- Select **name**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0005.png)

5. **Return URL**: enter ``https://localhost:5000/`` and click **Create user directory**. 

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0006.png)

6. Select **Go to overview**.

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0007.png)

7. In the **Amazon Ognito** interface.

    - Select **App clients**
    - Click **App client name**
    - Select **Edit**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0008.png)

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/0009.png)

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00010.png)

8. In the **App client** interface.

    - Unselect **ALLOW_USER_AUTH** and **ALLOW_USER_SRP_AUTH**
    - Select **ALLOW_USER_PASSWORD_AUTH** and **ALLOW_REFRESH_TOKEN_AUTH**
    - Click **Save changes**

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00011.png)

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00012.png)

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00013.png)

9. In the app client has been updated successfully after saving change.

![AmazonCoginto](images/2-Preparetion/2.2-create-a-cognito-for-jwt-token/00014.png)
