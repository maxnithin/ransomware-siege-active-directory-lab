# Ransomware Siege – Active Directory Disaster Recovery Lab

## Project Overview

This project simulates a real enterprise ransomware attack where the primary Domain Controller (DC01) is permanently lost. The environment is recovered using a secondary Domain Controller (DC02) through Active Directory disaster recovery procedures.

## Environment

- Windows Server 2022
- Active Directory Domain Services
- DNS
- Group Policy
- PowerShell
- VirtualBox

## Infrastructure

- DC01 – Primary Domain Controller (Destroyed)
- DC02 – Secondary Domain Controller (Recovered)
- CLIENT01 – Domain-joined Windows 10 workstation

## Project Phases

1. Enterprise AD Infrastructure Setup
2. Replication & Health Validation
3. Ransomware Attack Simulation
4. Active Directory Disaster Recovery
5. Business Continuity Validation
6. Documentation

## Skills Demonstrated

- Active Directory Administration
- FSMO Role Seizure
- Metadata Cleanup
- DNS Troubleshooting
- Group Policy Management
- PowerShell Administration
- Enterprise Disaster Recovery
