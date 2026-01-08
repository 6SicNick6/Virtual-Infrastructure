# Active Directory Design – Phase 2

## Overview

This document describes the deployment of Active Directory Domain Services (AD DS) in Phase 2 of the VMware Virtual Infrastructure Lab. This phase introduces centralized identity and authentication while preserving the Phase 1 baseline.

## Domain Design

* **Forest / Domain Name:** `vmware.lab`
* **NetBIOS Name:** `VMWARE`
* **Domain Controller:** DC01
* **AD DS Role:** Installed on DC01
* **Global Catalog:** Enabled

The `vmware.lab` namespace was selected to provide a descriptive, non-production domain aligned with the purpose of the lab. Deprecated namespaces such as `.local` were intentionally avoided.

## Domain Controller Configuration

* DC01 promoted as the **first domain controller in a new forest**
* DNS role installed during AD promotion
* Default AD database, log, and SYSVOL paths used
* Forest and domain functional levels set to match the installed Windows Server version

## IP Addressing Considerations

DC01 uses a **DHCP-assigned IP address** due to lab constraints. While static IP addressing is recommended for production domain controllers, this configuration was accepted and documented for this environment.

## Validation

* DC01 successfully rebooted after promotion
* Login verified using `VMWARE\Administrator`
* Active Directory management tools accessible
* Domain services operational
