# Chapter 0.3 – IP Address (Foundation of Networking)

## Objective

Understand what an IP Address is, why it is required, and how Public and Private IP addresses are used in enterprise cloud environments.

---

# Business Scenario

ABC Bank is deploying its Internet Banking application on Microsoft Azure.

The DNS server has already translated the domain name:

[www.abcbank.com](http://www.abcbank.com)

↓

20.45.10.120

Now the browser must communicate with that IP address.

This chapter explains what an IP Address is and why it is essential for networking.

---

# What is an IP Address?

An IP (Internet Protocol) Address is a unique logical address assigned to a device connected to a network.

It allows devices to identify and communicate with each other.

Without an IP Address, devices cannot exchange data over a network.

---

# Real Life Analogy

Just as every house has a postal address for receiving letters and parcels, every device on a network requires an IP Address to receive data.

House Address

↓

Courier Delivery

Computer IP Address

↓

Network Communication

---

# IPv4 Address

The most commonly used IP format is IPv4.

Example:

192.168.1.10

An IPv4 address consists of four numbers separated by dots.

Each number is called an **Octet**.

Each octet ranges from:

0 – 255

Example:

192 . 168 . 1 . 10

---

# Types of IP Addresses

## Public IP Address

A Public IP Address is reachable over the Internet.

Examples:

20.45.10.120

40.112.100.50

Public IPs are generally assigned to:

* Load Balancers
* Azure Firewall
* Application Gateway
* Azure Front Door
* Internet-facing services

---

## Private IP Address

A Private IP Address is used only inside a private network.

Examples:

10.0.0.4

10.1.2.5

192.168.1.10

Private IP addresses are commonly assigned to:

* Virtual Machines
* Databases
* Internal APIs
* Backend Services

Private IP addresses are not directly accessible from the Internet.

---

# Enterprise Example

ABC Bank Architecture

Internet User

↓

Public IP

↓

Azure Load Balancer

↓

Web Server (Private IP)

↓

Application Server (Private IP)

↓

Database Server (Private IP)

Only the entry point is exposed to the Internet.

Backend systems remain isolated inside the private network.

---

# Can an Azure VM Have Both IP Addresses?

Yes.

An Azure Virtual Machine can have:

* Private IP (Recommended)
* Public IP (Optional)

Production environments generally avoid assigning Public IP addresses directly to Virtual Machines.

Instead, access is provided through:

* Azure Bastion
* Azure Load Balancer
* Azure Application Gateway
* Azure Firewall
* NAT Gateway

---

# Production Best Practices

✔ Use Private IPs for backend workloads.

✔ Minimize the use of Public IP addresses.

✔ Protect Internet-facing services using firewalls and security controls.

✔ Never expose databases directly to the Internet.

✔ Use network segmentation for security.

---

# Key Learnings

* Every network device requires a unique IP Address.
* Public IPs are Internet reachable.
* Private IPs are used within internal networks.
* Enterprise workloads should primarily use Private IPs.
* Public exposure should always be minimized.

---

# Summary

An IP Address is the identity of a device on a network.

In enterprise Azure environments, Public IPs are typically assigned only to entry points, while application servers, databases, and internal services communicate using Private IP addresses to improve security and maintain proper network isolation.
