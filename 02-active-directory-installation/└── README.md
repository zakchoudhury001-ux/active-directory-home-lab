# Active Directory Domain Services Installation

## Objective

Install the Active Directory Domain Services (AD DS) role on the Windows Server VM (DC01) as preparation for promoting the server to a Domain Controller.

## Environment

- Server: DC01
- Operating System: Windows Server 2022 Datacenter
- Platform: Microsoft Azure
- Role: Active Directory Domain Services (AD DS)

## What I Did

1. Connected to DC01 using Remote Desktop.
2. Opened Server Manager.
3. Selected **Add Roles and Features**.
4. Chose **Role-based or feature-based installation**.
5. Selected DC01 as the target server.
6. Installed the **Active Directory Domain Services (AD DS)** role.
7. Installed the associated AD DS management tools.
8. Started the Active Directory Domain Services Configuration Wizard.
9. Selected **Add a new forest** for the new AD environment.
10. Configured the Domain Controller options.
11. Left DNS delegation disabled because this is a new environment.
12. Completed the prerequisite checks successfully.
13. Started the Domain Controller promotion.

## Key Concepts Learned

### Active Directory Domain Services (AD DS)

AD DS is a Windows Server role that provides directory services for managing users, computers, groups and authentication within a Windows domain.

### Domain Controller

A Domain Controller is a server that hosts AD DS and provides services such as authentication and authorization for the domain.

### Global Catalog

The Global Catalog provides a searchable view of objects across the Active Directory forest.

### DNS

DNS is closely integrated with Active Directory and is required for locating domain services and allowing clients to find Domain Controllers.

## Troubleshooting / Notes

During the promotion process, Windows displayed a DNS delegation warning:

> A delegation for this DNS server cannot be created because the authoritative parent zone cannot be found.

This was expected because this lab is creating a new Active Directory environment and there was no existing parent DNS zone.

The prerequisite checks completed successfully before starting the installation.

## What I Learned

Installing the AD DS role does not automatically make the server a Domain Controller. The server must be promoted and configured as a Domain Controller.

This lab helped me understand the relationship between:

**Windows Server → AD DS → Domain Controller → Active Directory Domain**
