# Virtual Machine Inventory – Phase 1

| VM Name | Operating System | Role | Notes |
|---------|-----------------|------|-------|
| DC01    | Windows Server  | Future Domain Controller | No roles installed yet, DHCP networking, snapshot taken |
| FS01    | Windows Server  | File Server | Baseline Windows Server installation, snapshot taken |
| MGMT01 | Windows Server  | Management / Admin Server | Used for admin tasks, snapshot taken |
| LNX01   | Linux Server (CLI-only) | Generic Linux Server | Minimal CLI-only installation, snapshot taken, firewall adjusted for ICMP |

### Notes
- All VMs are on the same DHCP network
- Baseline snapshots allow rollback to a clean OS state
- Linux is managed entirely via CLI; no GUI installed
- Joined to vmware.lab Active Directory domain
- Authentication managed via SSSD
- Privilege escalation controlled by AD group membership
