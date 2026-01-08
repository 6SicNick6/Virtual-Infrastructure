# Phase 1 - Testing and Validation

## Overview
This document captures all validation steps performed during Phase 1 of the VMware lab. Testing ensures that all VMs are operational and network connectivity is functional.

## Steps Performed
1. **IP Address Verification**
   - Windows: `ipconfig /all`
   - Linux: `hostname -I`
   - Confirmed all VMs received DHCP-assigned addresses in the same subnet

2. **Connectivity Tests**
   - Pinging between all VMs using IP addresses
   - Windows firewall rules updated to allow ICMP (ping)
   - Linux firewall verified; ICMP allowed

3. **VMware Tools Verification**
   - Checked VMware Tools installation status on all VMs

4. **Snapshot Verification**
   - Confirmed baseline snapshots exist: “Clean OS + VMware Tools”

## Notes
- Hostname-based ping is not functional due to the absence of DNS services
- All connectivity testing is based on IP addresses
- Evidence of testing is captured in the `screenshots/` directory

## Phase 2 – Active Directory and DNS Validation

### Tests Performed

* Verified DC01 promotion to Domain Controller
* Confirmed DNS service installation
* Tested forward DNS resolution using `nslookup`
* Verified successful login using domain credentials

### MGMT01 Domain Join Validation

* Configured MGMT01 to use DC01 as its primary DNS server
* Successfully joined MGMT01 to the `vmware.lab` Active Directory domain
* Verified domain membership via System Properties
* Confirmed domain authentication using `VMWARE\Administrator` credentials

**Result:** MGMT01 is fully integrated into the domain and ready for administrative and management tasks.


### Results

* Active Directory services operational
* DNS resolving domain and hostnames correctly
* Known DHCP-related warning documented and accepted
