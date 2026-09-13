# Active Directory User Creation

## Objective

Create domain user accounts and place them into the correct Organizational Unit (OU) for the Manchester branch.

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
3. Created three domain user accounts:
   - Kai Morris (`kmorris`)
   - Ste Johnson (`sjohnson`)
   - Tom Stuart (`tstuart`)
4. Configured each user's logon name and initial password.
5. Verified that all three users were located inside the correct `Users` OU.

## Screenshots

### Creating the First User

The first domain user, Kai Morris, was created inside the `Manchester → Users` OU. 

![Creating the First User](./01-user-creation.png)

### More Users Created

After creating the remaining accounts, I verified that Kai Morris, Ste Johnson, and Tom Stuart were all located inside the `Manchester → Users` OU.

![More Users Created](./02-more-users-created%20%281%29.png)


## PowerShell Automation

As an additional exercise, I recreated the user creation process using PowerShell.

PowerShell can be used to automate Active Directory user provisioning, which is useful when creating multiple accounts in larger environments.

### What I Did

1. Imported the Active Directory PowerShell module.
2. Created a variable containing the Distinguished Name (DN) of the Manchester Users OU.
3. Used `New-ADUser` to create a test domain user.
4. Used `Set-ADAccountPassword` to securely configure the account password.
5. Used `Enable-ADAccount` to enable the account.
6. Used `Get-ADUser` to verify the account details and confirm its location in Active Directory.

### Test Account

- Name: PowerShell Test
- Username: `pstest`
- OU: `Manchester → Users`
- Domain: `zak.lab.local`

### PowerShell Commands

```powershell
Import-Module ActiveDirectory



$ou = "OU=Users,OU=Manchester,OU=_Branches,DC=zak,DC=lab,DC=local"

New-ADUser -Name "PowerShell Test" -GivenName "PowerShell" -Surname "Test" -SamAccountName "pstest" -UserPrincipalName "pstest@zak.lab.local" -Path $ou

Set-ADAccountPassword -Identity pstest -Reset -NewPassword (Read-Host -AsSecureString "Enter password")

Enable-ADAccount -Identity pstest

Get-ADUser -Identity pstest -Properties Enabled

### PowerShell User Creation

I used PowerShell to automate the creation of a test Active Directory user. The account was created in the `Manchester → Users` OU, assigned a password, enabled, and then verified using `Get-ADUser`.

![PowerShell User Creation](./03-powershell-user-creation.png)









OUs are containers used to organise users, computers, and other Active Directory objects.

Placing users into the correct OU allows administrators to apply appropriate Group Policy, delegation, and management settings based on their location or department.

### Security Groups and Permissions

OUs do not directly give users access to files or folders.

Access is normally controlled through security groups and permissions.

```text
User
 ↓
Security Group
 ↓
Permissions
 ↓
File / Folder
