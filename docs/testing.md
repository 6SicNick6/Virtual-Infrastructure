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
* MGMT01 is fully integrated into the domain and ready for administrative and management tasks.

### Configuration Adjustment

During Phase 2 validation, DC01 was assigned a static IP address to improve DNS reliability and domain join consistency.  
Post-change validation confirmed continued Active Directory and DNS functionality across all domain-joined systems.

## Phase 3 – Windows File Services

#### Tests Performed

* Installed and configured Windows File Server role on FS01
* Created Active Directory security groups for file access control
* Applied NTFS and share permissions using AD groups
* Verified file access from Windows management workstation
* Configured Linux DNS to use Active Directory DNS
* Installed SMB client utilities on Linux
* Authenticated to Windows file share from Linux using domain credentials

#### Results

* Windows file services configured according to enterprise best practices
* NTFS and share permissions enforced through Active Directory groups
* Linux systems successfully resolved domain resources via AD DNS
* Read/write access to Windows file shares validated from Linux clients

## Phase 4 – Linux Identity and Privilege Integration

#### Tests Performed
* Verified Active Directory authentication from Linux using SSSD
* Confirmed AD user and group resolution on Linux
* Validated AD-based sudo access via Linux-Sudo group
* Confirmed cross-platform identity consistency between Linux and Windows systems

#### Results
* Linux systems successfully authenticate against vmware.lab Active Directory
* Privilege escalation is centrally controlled using AD group membership
* Linux hosts participate fully in the enterprise identity model
* Cross-platform authentication and authorization function as designed
