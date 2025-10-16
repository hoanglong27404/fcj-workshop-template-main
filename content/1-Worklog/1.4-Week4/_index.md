---
title: "Week 4 Worklog"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives: System Optimization

This week was centered on applying the AWS Well-Architected Framework to comprehensively optimize the system across its five core pillars:
-   **Operational Excellence**: Automating operations, implementing proactive monitoring, and establishing efficient incident response procedures.
-   **Security**: Building a security architecture based on zero-trust principles, ensuring compliance, and protecting the system against threats.
-   **Reliability**: Ensuring high availability, developing a robust disaster recovery plan, and enhancing fault tolerance.
-   **Performance Efficiency**: Improving performance through auto-scaling, caching techniques, and optimizing resources across container and storage services.
-   **Cost Optimization**: Right-sizing resources, utilizing savings plans, and leveraging detailed spending analysis tools.

---
### Tasks Overview

| Day | Task                                                                                                                                                                                                                                                                                    | Start Date | Completion Date | Reference Material                                                                                                                              |
|:---:| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |:----------:|:---------------:| ----------------------------------------------------------------------------------------------------------------------------------------------- |
|  2  | **Operational Excellence**:<br>- Automating tasks (server shutdown, Slack notifications) with AWS Lambda<br>- Building a monitoring dashboard with CloudWatch and Grafana<br>- Managing resources and EC2 access permissions based on Tags<br>- Automating management and operations with AWS Systems Manager<br>- Implementing Infrastructure as Code (IaC) with AWS CloudFormation | 09/29/2025 | 09/29/2025      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/)<br>[https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
|  3  | **Security**:<br>- Setting up Single Sign-On (SSO) for the organization<br>- Limiting maximum user permissions with IAM Permission Boundaries<br>- Auditing security standards with AWS Security Hub<br>- Protecting web applications and APIs with AWS WAF<br>- Managing encryption keys centrally with AWS KMS | 09/30/2025 | 09/30/2025      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/)<br>[https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
|  4  | **Reliability**:<br>- Developing a system backup and recovery strategy with AWS Backup<br>- Establishing direct connections between VPCs using VPC Peering<br>- Centrally managing network connectivity with AWS Transit Gateway for enhanced stability                               | 10/01/2025 | 10/01/2025      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/)<br>[https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
|  5  | **Performance Efficiency**:<br>- Containerizing applications with Docker and deploying on Amazon ECS<br>- Building an automated CI/CD pipeline with AWS CodePipeline<br>- Implementing unlimited file storage with AWS File Storage Gateway<br>- Deploying a shared file system for Windows with Amazon FSx<br>- Building a Data Lake and designing an advanced architecture with DynamoDB | 10/02/2025 | 10/02/2025      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/)<br>[https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
|  6  | **Cost Optimization**:<br>- Optimizing expenses with Savings Plans and Reserved Instances<br>- Right-sizing EC2 configurations<br>- Visualizing AWS service usage costs<br>- Performing in-depth cost analysis with AWS Glue and Amazon Athena<br>- Reviewing and consolidating the 5 pillars of the Well-Architected Framework | 10/03/2025 | 10/03/2025      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/)<br>[https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |

---
### Week 4 Achievements

#### What was accomplished

-   **Automated Operations & Monitoring**: Finalized automated server shutdown processes, built performance monitoring dashboards with CloudWatch/Grafana, and centralized resource management using Tags.
-   **Comprehensive Security Hardening**: Successfully configured SSO, applied IAM Permission Boundaries for strict access control, deployed a Web Application Firewall (WAF), and managed encryption with KMS.
-   **Enhanced System Reliability**: Implemented an automated backup plan with AWS Backup and configured VPC Peering and Transit Gateway to ensure stable and resilient network connectivity.
-   **Application Performance Optimization**: Deployed containerized applications via Docker/ECS, automated the CI/CD pipeline with CodePipeline, and designed high-performance data architectures with DynamoDB and a Data Lake.
-   **Effective Cost Management**: Successfully applied Savings Plans/Reserved Instances, performed EC2 right-sizing, and utilized Glue/Athena for advanced, granular cost analysis.