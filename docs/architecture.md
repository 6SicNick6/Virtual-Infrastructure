# VMware Virtual Infrastructure – Architecture

## Overview
This document describes the logical architecture of the Phase 1 lab environment. The design emphasizes clear role separation, manageability, and readiness for future Active Directory and DNS deployment.

## Logical Layout
- **DC01** – Future Domain Controller  
  - Intended for Active Directory services
  - No roles installed in Phase 1

- **FS01** – File Server  
  - Centralized file storage (role placeholder)
  - Windows Server baseline installation

- **MGMT01** – Management / Admin Server  
  - Administrative workstation for managing the environment
  - Used for testing connectivity, snapshot management, and VMware Tools verification

- **LNX01** – Linux Server (CLI-only)  
  - Minimal Linux installation
  - Managed entirely via command line
  - Represents a generic Linux server in enterprise environments

## Design Considerations
- Each server is deployed as a separate VM for **role isolation**
- Management traffic is centralized via MGMT01
- Linux intentionally deployed without a GUI to reflect enterprise best practices
- Snapshots taken for rollback and experimentation without compromising baseline
- Linux systems are integrated with Active Directory for centralized authentication, authorization, and privilege management.
