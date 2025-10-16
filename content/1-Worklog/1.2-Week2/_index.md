---
title: "Week 2 Worklog"
date: 2025-10-13
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

This week's focus was on establishing hybrid connectivity between on-premises systems and AWS. The key goals were:

- **Set up Hybrid DNS**: Use Route 53 Resolver to allow on-premises servers to resolve DNS queries for services hosted in AWS, and vice-versa.
- **Establish VPC Peering**: Create a direct network connection between two VPCs (Dev and Staging) to allow them to communicate using private IP addresses.
- **Deploy AWS Transit Gateway**: Implement a centralized hub to simplify network connectivity and routing between multiple VPCs and on-premises networks.
- **Automate with CloudFormation**: Practice infrastructure-as-code by using CloudFormation templates to provision the required resources automatically.
- **Plan Final Project**: Brainstorm and outline the architecture for the final semester project, applying the concepts learned during the week.

---

### Tasks Overview

| Day | Task                                                                                                                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                  |
| :-: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------: | :-------------: | ----------------------------------- |
|  2  | **Configure Hybrid DNS with Route 53 Resolver**:<br>- Generate Key Pair<br>- Initialize CloudFormation Template<br>- Configure Security Group<br>- Connect to RDGW<br>- Configure DNS<br> + Create Outbound Endpoint<br> + Create Resolver Rules<br> + Create Inbound Endpoint<br>- Clean up resources | 09/15/2025 |   09/15/2025    | AWS Study Group<br>YouTube Playlist |
|  3  | **Review Key Concepts**:<br>- Hybrid DNS<br>- RDGW<br>- Route 53 Endpoints<br>- Resolver Rules                                                                                                                                                                                                         | 09/16/2025 |   09/16/2025    | Same sources                        |
|  4  | **Configure VPC Peering**:<br>- Introduction to Peering<br>- Initialize CloudFormation Template<br>- Create Security Group & EC2 instance<br>- Update Network ACLs<br> + Establish Peering Connection<br> + Update Route Tables<br>- Enable Cross-Peer DNS                                             | 09/17/2025 |   09/17/2025    | Same sources                        |
|  5  | **Deploy AWS Transit Gateway**:<br>- Create Transit Gateway<br>- Create Attachments for each VPC<br>- Configure Transit Gateway Route Tables<br>- Add Routes to VPC Route Tables                                                                                                                       | 09/18/2025 |   09/18/2025    | Same sources                        |
|  6  | **Final Project Planning**:<br>- Research potential solutions<br>- Brainstorm and develop core ideas<br>- Outline a preliminary architecture                                                                                                                                                           | 09/19/2025 |   09/19/2025    | Same sources                        |

---

### Week 2 Achievements

#### What was accomplished

- Successfully simulated **Hybrid DNS** connectivity between an on-premises environment and AWS.
- Implemented **VPC Peering** to link the Development (Dev) and Staging environments, enabling secure, private communication.
- Deployed an **AWS Transit Gateway** to serve as a central hub for managing network traffic between multiple VPCs.
- Practiced infrastructure-as-code by automating resource deployment with **AWS CloudFormation**.
- Developed a concrete idea and architecture for the final project based on practical experience with AWS networking services.

#### Architecture Summary

- **Multi-region Connectivity**: Established a connection between a Dev VPC in `us-east-1` and a Prod VPC in `ap-southeast-1` using a Transit Gateway.
- **Hybrid DNS Resolution**: Configured the system so that a local domain (`app.company.local`) on-premises can successfully resolve an AWS-hosted domain (`analytics.aws.company.com`).
