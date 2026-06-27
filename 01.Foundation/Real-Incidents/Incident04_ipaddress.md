# Real Production Incident

## Public VM Exposure

A development Virtual Machine was temporarily assigned a Public IP address for testing.

After testing, the Public IP was not removed.

Automated Internet bots continuously scanned the exposed SSH port.

A weak administrator password was eventually compromised, allowing unauthorized access.

### Root Cause

* Public IP left enabled
* Weak authentication
* Lack of network restrictions

### Resolution

* Remove unnecessary Public IPs
* Use Azure Bastion for administration
* Restrict inbound access using NSGs
* Enable Multi-Factor Authentication
* Monitor login attempts

---
