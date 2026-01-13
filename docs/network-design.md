# Network Design

## Overview
The lab operates within a constrained networking model provided by a shared enterprise VMware environment.

---

## Network Characteristics
- Single virtual network
- DHCP-assigned IP addresses
- No control over upstream routing or switching
- No VLAN segmentation available

---

## DNS Strategy
- DC01 provides DNS services for the vmware.lab domain
- All domain-joined systems use DC01 as their primary DNS server
- Linux DNS resolution is configured to use Active Directory DNS

---

## Design Considerations
- DHCP was used to comply with lab constraints
- DNS reliability was prioritized over static IP usage
- Name resolution validation was performed from all systems
