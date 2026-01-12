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

### Results

* Active Directory services operational
* DNS resolving domain and hostnames correctly
* DHCP-related warning identified, documented, and accepted due to lab constraints

### MGMT01 Domain Join Validation

* Configured MGMT01 to use DC01 as its primary DNS server
* Successfully joined MGMT01 to the `vmware.lab` Active Directory domain
* Verified domain membership via System Properties
* Confirmed domain authentication using `VMWARE\Administrator` credentials

**Result:** MGMT01 is fully integrated into the domain and ready for administrative and management tasks.

### Configuration Adjustment

During Phase 2 validation, DC01 was assigned a static IP address to improve DNS reliability and domain join consistency.  
Post-change validation confirmed continued Active Directory and DNS functionality across all domain-joined systems.

## Phase 3A – File Services Validation

### Tests Performed
- Created AD security groups for file access
- Configured NTFS permissions on FS01
- Configured SMB share permissions
- Validated access from MGMT01 using a standard domain user

### Results
- File share accessible as designed
- Read/write access correctly enforced via group membership
- Administrative privileges not required for access

## Phase 3B – Linux Integration Validation

### Tests Performed
- Configured Linux DNS to use Active Directory DNS
- Verified forward DNS resolution for domain hosts
- Installed SMB client tools
- Authenticated to Windows file share using domain credentials

### Results
- Linux successfully resolved domain resources
- SMB authentication against Active Directory succeeded
- Read/write access to Windows file share validated from Linux

## Phase 4 – Linux Integration Validation

### Tests Performed
- Verified Active Directory authentication from Linux using SSSD
- Confirmed AD group resolution and user identity mapping
- Validated AD-based sudo access via Linux-Sudo group
- Tested SMB access from Linux to Windows file server using AD credentials

### Results
- Linux successfully authenticates against vmware.lab Active Directory
- Privilege escalation controlled through AD group membership
- Linux users can access Windows SMB shares with correct NTFS permissions
- Cross-platform identity and access model functions as designed

