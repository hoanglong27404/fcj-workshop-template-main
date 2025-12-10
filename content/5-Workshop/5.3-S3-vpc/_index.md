---
title : "Deploy Backend"
date: 2025-10-13
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

## Introduction to Infrastructure as Code (IaC)

Instead of manually clicking through the AWS Console ("ClickOps"), we use **AWS CDK** to define our entire infrastructure. In the file `cdk/lib/backend-stack.ts`, we have designed a complete Serverless system.

When you run the `cdk deploy` command, CDK synthesizes this code into a CloudFormation Template, and AWS automatically provisions the corresponding resources.

## Architecture

![FindNest Architecture](/images/5-Workshop/5.1-Workshop-overview/AWSProject.png)

## Content

1. [Architecture Deep Dive](5.3.1-architecture/) - Detailed code walkthrough of all AWS resources
2. [Install Dependencies](5.3.2-dependencies/) - Setting up the development environment
3. [Deploy Stack](5.3.3-deploy/) - Running CDK commands to provision infrastructure
4. [Results & Outputs](5.3.4-results/) - Understanding deployment outputs and next steps