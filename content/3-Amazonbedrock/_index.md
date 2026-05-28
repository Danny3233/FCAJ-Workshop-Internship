---
title: "Create an IAM user for Amazon Bedrock"
date: 2026-05-15T14:33:34+07:00
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Overview

In this section, you will create an IAM user with the necessary permissions to access Amazon Bedrock services securely.

The IAM user will be used to:

- Access the AWS Management Console
- Interact with Amazon Bedrock
- Create Knowledge Bases
- Manage S3 resources for AI applications
- Use AWS CLI or SDK programmatically

> Using an IAM user instead of the root account follows AWS security best practices and helps protect your AWS environment.

**⚠️ Warning**:
Do not use the AWS root account for daily operations or application development.Using the root account for Amazon Bedrock, Knowledge Bases, or API access can increase security risks if the credentials are exposed. Always create dedicated IAM users or IAM roles with limited permissions.

**🔒 Security Note**:

After creating the IAM user:

- Store the Access Key ID and Secret Access Key securely
- Never hardcode credentials inside source code repositories
- Enable Multi-Factor Authentication (MFA)
- Rotate access keys regularly
- Follow the principle of least privilege

Recommended AWS managed policies for Amazon Bedrock environments:

```text
AmazonBedrockFullAccess
AmazonS3FullAccess
IAMReadOnlyAccess
```

#### Main Topics in This Section:

* Create a new IAM user
* Attach permissions for Amazon Bedrock
* Generate Access Key ID and Secret Access Key
* IAM user Sgin in