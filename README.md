#  Active Directory Home Lab

A fully functional Active Directory home lab built on Windows Server to simulate a real enterprise IT environment. This project covers user management, Group Policy, domain-joined clients, security event monitoring, password management, and account lifecycle management.

---

##  Tools & Technologies

- Windows Server (Domain Controller)
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- Windows Event Viewer
- Virtual Machines (VM1 - Server, VM2 - Client)

---

##  What I Built

### 1. Active Directory Domain Setup
- Created a domain: `lab.local`
- Configured Organizational Units (OUs): `Lab Users`, `it lab users`
- Built the foundation for a structured AD environment

### 2. User & Group Management
- Created a user account: `John Smith (jsmith)`
- Created a Security Group: `Staff`
- Assigned users and computers to the appropriate OU

### 3. Group Policy Object (GPO)
- Created a GPO called `IT Lab Policy`
- Linked it to the `Lab Users` OU
- Configured an **account lockout policy** (locks account after failed login attempts)
- Verified policy application using `gpresult` on the client machine

### 4. Domain-Joined Client
- Joined a Windows client VM (VM2) to the `lab.local` domain
- Confirmed the GPO was applied to the client via `gpresult /r`
- VM2 appeared in ADUC under the `Lab Users` OU

### 5. Security Event Monitoring
- Triggered an account lockout on `jsmith` from VM2
- Located and analyzed **Event ID 4740** (Account Lockout) in Windows Event Viewer
- Identified the source computer and timestamp of the lockout
- Unlocked the account in ADUC

### 6. Password Reset
- Performed a password reset on `jsmith` via ADUC
- Simulating one of the most common real-world help desk tickets
- Used the "User must change password at next logon" option to follow security best practices

### 7. Account Offboarding
- Disabled `John Smith's` account after lab completion
- Moved account to the `Disabled Accounts` OU — simulating real employee offboarding procedures

---

##  Screenshots

> Screenshots documenting each step are located in the `/screenshots` folder.

| File | Description |
|------|-------------|
| 01-ad-users-groups.png | AD Users and Computers — user and group created |
| 02-gpo-linked.png | GPO linked to Lab Users OU |
| 03-gpresult-applied.png | gpresult confirming IT Lab Policy applied to VM2 |
| 04-aduc-lab-users-ou.png | ADUC showing VM2, Staff group, and John Smith in Lab Users OU |
| 05-event-4740-lockout.png | Event Viewer — Event ID 4740 account lockout for jsmith |
| 06-password-reset.png | Password reset performed on jsmith via ADUC |
| 07-account-disabled.png | Disabled Accounts OU — John Smith offboarded |

---

##  What I Learned

- How Active Directory structures users, groups, and computers using OUs
- How GPOs are created, linked, and applied to domain objects
- How to join a Windows client to a domain and verify policy application
- How to read and interpret Windows Security Event Logs
- How to perform common help desk tasks: password resets, account unlocks, and offboarding
- How to handle the full lifecycle of a user account: creation → policy enforcement → troubleshooting → offboarding

---

##  Real World Skills Demonstrated

| Lab Task | Enterprise Equivalent |
|----------|----------------------|
| Created user & security group | Employee onboarding |
| Configured & linked GPO | Enforcing company IT policies |
| Joined client VM to domain | Setting up a work computer |
| Monitored lockout via Event Viewer | Help desk troubleshooting |
| Reset user password | Common help desk ticket |
| Disabled & moved account | Employee offboarding |

---

