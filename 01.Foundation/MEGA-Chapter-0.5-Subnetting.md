# MEGA Chapter 0.6 – Subnetting Masterclass

## Part 1 – Why Subnetting?

## Objective

Understand why subnetting is required in enterprise environments before learning subnet calculations.

This chapter focuses on the business problem that subnetting solves.

---

# Business Scenario

ABC Bank is migrating its infrastructure from an on-premises data center to Microsoft Azure.

Initially, the company had only a few servers.

As the business expanded, the infrastructure grew significantly.

Current infrastructure includes:

* Web Servers
* Application Servers
* Database Servers
* Azure Bastion
* Monitoring Servers
* Backup Servers
* Developer Virtual Machines
* Testing Virtual Machines
* AKS Cluster Nodes

More than 500 systems now communicate over the network.

The cloud engineering team must design a secure and scalable network.

---

# The Problem

The management proposes keeping every server inside one large network.

Example:

10.0.0.0/16

↓

* Web Server
* Application Server
* Database Server
* Bastion
* Monitoring
* Backup
* Developer VM
* AKS Cluster

Everything exists in one network.

At first, this seems simple.

However, this design creates multiple production problems.

---

# Problem 1 – Security

Suppose a Developer Virtual Machine is compromised.

If all systems exist in the same network, an attacker may attempt to reach:

* Database Servers
* Storage Accounts
* Internal APIs
* Backup Systems

Without proper network segmentation, the attack surface becomes significantly larger.

---

# Problem 2 – Broadcast Traffic

Large networks generate more broadcast traffic.

As the number of connected devices increases:

* Network congestion increases.
* Performance decreases.
* Troubleshooting becomes more difficult.

Keeping thousands of devices inside a single network is inefficient.

---

# Problem 3 – Troubleshooting

Suppose the database becomes unreachable.

If every workload exists inside one large network:

* Identifying traffic flow becomes difficult.
* Packet tracing becomes complex.
* Root cause analysis takes longer.

Well-organized networks simplify troubleshooting.

---

# Problem 4 – Compliance

Banking organizations must comply with security standards.

Examples include:

* PCI DSS
* ISO 27001
* RBI Security Guidelines

Sensitive workloads such as databases should never share the same network segment as development systems.

Network isolation is an important compliance requirement.

---

# The Solution

Instead of using one large network, engineers divide it into multiple smaller logical networks.

This process is called:

# Subnetting

Subnetting means dividing one large network into multiple smaller networks based on workload and business requirements.

---

# Real Life Analogy

Imagine a large apartment complex.

Apartment Complex

↓

Tower A

Tower B

Tower C

Tower D

The apartment complex represents the network.

Each tower represents a subnet.

Each apartment inside the tower represents a host.

This organization improves security and management.

---

# Enterprise Network Design

Instead of placing every workload inside one network:

10.0.0.0/16

The Azure network is divided into dedicated subnets.

Example:

Web Subnet

10.0.1.0/24

Application Subnet

10.0.2.0/24

Database Subnet

10.0.3.0/24

Azure Bastion Subnet

10.0.4.0/26

Monitoring Subnet

10.0.5.0/24

AKS Subnet

10.0.6.0/22

Each workload is isolated from the others.

This improves both security and scalability.

---

# Azure Perspective

When creating a Virtual Network (VNet) in Azure, engineers normally create multiple subnets.

Typical enterprise subnet layout:

* Web Subnet
* Application Subnet
* Database Subnet
* Bastion Subnet
* Firewall Subnet
* Monitoring Subnet
* AKS Subnet

This architecture follows Microsoft cloud networking best practices.

---

# Production Best Practices

✔ Separate application tiers into different subnets.

✔ Keep databases isolated.

✔ Deploy Azure Bastion in its dedicated subnet.

✔ Reserve address space for future expansion.

✔ Never design networks only for current requirements.

✔ Apply Network Security Groups (NSGs) at the subnet level where appropriate.

---



# Key Learnings

* Subnetting divides one large network into smaller logical networks.
* Network segmentation improves security.
* Smaller subnets simplify troubleshooting.
* Enterprise cloud environments always use multiple subnets.
* Good subnet planning supports future scalability.

---

# Practice Questions

1. Why is subnetting required?
2. What problems occur if every server is placed inside one network?
3. Why should databases use separate subnets?
4. How does subnetting improve security?
5. Why is subnet planning performed before deploying Azure resources?

---

# Mini Quiz

### Question 1

What is subnetting?

---

### Question 2

True or False:

Keeping every workload inside one subnet is a production best practice.

---

### Question 3

Which workload should normally have its own dedicated subnet?

* Database
* Azure Bastion
* Web Servers
* All of the above

---

# Summary

Subnetting is one of the most important concepts in cloud networking.

Instead of creating one large network, enterprise organizations divide infrastructure into multiple logical subnets based on workload, security, scalability, and compliance requirements.

Every Azure production environment follows this design principle.

This understanding forms the foundation for Azure Virtual Networks, Network Security Groups, Azure Firewall, Private Endpoints, and enterprise landing zones.

---

# Next Part

In the next section of this Mega Chapter, we will learn:

* Network Address
* Broadcast Address
* Host Address

These concepts are essential before performing subnet calculations and designing enterprise Azure networks.
