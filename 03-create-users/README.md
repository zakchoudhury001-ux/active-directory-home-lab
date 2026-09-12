# Active Directory User Creation

## Objective

Create domain user accounts and place them in the correct Organizational Unit (OU) for the Manchester branch.

## Environment

- Domain Controller: DC01
- Domain: zak.lab.local
- Branch: Manchester
- OU: _Branches → Manchester → Users
- Operating System: Windows Server 2022
- Directory Service: Active Directory Domain Services (AD DS)

## What I Did

1. Opened **Active Directory Users and Computers**.
2. Navigated to `_Branches → Manchester → Users`.
3. Created the first domain user account.
4. Configured the user's logon name and initial password.
5. Created the additional domain user accounts.
6. Verified that all users were located inside the correct `Users` OU.

## User Accounts

The following accounts were created for the Manchester branch:

- Kai Morris (`kmorris`)
- Ste Johnson (`sjohnson`)
- Tom Stuart (`tstuart`)

## Key Concepts Learned

### Organizational Units (OUs)

OUs are containers used to organise users, computers, and other Active Directory objects.

Placing users into the correct OU allows administrators to apply appropriate **Group Policy**, delegation, and management settings based on their location or department.

### Security Groups vs OUs

An OU does **not** directly give a user access to a file or resource.

Access is normally controlled through **security groups and permissions**.

For example:

`User → Security Group → Resource Permissions`

## What I Learned

I learned how to create domain user accounts in Active Directory and place them into the correct OU.

I also learned that the OU is used for organisation and management, while security groups and permissions are used to control access to resources.

## Lab Structure

```text
zak.lab.local
└── _Branches
    └── Manchester
        ├── Users
        │   ├── Kai Morris
        │   ├── Ste Johnson
        │   └── Tom Stuart
        ├── Workstations
        └── Laptops
