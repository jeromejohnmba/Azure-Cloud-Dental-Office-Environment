# Cloud Dental Office Environment

## Purpose

The purpose of the Cloud Dental Office project is to simulate a small dental practice environment using Microsoft Azure and Microsoft 365 technologies. The project demonstrates core cloud administration, endpoint management, identity security, monitoring, backup, and Microsoft 365 administration tasks commonly performed in modern business environments.

---

# Tech Stack

- Microsoft 365
- Microsoft Intune
- Microsoft Exchange Online
- Microsoft Entra ID
- Azure Virtual Machines (VMs)
- Azure Storage
- Azure Monitor
- Log Analytics

---

# Features / Objectives

- Azure cloud infrastructure deployment and management
- Microsoft Entra ID configuration
- Multi-Factor Authentication (MFA) enforcement through Conditional Access
- Conditional Access policy configuration
- Microsoft Intune endpoint management
- Windows device enrollment into Intune
- Endpoint security policy enforcement
- Azure Storage configuration
- Azure Monitor and Log Analytics setup
- Azure alert rule configuration
- Azure VM backup configuration
- Exchange Online administration and mailbox management

---

# Environment Details

| Component | Name |
|---|---|
| Resource Group | DentalServer01_group |
| Virtual Machine | DentalServer01 |
| Storage Account | contosodentalstorage01 |
| Storage Container | patientrecords |
| Recovery Services Vault | DentalBackupVault |
| Shared Mailbox | Jerome Admin |
| Distribution Group | Dental Providers |
| Region | West US 2 |

---

# Documentation Structure

Project files are organized into the following folders:

- `/docs` – Architecture overview and project documentation
- `/configs` – Configuration details and policy settings
- `/screenshots` – Project screenshots with implementation notes and configuration proof

---
