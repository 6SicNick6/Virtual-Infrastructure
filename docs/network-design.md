# Network Design – Phase 1

## Overview
This document outlines the network configuration and validation steps for Phase 1 of the VMware lab. The environment operates under lab-imposed constraints.

## Network Topology
- Single VMware-provided virtual network
- DHCP used for all VMs
- No static IP addresses permitted
- No DNS configured in Phase 1

### Connectivity Validation
- All VMs can ping each other **using IP addresses**
- Windows firewall configured to allow ICMP (ping)
- Linux firewall rules reviewed; ICMP allowed
- Hostname resolution is deferred until DNS is deployed

## Constraints and Considerations
- Limited to DHCP due to lab restrictions
- Single network requires careful VM planning for future domain services
- Current setup is sufficient for baseline validation and portfolio documentation
