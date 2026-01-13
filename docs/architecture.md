# Architecture Design

## Overview
This environment represents a simplified enterprise virtual infrastructure built on VMware virtualization.  
The design centralizes identity, authentication, and authorization using Active Directory and extends those services to both Windows and Linux systems.

---

## Logical Architecture

- All virtual machines reside on a single VMware-provided virtual network
- DHCP is used due to lab constraints
- Active Directory DNS is the authoritative name resolution service
- Security and access control are enforced using Active Directory groups

---

## Key Components

### DC01
- Active Directory Domain Services
- DNS Server
- Domain: vmware.lab

### FS01
- Windows File Server
- NTFS and share permissions controlled by AD security groups

### MGMT01
- Domain-joined management workstation
- Used for administration and validation

### LNX01
- Linux server (CLI-only)
- Integrated with Active Directory using SSSD
- Uses AD for authentication and authorization

---

## Design Principles
- Centralized identity and access management
- Role-based access control using security groups
- Separation of administrative privileges and data access
- Cross-platform interoperability between Windows and Linux systems
