---
title: "Building an AI gateway to Amazon Bedrock with Amazon API Gateway"
date: 2024-01-01
weight: 1
chapter: false
---

    
# Building an AI gateway to Amazon Bedrock with Amazon API Gateway

### Overview
This architecture creates an AI Gateway in front of Amazon Bedrock using Amazon API Gateway and AWS Lambda. The gateway acts as a centralized entry point for AI requests, providing security, authorization, request management, and routing capabilities before forwarding requests to Amazon Bedrock.

The architecture allows client applications to interact with Amazon Bedrock APIs transparently while the gateway handles authentication, quota management, logging, and other enterprise requirements behind the scenes.
### Architecture Flow

![AI Gateway](/static/images/aigateway.png)

### Content

1.  [Introduction](1-Introduction/)
2.  [Preparetion](2-Preparetion/)
3.  [Create an IAM user for Amazon Bedrock](3-Amazonbedrock/)
4.  [Create a Knowledge base on Amazon Bedrock](4-Knowledgebase/)
5.  [Deploying with AWS CloudFormation](5-Launchstack/)
6.  [Run Application on VS Code](6-Runapplication/)
7.  [Testing the deployment](7-Testdeployment/)
8.  [Configuring Authorization](8-Configuringauthorization/)
9.  [Clean up Resources and Costs](9-Cleanupresourcesandcosts/)
