# DNS Design – Phase 2

## Overview

This document describes the DNS configuration introduced during Phase 2. DNS services are required for Active Directory functionality and hostname resolution.

## DNS Configuration

* DNS installed on **DC01**
* AD-integrated forward lookup zone created:

  * `vmware.lab`
* DC01 configured to use **itself** as the primary DNS server

## Name Resolution Validation

The following validation steps were performed:

* Forward lookup resolution:

  * `nslookup dc01`
* Domain name resolution:

  * `nslookup vmware.lab`

Both commands returned valid results, confirming DNS functionality.

## Known Warnings and Limitations

* A warning was generated during AD promotion due to DC01 using DHCP
* Static IP addressing was not permitted by lab constraints
* DNS services were validated and confirmed operational despite this limitation

## Deferred Configuration

* Reverse lookup zones
* DHCP DNS integration (if supported by lab)

These items may be revisited in a future phase if constraints allow.
