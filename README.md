#  AWS VPC Network Access Control Lists (NACLs) Lab


## Introduction

### What is Amazon VPC?
Amazon Virtual Private Cloud (VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have full control over your virtual networking environment including IP address ranges, subnets, route tables, and network gateways.

### What are Network Access Control Lists (NACLs)?
NACLs are an optional layer of security for your VPC that act as a **stateless firewall** for controlling traffic in and out of one or more **subnets**. Unlike Security Groups (which operate at the instance level), NACLs operate at the **subnet level**, providing a broader net of traffic control.

### Why NACLs Matter
- Provide an **additional layer of defense** beyond Security Groups
- Allow you to **explicitly deny** specific IP ranges or ports
- Are **stateless** - return traffic must be explicitly allowed
- Evaluated in **rule number order**, with the first matching rule applied

---

## Lab Objectives

- Create a custom **VPC** with public and private subnets
- Launch **EC2 instances** in both subnet types
- Create and configure a **custom NACL**
- Define and test **inbound and outbound rules**
- Observe how NACL rules affect connectivity to the instances

---

##  Architecture of Lab

The lab environment consists of:
- 1 Custom VPC
- 1 Public Subnet + 1 Private Subnet
- 1 Internet Gateway
- 2 Route Tables (public & private)
- 2 EC2 Instances (one in each subnet)
- 1 Custom NACL (MyPublicNACL) associated with the public subnet

---

## Lab Tasks

| 1 | Sign into the AWS Management Console |
| 2 | Create a New VPC |
| 3 | Create Public and Private Subnets |
| 4 | Create and Attach an Internet Gateway |
| 5 | Create Route Tables and Associate with Subnets |
| 6 | Update Route Table to Configure the Internet Gateway |
| 7 | Enable Auto-Assign Public IP for the Public Subnet |
| 8 | Launch an EC2 Instance in the Public Subnet |
| 9 | Launch an EC2 Instance in the Private Subnet |
| 10 | Test Connectivity on Both EC2 Instances |
| 11 | Create a Custom NACL and Associate it with the Subnet |
| 12 | Test Public and Private Server After NACL Association |
| 13 | Add Inbound/Outbound Rules to the Custom NACL |
| 14 | Re-test Both EC2 Instances |


---

## Screenshots

Screenshots from each major step of the lab are included in this repository. They document the AWS Console configuration at each stage, including VPC creation, subnet setup, NACL rule configuration, and connectivity testing.

---

## Key Concepts Covered

- **VPC**: Isolated virtual network in AWS
- **Subnets**: Subdivisions of a VPC (public vs. private)
- **Internet Gateway** : Enables internet access for public subnets
- **Route Tables** : Direct traffic between subnets and the internet
- **NACLs** : Stateless subnet-level firewall rules
- **Security Groups** : Stateful instance-level firewall (complementary to NACLs)
- **EC2** : Virtual servers launched within the VPC

---

## Learning Outcomes

After completing this lab, i was able to:

  - Create and configure a custom VPC from scratch
  - Understand the difference between NACLs and Security Groups
  - Write and order NACL inbound and outbound rules correctly
  - Troubleshoot connectivity issues caused by NACL misconfigurations
  - Appreciate the role of stateless vs. stateful firewalls in AWS networking

---




## AWS Region

**US East (N. Virginia) - `us-east-1`**

---

## Notes

- NACLs are **stateless**: you must explicitly allow both inbound and outbound traffic for a connection to work.
- Rules are evaluated **in ascending order** by rule number - the first match wins.
- Rule number **`*` (asterisk)** is the default deny-all rule and cannot be modified.
- Always test your NACL changes - a misconfigured rule can cut off access to your instances.

---

## Acknowledgements

This lab was completed as part of a hands-on AWS networking learning journey. Special thanks to Whizlab for making this exercise possible.

---

> **Author:** *Angela Achiaa Osei*  
> **Date Completed:** *May 2026*  
> **Certification Goal:** *AWS Solutions Architect / Cloud Practitioner*
