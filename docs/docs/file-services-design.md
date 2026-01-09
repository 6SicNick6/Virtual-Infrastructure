# File Services Design – Phase 3

## Overview
This document describes the implementation of centralized file services on FS01 using Active Directory–based access control.

## Design Goals
- Centralized storage
- Least-privilege access
- Group-based permissions
- Separation of share and NTFS permissions

## Share Configuration
- Server: FS01
- Share Name: Dept-Shared
- UNC Path: \\FS01\Dept-Shared

## Security Model
Access is controlled using Active Directory security groups:

- FS-Dept-Shared-RW: Read/Write access
- FS-Dept-Shared-RO: Read-only access

Permissions are enforced at both:
- NTFS level
- SMB share level

## Validation
Access was validated from MGMT01 using a non-administrative domain user, confirming correct group-based authorization.
