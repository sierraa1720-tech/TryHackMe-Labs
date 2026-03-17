**Lab Environment:** [TryHackMe - Active Directory Basics](https://tryhackme.com/room/winadbasics) 
![TryHackMe Stats](https://tryhackme-badges.s3.amazonaws.com/sierraa1720.png)
🖥️ Active Directory Lab: User Delegation & Password Management
Platform: TryHackMe | Lab: Active Directory Basics

Objective
Demonstrated the principle of Least Privilege and Delegated Administration within a Windows Domain environment. The goal was to perform administrative tasks as a delegated user (Phillip) rather than using the full Domain Administrator account.

Tasks Executed
User Impersonation: Logged in as THM\phillip, a member of the IT Support team with specific delegated permissions over the Sales Organizational Unit (OU).

PowerShell Administration: Used PowerShell to bypass GUI limitations and manage user accounts via the command line.

Password Reset & Security Policy: Successfully reset the password for the user sophie using Phillip's delegated authority.

Commands Used:

PowerShell
# Resetting a user password via PowerShell
Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose

# Forcing a password change at the next login to maintain security integrity
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose
Key Concepts Mastered
Organizational Units (OUs): Navigated the structure of a Domain Controller to locate specific users and groups.

Delegation of Control: Understood how a Domain Admin can grant specific permissions (like password resets) to non-admin users to reduce security risks.

Domain Connectivity: Practiced connecting to a Domain Controller via RDP and managing sessions within an AttackBox environment.
