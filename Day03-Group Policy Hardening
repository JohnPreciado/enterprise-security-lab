# Day 03 – Group Policy Hardening

## 🎯 Objective
Implement domain-wide security controls using Group Policy to harden the Active Directory environment and mitigate common attack vectors such as brute-force attacks and unauthorized system access.

---

## 🧱 Environment Overview

- Domain: corp.local
- Domain Controller: DC01
- Client: Windows 10 (Domain Joined)
- Network: Host-only (192.168.56.0/24)

---

## 🔐 Group Policy Configuration

### 📌 GPO Structure
Two policies were used:

1. **Default Domain Policy**
   - Password Policy
   - Account Lockout Policy

2. **CORP Security Baseline**
   - User restrictions (CMD, Control Panel)
   - Audit policy configuration

---

### 📊 GPO Link Verification
![GPO Linked](./screenshots/01-GPO-linked.png)

---

## 🔐 Password Policy (Domain-Level)

Configured in **Default Domain Policy**:

- Minimum password length: 12 characters
- Password complexity: Enabled
- Maximum password age: 60 days

### 📸 Evidence
![Password Policy](./screenshots/02-pw-policy-settings.png)

---

## 🔒 Account Lockout Policy (Domain-Level)

Configured in **Default Domain Policy**:

- Lockout threshold: 5 invalid attempts
- Lockout duration: 30 minutes
- Reset counter: 30 minutes

### 📸 Evidence
![Account Lockout Policy](./screenshots/03-acc-lockout-policy.png)

---

## 🚫 User Restrictions (GPO)

Configured in **CORP Security Baseline**:

### Command Prompt Restriction
- Prevent access to command prompt: Enabled

### 📸 Evidence
![CMD Restriction Policy](./screenshots/04-cmd-restriction.png)

---

## 🔍 Audit Policy Reinforcement

Configured to ensure visibility of authentication activity:

- Audit Credential Validation: Success & Failure
- Audit Kerberos Authentication Service: Success & Failure

### 📸 Evidence
![Audit Policy](./screenshots/05-audit-reinforcement.png)

---

## 🧪 Testing & Validation

### ❌ Password Complexity Enforcement

Attempted to set a weak password:

👉 Result: Rejected due to domain policy

### 📸 Evidence
![Password Complexity Failure](./screenshots/06-pw-complexity-fail.png)

---

### 🚫 Command Prompt Restriction

Attempted to launch CMD:

👉 Result: Blocked by Group Policy

### 📸 Evidence
![CMD Disabled](./screenshots/07-cmd-disabled-by-admin.png)

---

### 🔒 Account Lockout Enforcement

Performed multiple failed login attempts:

👉 Result: Account locked after threshold exceeded

### 📸 Evidence
![Account Lockout](./screenshots/08-lockout-policy-works.png)

---

## 🧠 Key Findings

- Account lockout policies must be configured in the **Default Domain Policy**
- Custom GPOs cannot override domain-level account policies
- Group Policy can effectively restrict user behavior and reduce attack surface
- Audit policies provide visibility into authentication activity for detection

---

## 🔐 Security Impact

This configuration helps defend against:

- Brute-force password attacks
- Unauthorized command execution
- Local system manipulation by standard users
- Lack of visibility into authentication failures

---

## 🎯 Outcome

Successfully implemented and validated domain-wide security controls using Group Policy.

Demonstrated the ability to:
- Enforce centralized security policies
- Restrict user-level access to sensitive tools
- Detect and prevent brute-force authentication attempts
- Apply real-world enterprise hardening techniques

---
