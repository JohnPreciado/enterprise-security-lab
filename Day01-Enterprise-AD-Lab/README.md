# Day 01 – Active Directory Domain Setup (corp.local)

## Objective

Build a functional Windows Active Directory environment from scratch, including a Domain Controller, user management, and a domain-joined Windows 10 client.

---

## Environment Overview

| Component         | Details             |
| ----------------- | ------------------- |
| Hypervisor        | Oracle VirtualBox   |
| Domain Controller | Windows Server 2022 |
| Client Machine    | Windows 10          |
| Domain Name       | corp.local          |
| Network Type      | Host-Only           |
| DC IP             | 192.168.56.10       |
| Client IP         | 192.168.56.20       |

---

## Key Tasks Completed

### 1. Domain Controller Setup

* Installed **Active Directory Domain Services (AD DS)** and **DNS**
* Promoted server to Domain Controller
* Created domain: `corp.local`

---

### 2. Network Configuration

* Configured static IP on Domain Controller:

  * IP: `192.168.56.10`
* Configured Windows 10 client:

  * IP: `192.168.56.20`
  * DNS: `192.168.56.10`
* Verified connectivity using `ping`

---

### 3. Active Directory Configuration

* Created Organizational Units (OUs):

  * `_Admins`
  * `_IT`
  * `_HR`
  * `_Users`
* Created user accounts:

  * `Admin1`
  * `John Doe`
  * `Jane Doe`
* Added `Admin1` to **Domain Admins**

---

### 4. Domain Join

* Joined Windows 10 client to `corp.local`
* Verified successful domain join

---

### 5. Authentication Validation

* Logged into domain using:

  * `corp\JohnDoe`
* Confirmed domain authentication functionality

---

## Validation Steps

* Verified domain on DC:

```bash
systeminfo | findstr /B /C:"Domain"
```

* Verified network connectivity:

```bash
ping 192.168.56.10
```

---

## Screenshots

### AD DS Installed

![AD DS](screenshots/01-AD-DS-Installed.png)

### Client Network + Ping Test

![Ping](screenshots/02-Client-IP-and-Ping.png)

### Domain Admin Privileges

![Admins](screenshots/03-Domain-Admins-Membership.png)

### Domain Verification

![Domain](screenshots/04-Domain-Verification.png)

### Domain Join Success

![Join](screenshots/05-Domain-Join-Success.png)

### Domain User Login

![Login](screenshots/06-Domain-User-Login.png)

### Client Static IP Configuration

![IP](screenshots/07-Client-Static-IP.png)

---

## Skills Demonstrated

* Active Directory deployment and configuration
* DNS configuration and troubleshooting
* Windows Server administration
* User and group management (RBAC)
* Domain join and authentication workflows
* Network troubleshooting and validation

---

## Outcome

Successfully built and validated a fully functional Active Directory domain environment with centralized authentication and domain-joined client access.

---

## Next Steps (Day 02)

* Domain enumeration from client machine
* Event log analysis
* Initial attack simulation (authentication-based)

