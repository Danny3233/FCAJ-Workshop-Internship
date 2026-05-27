---
title: "Introduction"
date: 2026-05-14T13:38:56+07:00
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

### Amazon Route 53

Amazon Route 53 manages custom domain routing, allowing applications to access the AI Gateway through a company-specific domain instead of the default API Gateway endpoint.

### Amazon API Gateway

Amazon API Gateway serves as the main entry point for requests and provides features such as:

- Request routing
- API lifecycle management
- Rate limiting and throttling
- Monitoring and logging
- Authorization integration

### Lambda Authorizer

The Lambda Authorizer validates incoming requests before they reach Amazon Bedrock. Common authorization methods include:

- JWT token validation
- Amazon Cognito integration
- OAuth 2.0
- Custom authentication logic

### Lambda Integration Proxy

The Lambda Integration function dynamically forwards requests to Amazon Bedrock while preserving the original API structure. It signs requests using AWS credentials and supports multiple Bedrock APIs without requiring client-side changes.

### Amazon Bedrock
Amazon Bedrock provides access to foundation models and AI capabilities such as:

- Large Language Models (LLMs)
- Knowledge Bases
- Retrieval-Augmented Generation (RAG)
- AI Agents
- Guardrails

Let’s get started by setting up the preparetion in next step!