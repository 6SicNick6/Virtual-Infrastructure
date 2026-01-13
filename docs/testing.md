# Testing and Validation

## Phase 1 – Baseline Infrastructure

### Tests Performed
- Deployed all virtual machines
- Installed operating system updates
- Installed VMware Tools on all VMs
- Verified DHCP network connectivity
- Created clean snapshots for rollback

### Results
- All VMs deployed successfully
- Network connectivity established
- Baseline snapshots available

---

## Phase 2 – Active Directory and DNS

### Tests Performed
- Installed Active Directory Domain Services on DC01
- Promoted DC01 to Domain Controller
- Created vmware.lab forest
- Verified DNS functionality
- Tested domain authentication from MGMT01

### Results
- Active Directory services operational
- DNS resolving domain and hostnames correctly
- Domain authentication validated

---

## Phase 3 – Windows File Services (Including Linux Client Validation)

### Tests Performed
- Installed and configured the Windows File Server role on FS01
- Created Active Directory security groups for file access control
- Applied NTFS and share permissions using AD security groups
- Verified file share access from Windows management workstation
- Configured Linux system to use Active Directory DNS
- Installed SMB client utilities on Linux
- Authenticated to Windows file share from Linux using domain credentials

### Results
- Windows file services configured according to enterprise best practices
- NTFS and share permissions enforced through Active Directory groups
- Linux systems successfully resolved domain resources
- Read/write access to Windows file shares validated from Linux clients

---

## Phase 4 – Linux Identity and Privilege Integration

### Tests Performed
- Verified Active Directory authentication from Linux using SSSD
- Confirmed AD user and group resolution on Linux
- Validated AD-based sudo access via Linux-Sudo group
- Confirmed cross-platform identity consistency between Linux and Windows systems

### Results
- Linux systems successfully authenticate against vmware.lab Active Directory
- Privilege escalation controlled using AD group membership
- Linux hosts fully integrated into enterprise identity model
- Cross-platform authentication and authorization function as designed
