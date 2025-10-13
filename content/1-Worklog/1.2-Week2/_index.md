---
title: "Week 2 Worklog"
date: 2025-10-13
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

- Set up Hybrid DNS with Route 53 Resolver (intro, architecture, components).
- Hands-on: generate Key Pair, initialize a CloudFormation template, configure Security Group.
- Connect to RDGW, set up DNS, create Outbound/Inbound Endpoints and Resolver Rules.
- Clean up resources after the lab.

### Tasks to be carried out this week

<!-- markdownlint-disable MD033 -->

| Day | Task                                                                                                                                                                                                                                                                                                                  | Start Date | Completion Date | Reference Material                                                                                                                |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | Set up Hybrid DNS with Route 53 Resolver:<br>- Generate Key Pair<br>+ Initialize CloudFormation Template<br>+ Configure Security Group<br>- Connect to RDGW<br>- Set up DNS<br>+ Create Route 53 Outbound Endpoint<br>+ Create Route 53 Resolver Rules<br>+ Create Route 53 Inbound Endpoints<br>- Clean up resources | 09/15/2025 | 09/15/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | Review learned topics (Hybrid DNS, RDGW, DNS, Endpoints/Rules)                                                                                                                                                                                                                                                        | 09/16/2025 | 09/16/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | Set up VPC peering:<br>- Set up VPC peering (Introduction)<br>+ Initialize CloudFormation Templates<br>+ Create Security group<br>- Create EC2 instance<br>- Update Network ACL (NACLs)<br>+ Create a peering connection<br>+ Configure Route tables<br>- Enable Cross-Peer DNS                                       | 09/17/2025 | 09/17/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | Set up AWS Transit Gateway:<br>- Set up AWS Transit Gateway (Introduction)<br>+ Create Transit Gateway<br>+ Create Transit Gateway Attachments<br>- Create Transit Gateway Route Tables<br>- Add Transit Gateway Routes to VPC Route Tables                                                                           | 09/18/2025 | 09/18/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | Find solutions and brainstorm project ideas                                                                                                                                                                                                                                                                           | 09/19/2025 | 09/19/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |

<!-- markdownlint-enable MD033 -->

### Week 2 Achievements

#### What was accomplished

- Set up Hybrid DNS lab to simulate university-to-AWS connectivity
- Configured VPC Peering to connect development and staging environments
- Deployed Transit Gateway for managing multiple VPCs in large projects
- Practiced CloudFormation for infrastructure deployment automation
- Planned final semester project using learned AWS knowledge
- **Multi-region**: Dev VPC (us-east-1) connects with Prod VPC (ap-southeast-1) via Transit Gateway
- **DNS**: app.company.local (on-premises) resolves analytics.aws.company.com
