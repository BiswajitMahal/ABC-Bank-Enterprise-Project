# Real Production Incident

## Network Segmentation Failure

A company placed development systems and production databases inside the same subnet.

One developer workstation was compromised through phishing.

The attacker later moved laterally across the network and reached production database systems.

### Root Cause

* No subnet isolation
* Weak network segmentation
* Excessive internal access

### Resolution

* Separate workloads into dedicated subnets.
* Apply NSGs.
* Restrict east-west traffic.
* Implement Zero Trust networking principles.

---
