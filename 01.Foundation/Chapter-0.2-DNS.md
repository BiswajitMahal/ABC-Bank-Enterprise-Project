# Chapter 0.2 – DNS (Domain Name System)

## Objective

Understand how a browser finds the IP address of a website before connecting to an application hosted in Azure.

---

## The Problem

A user types:

[www.abcbank.com](http://www.abcbank.com)

The browser cannot communicate using domain names.

It needs an IP address.

---

## What is DNS?

DNS (Domain Name System) translates a domain name into an IP address.

Example:

[www.abcbank.com](http://www.abcbank.com)

↓

20.45.10.120

---

## DNS Resolution Flow

User

↓

Browser

↓

DNS Server

↓

IP Address Returned

↓

Azure Application

---

## Why DNS Exists

Humans can easily remember names.

Computers communicate using IP addresses.

DNS acts as the translator between the two.

---

## DNS Cache

Browsers and operating systems temporarily store DNS results.

Benefits:

* Faster Website Loading
* Reduced DNS Queries
* Lower Latency

---

## TTL (Time To Live)

TTL defines how long a DNS record remains cached before a new lookup is performed.

Lower TTL allows faster DNS updates during migrations.

Higher TTL reduces DNS traffic.

---

## Production Best Practice

Applications should always communicate using DNS names rather than hardcoded IP addresses.

This allows infrastructure changes without modifying application configuration.

---

## Real Production Scenario

A company migrated its application to a new server.

The DNS record was updated.

Some users continued reaching the old server because their systems still had cached DNS records.

After the TTL expired (or the DNS cache was cleared), all users automatically reached the new server.

---

## Key Learnings

* DNS converts domain names into IP addresses.
* DNS Cache improves performance.
* TTL controls cache duration.
* DNS enables infrastructure flexibility.

---

## Summary

Without DNS, users would need to remember IP addresses for every website. DNS is one of the most fundamental services used in cloud networking.
