# Ransomware Siege – Active Directory Disaster Recovery Lab

## Project Overview

This project simulates an enterprise ransomware attack where the primary Domain Controller (DC01) is permanently lost. The Active Directory environment is recovered using a secondary Domain Controller (DC02) through disaster recovery procedures.

---

## Network Architecture

![Network Architecture](diagrams/network-architecture.png.png)

---

## Lab Environment

*Hypervisor:* Oracle VirtualBox

*Server OS:* Windows Server 2022

*Client OS:* Windows 10 Enterprise

*Domain:* technova.local

*Services:* Active Directory, DNS, Group Policy

*Tools:* PowerShell, NTDSUTIL, DCDIAG, REPADMIN

---

# Phase 1 – Initial Domain Health

The Active Directory environment was deployed with DC01 as the primary Domain Controller. DNS and replication were verified before introducing the disaster scenario.

![DC01 DNS Health](screenshots/01-dc01-dns-health.png)

---

# Phase 2 – Promote DC02

DC02 was promoted as an additional Domain Controller with integrated DNS to provide redundancy.

![DC02 Promotion](screenshots/02-dc02-promotion.png)

---

# Phase 3 – DNS Validation

After promotion, DNS records and Active Directory health were validated using DCDIAG.

![DC02 DNS Health](screenshots/03-dc02-dns-health.png)

---

# Phase 4 – Recovery Snapshot

A VirtualBox snapshot was created to preserve the healthy recovery state before performing critical recovery operations.

![Recovery Snapshot](screenshots/04-recovery-snapshot.png)

---

# Phase 5 – Connect for FSMO Recovery

NTDSUTIL was used to connect DC02 and prepare it for FSMO role recovery.

![FSMO Connection](screenshots/05-fsmo-connection.png)

---

# Phase 6 – FSMO Role Seizure

All five FSMO roles were seized from the failed DC01 and assigned to DC02.

![FSMO Seizure](screenshots/06-fsmo-seizure.png)

---

# Phase 7 – Verify FSMO Ownership

The transfer was confirmed successfully using `netdom query fsmo`. 

![FSMO Verification](screenshots/07-fsmo-verification.png)

---

# Phase 8 – Final Health Check

A complete DNS diagnostic confirmed that the recovered domain was fully operational.

![Final Health Check](screenshots/08-final-health-check.png)

---

# Skills Demonstrated

- Active Directory Domain Services
- Windows Server 2022 Administration
- DNS Management
- Domain Controller Promotion
- FSMO Role Seizure
- NTDSUTIL Recovery
- DCDIAG Health Validation
- PowerShell Administration
- VirtualBox Disaster Recovery

---

# Project Outcome

- Recovered enterprise Active Directory after a simulated ransomware attack.
- Restored DNS and Global Catalog services.
- Successfully transferred all FSMO roles to DC02.
- Validated a healthy and operational domain environment.
