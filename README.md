# VMware Virtual Infrastructure Lab

## Overview
This project documents the design, deployment, and validation of a beginner-friendly, enterprise-style VMware virtual infrastructure.  
The lab focuses on centralized identity management using Active Directory and demonstrates secure access to services across both Windows and Linux systems.

The environment was built under constrained lab conditions, simulating a shared enterprise VMware platform with abstracted hardware and networking.

---

## Objectives
- Build a functional VMware-based virtual infrastructure
- Deploy Active Directory and DNS services
- Implement Windows file services with role-based access control
- Integrate a Linux system with Active Directory
- Validate cross-platform authentication and authorization

---

## Environment Constraints
- Shared enterprise VMware lab
- Host hardware and physical networking abstracted
- Single lab-provided VM network
- DHCP required for virtual machines

---

## Virtual Machines
- **DC01** – Windows Server (Active Directory Domain Controller, DNS)
- **FS01** – Windows Server (File Server)
- **MGMT01** – Windows Server (Management workstation)
- **LNX01** – Linux Server (CLI-only)

---

## Project Phases
- **Phase 1:** Baseline Infrastructure
- **Phase 2:** Active Directory and DNS
- **Phase 3:** Windows File Services
- **Phase 4:** Linux Identity and Privilege Integration

---

## Project Status
This lab environment is complete and fully functional.  
All systems are integrated into a centralized identity model using Active Directory, with validated access control across Windows and Linux platforms.

The project demonstrates foundational enterprise infrastructure concepts, including directory services, file services, cross-platform authentication, and role-based access control.
