# Active Directory Security Groups

## Objective

Create and configure security groups to organise users and manage access to resources within the Active Directory environment.

## Environment

- Domain Controller: DC01
- Domain: zak.lab.local
- Branch: Manchester
- Operating System: Windows Server 2022
- Directory Service: Active Directory Domain Services (AD DS)

## What I Did

1. Opened **Active Directory Users and Computers**.
2. Navigated to the `OU_Groups` organizational unit.
3. Created the following security groups:
   - Helpdesk
   - Accounting
   - ITSupport
4. Added users to the appropriate security groups.
5. Opened each group's **Members** section to verify group membership.
6. Confirmed that users remained members of their security groups independently of their OU location.


### Groups Created

The security groups were created inside the `OU_Groups` organizational unit.

![Active Directory Groups](./01-groups-created.png)

## Security Groups

| Group | Purpose |
|---|---|
| Helpdesk | Provides access appropriate for Helpdesk staff |
| Accounting | Provides access appropriate for Accounting staff |
| ITSupport | Provides access appropriate for IT Support staff |

## Key Concepts Learned

### Security Groups

Security groups are used to assign permissions to resources such as files, folders, applications, and shared drives.

Instead of assigning permissions to individual users, permissions can be assigned to a security group and users can then be added to that group.

```text
User
 ↓
Security Group
 ↓
Permissions
 ↓
Resource
