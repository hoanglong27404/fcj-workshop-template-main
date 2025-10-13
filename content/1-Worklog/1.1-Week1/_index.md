---
title: "Week 1 Worklog"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives

- Initialize and secure the first AWS account:
  - Create a new AWS account, enable MFA for the Root user
  - Create Administrator group/permissions and an admin account
  - Get support for account authentication if needed
  - Explore and configure the AWS Management Console
- Manage costs with AWS Budgets:
  - Create Cost, Usage, Reservation, and Savings Plans budgets
  - Set up alerts and resource cleanup procedures
- Overview of AWS Support (channels and service scope)
- Access management with IAM: Users, Groups, Roles, Switch Roles
- Networking with VPC:
  - VPC introduction; differences between Security Groups and Network ACLs
  - Environment preparation; deploy EC2
  - Cleanup after the lab

### Tasks to be carried out this week

<!-- markdownlint-disable MD033 -->

| Day | Task                                                                                                                                                        | Start Date | Completion Date | Reference Material                                                                                                                |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | Create a new AWS account:<br>- Enable Root MFA<br>+ Create Administrator group/permissions<br>+ Create admin account<br>- Explore and configure the Console | 09/08/2025 | 09/08/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | Set up AWS Budgets:<br>- Cost Budget<br>+ Usage Budget<br>+ Reservation Budget<br>+ Savings Plans Budget<br>- Configure alerts<br>- Review cleanup process  | 09/09/2025 | 09/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | IAM:<br>- Create Users and Groups<br>+ Attach policies<br>+ Create Roles<br>- Practice Switch Role<br>- Apply least privilege                               | 09/10/2025 | 09/10/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | VPC:<br>- Overview<br>+ Compare Security Groups vs NACLs<br>- Prepare networking environment for the lab                                                    | 09/11/2025 | 09/11/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | EC2:<br>- Deploy EC2 in a subnet<br>+ Configure Security Group<br>- Resource cleanup                                                                        | 09/12/2025 | 09/12/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

<!-- markdownlint-enable MD033 -->

### Week 1 Achievements

#### What was accomplished

- Created AWS account with $100 free credit and set up MFA security
- Created dedicated IAM user to avoid using Root account during practice
- Set up $50/month budget with automatic alerts for learning cost control
- Mastered IAM permissions and practiced Switch Role between environments
- Understood basic VPC architecture and resource protection with Security Groups
- Successfully deployed first EC2 instance and SSH connection
- Understood VPC architecture and the differences between Security Groups and Network ACLs; prepared the networking environment for the lab.
- Deployed EC2 in a subnet, configured Security Groups and key pair.
