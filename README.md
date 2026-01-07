# VMware Virtual Infrastructure Lab

## Overview
This repository documents the design, validation, and staged build-out of a beginner-friendly, enterprise-style VMware virtual infrastructure. The lab is intended as a systems engineering portfolio project, with an emphasis on **clean architecture, operational discipline, and clear documentation** rather than ad-hoc configuration.

The environment is built incrementally under realistic constraints, with each phase validated and documented before additional services are introduced.

## Objectives
- Design and deploy a foundational VMware-based virtual infrastructure
- Demonstrate core systems administration skills across Windows and Linux
- Apply enterprise-style validation and documentation practices
- Create a reusable baseline suitable for future Active Directory and DNS deployment

## Environment Constraints
This lab is hosted in a **shared enterprise VMware environment**, which imposes the following constraints:

- Underlying host hardware is abstracted
- Physical networking is not accessible
- A single lab-provided VM network is available
- DHCP is required for all virtual machines
- Static IP addressing is not permitted

All design decisions documented in this repository reflect these constraints.

## Current State (Phase 1 – Baseline Infrastructure)

### Virtual Machines
The following virtual machines have been provisioned and validated:

| VM Name | Operating System | Role |
|---------|-----------------|------|
| DC01    | Windows Server  | Future Domain Controller |
| FS01    | Windows Server  | File Server |
| MGMT01 | Windows Server  | Administrative / Management Server |
| LNX01   | Linux Server (CLI-only) | General-purpose Linux Server |

### Common Configuration
- All VMs configured with **DHCP networking**
- OS updates installed on all machines
- **VMware Tools installed and verified**
- **Baseline snapshots** taken: “Clean OS + VMware Tools”
- Linux server installed **without GUI**, managed entirely via CLI

### Network Validation
- **IP-based connectivity verified** between all VMs  
  (Windows ↔ Windows, Windows ↔ Linux)
- Host-based firewalls on Windows were adjusted to allow ICMP (ping)
- Linux firewall rules verified; ICMP explicitly allowed for validation
- Hostname resolution is **not yet configured** due to absence of DNS services  
  Connectivity testing performed using IP addresses only

## Design Decisions
- **DHCP** is used due to lab network limitations
- A **Windows Server management host** is used instead of a Windows 10/11 client to better align with enterprise administration scenarios
- **Snapshots** are used strictly for rollback purposes, not as a backup mechanism
- Linux is managed exclusively via the command line to reflect common server deployments

## Documentation Structure
Detailed documentation is located in the `docs/` directory:

- `architecture.md` – Logical infrastructure and role layout
- `network-design.md` – Network configuration, constraints, and validation
- `vm-inventory.md` – Virtual machine inventory and roles
- `testing.md` – Validation steps, results, and deferred items

Supporting screenshots are stored in the `screenshots/` directory.

## Future Work
Planned next phases include:
- Promoting DC01 to an Active Directory Domain Controller
- Introducing centralized DNS services
- Joining Windows servers to the domain
- Registering Linux hostnames in DNS
- Expanding validation and testing documentation

Each phase will be implemented and documented incrementally to preserve a clear audit trail of design and configuration decisions.

## Status
**Phase 1 complete:** Baseline infrastructure deployed, validated, and documented.
