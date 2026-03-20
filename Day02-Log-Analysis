# Day 02 – Authentication Attack Simulation & Log Analysis

## 🎯 Objective

Simulate authentication behavior in an Active Directory environment and analyze security logs to identify both normal activity and failed authentication attempts.

---

## 🧪 Lab Activities

### 1. Baseline Authentication (Successful Logons)

* Logged into Windows 10 client using:

  * CORP\jdoe
* Generated normal login/logout activity

---

### 2. Failed Authentication Attempts

Initial attempts using `runas` from within a logged-in session **did not generate failure logs** due to credential caching behavior.

👉 Key finding:

* When already authenticated, Windows may reuse valid session tokens
* This can prevent failed authentication attempts from reaching the Domain Controller

---

### 3. Forced Authentication Failures (Correct Method)

To properly generate failed authentication logs:

* Logged out of the Windows 10 client
* Used **"Other user"** login option
* Attempted login with:

  * CORP\jdoe + incorrect password
  * Non-existent users (e.g., CORP\fakeuser)

👉 This forced authentication directly against the Domain Controller

---

## 🔍 Log Analysis (Domain Controller)

Accessed:
Event Viewer → Windows Logs → Security

---

## 📌 Key Event IDs Observed

### 🔹 Event ID 4624 – Successful Logon

Indicates a valid authentication event.

* Used to establish baseline behavior

---

### 🔹 Event ID 4672 – Special Privileges Assigned

Indicates a privileged account login.

* Seen when administrative users authenticate

---

### 🔹 Event ID 4771 – Kerberos Authentication Failure

Indicates failed authentication at the Kerberos level.

* Triggered by:

  * Incorrect passwords
  * Invalid usernames

---

## 📊 Evidence

### Successful Logon (4624)

![Successful Logon](./screenshots/01-normal-logon.png)

---

### Failed Authentication (4771)

![Kerberos Failure](./screenshots/02-failed-auth.png)

---

### Audit Policy Configuration

![Audit Policy](./screenshots/03-audit-logon-config.png)

---

## 🧠 Analysis

This lab demonstrates how authentication events behave in an Active Directory environment.

Key insights:

* Successful logons (4624) establish normal activity
* Privileged logons (4672) identify high-value account usage
* Kerberos failures (4771) indicate authentication issues or attack attempts

⚠️ Important finding:

* Not all failed login attempts generate logs on the Domain Controller
* Authentication must be forced against the DC (e.g., login screen vs. active session)

---

## 🔐 Security Relevance

Authentication logs are critical for detecting:

* Brute force attacks
* Credential misuse
* Unauthorized access attempts

Repeated 4771 events from a single source may indicate:

* Password spraying
* Brute force attacks
* Enumeration attempts

---

## 🎯 Outcome

Successfully:

* Configured audit policies for authentication logging
* Simulated both successful and failed login attempts
* Identified Kerberos authentication failures in logs
* Understood differences between local vs domain authentication behavior

---

## 💡 Key Takeaway

Authentication logging depends on how credentials are used.

* Cached/local authentication may not generate logs
* Domain-level authentication must be triggered to produce detectable events

This distinction is critical for real-world SOC monitoring and detection.

