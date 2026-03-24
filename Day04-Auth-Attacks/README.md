# Day 04 - Authentication Attacks & Detection

## Objective
Simulate authentication attack patterns in an Active Directory environment and analyze corresponding security event logs to identify indicators of brute-force and privileged access activity.

---

## Lab Setup
- Domain Controller: DC01 (corp.local)
- Client Machine: Windows 10 (Domain Joined)
- Domain Users: John Doe, Admin1
- Security Controls: Account Lockout Policy Enabled (Day 03)

---

## Attack Simulation

### 1. Failed Authentication Attempts (Brute Force Behavior)

Multiple incorrect password attempts were performed against a domain user account to simulate brute-force activity.

#### Result:
- Event ID **4771** (Kerberos Pre-Authentication Failed) generated
- Confirms invalid credential attempts against domain account

📸 Screenshot:
![Failed Authentication](screenshots/02-failed-auth.png)

---

### 2. Successful Authentication After Failures

After several failed attempts, a correct password was entered.

#### Result:
- Event ID **4624** (Successful Logon)
- Indicates account compromise following repeated failures

📸 Screenshot:
![Successful Logon](screenshots/01-normal-logon.png)

---

### 3. Privileged Account Logon Detection

A domain administrator account (`CORP\admin1`) was used to log in.

#### Result:
- Event ID **4672** (Special Privileges Assigned)
- Confirms elevated privileges granted during logon session

#### Observed Privileges:
- SeDebugPrivilege  
- SeBackupPrivilege  
- SeRestorePrivilege  
- SeTakeOwnershipPrivilege  
- SeImpersonatePrivilege  

📸 Screenshot:
![Admin Privileges Assigned](screenshots/01-ps-spray-admin-priv.png)

---

### 4. Account Lockout Enforcement

Account lockout policy from Day 03 was triggered after exceeding failed login threshold.

#### Result:
- User account locked after multiple failed attempts
- Prevents further brute-force attempts

📸 Screenshot:
![Account Lockout](screenshots/03-account-lockout.png)

---

## Event Correlation (Attack Timeline)

The following sequence was observed:

```text
4771 → 4771 → 4771 → 4624 → 4672
