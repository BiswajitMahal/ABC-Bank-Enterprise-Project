# Chapter 0.4 – CIDR, Subnet Mask and IP Planning

## Objective

Understand why IP planning is required in enterprise environments and how CIDR helps organize large networks efficiently.

---

# Business Scenario

ABC Bank is migrating its infrastructure to Microsoft Azure.

Initially, the company had only a few servers.

As the business grew, the infrastructure expanded to:

* Web Servers
* Application Servers
* Database Servers
* Jump Servers
* Monitoring Servers
* Backup Servers
* Development Virtual Machines
* Test Virtual Machines

Managing IP addresses manually became impossible.

A structured IP addressing strategy was required.

---

# The Problem

Suppose an organization has 1,000 Virtual Machines.

Assigning IP addresses manually like this is not practical:

VM1 → 10.0.0.1

VM2 → 10.0.0.2

VM3 → 10.0.0.3

...

VM1000 → ?

As infrastructure grows, manual management becomes difficult and error-prone.

---

# What is CIDR?

CIDR stands for:

**Classless Inter-Domain Routing**

CIDR is a method of representing an entire IP network using a compact notation.

Example:

10.0.0.0/24

Here:

* **10.0.0.0** represents the Network Address.
* **/24** represents the network prefix length.

CIDR helps define how large or small a network is.

---

# Understanding the CIDR Format

Example:

10.0.0.0/24

* Network Address: 10.0.0.0
* Prefix Length: /24

CIDR determines:

* Network Portion
* Host Portion

This makes network planning flexible and scalable.

---

# Enterprise Example

ABC Bank plans its Azure Virtual Network as follows:

Azure Virtual Network

10.0.0.0/16

Inside the VNet:

Web Subnet

10.0.1.0/24

Application Subnet

10.0.2.0/24

Database Subnet

10.0.3.0/24

Azure Bastion Subnet

10.0.4.0/24

Each workload is isolated into its own subnet.

---

# Why IP Planning Matters

Proper IP planning helps organizations:

* Avoid IP exhaustion
* Separate workloads
* Improve security
* Simplify troubleshooting
* Support future expansion
* Reduce redesign efforts

A well-designed network can grow without major architectural changes.

---

# Production Best Practices

✔ Plan IP ranges before creating Azure resources.

✔ Keep Development, Test, and Production networks separate.

✔ Place Databases in dedicated subnets.

✔ Reserve additional address space for future growth.

✔ Never design networks only for today's requirements.

---

# Key Learnings

* CIDR represents an IP network.
* CIDR simplifies network planning.
* Good IP planning reduces future operational risk.
* Enterprise networks are divided into multiple subnets based on workload.

---

# Practice Exercises

## Exercise 1

Run the following command:

Windows

ipconfig

Observe:

* IPv4 Address
* Default Gateway

---

## Exercise 2

Ping Google's Public DNS:

ping 8.8.8.8

Observe:

* Response Time
* Packet Loss

---

## Exercise 3

Ping Google's Domain Name:

ping google.com

Question:

Why does this command work even though you entered a domain name instead of an IP address?

(Hint: Think about the previous DNS chapter.)

---

# Summary

CIDR is the foundation of enterprise network design.

Before creating Azure Virtual Networks, cloud engineers must plan address spaces carefully to ensure scalability, security, and long-term maintainability.

Good IP planning prevents future redesigns and supports production-grade cloud architectures.
