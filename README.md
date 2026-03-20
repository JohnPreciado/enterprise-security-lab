# Enterprise Security Lab (Active Directory + SOC Simulation)

## 🚨 What This Proves
This project demonstrates hands-on experience with:

- Active Directory deployment and administration
- Identity and Access Management (IAM)
- Domain authentication workflows
- Network configuration and troubleshooting
- Role-Based Access Control (RBAC) and privilege management
- Security event generation and analysis (SOC-level concepts)

This lab simulates a real-world enterprise environment used in IT operations and Security Operations Centers (SOC).

---

## 🧠 Project Context
This lab was built to simulate an enterprise network from the ground up, following real-world blue team workflows:

1. Build core infrastructure (Active Directory + DNS)
2. Configure users, groups, and permissions
3. Join endpoints to the domain
4. Simulate attacks and authentication failures
5. Analyze logs and detect suspicious activity
6. Apply security controls and hardening

This mirrors how real organizations build, attack, and defend their environments.

---

## 🧱 Lab Architecture

- **Domain Controller:** Windows Server 2022 (DC01)
- **Client Machine:** Windows 10 (WIN10-CLIENT1)
- **Domain:** corp.local
- **Network:** Host-only (VirtualBox)

### IP Configuration
- DC01: `192.168.56.10`
- Client: `192.168.56.20`

---

## 🗂️ Lab Structure

| Day | Focus |
|-----|------|
| Day 01 | Active Directory Setup & Domain Join |
| Day 02 | Attack Simulation & Log Analysis |
| Day 03 | Group Policy Hardening |
| Day 04 | Authentication Attacks |
| Day 05 | SIEM Integration |
| Day 06 | Firewall Configuration |
| Day 07 | Network Segmentation |
| Day 08 | Attack Detection & Response |
| Day 09 | Hardening & Remediation |
| Day 10 | Final Report |

---

## 🛠️ Technologies Used

- Windows Server 2022
- Windows 10
- Active Directory Domain Services (AD DS)
- DNS
- VirtualBox
- Windows Event Viewer
- (Upcoming) Wazuh / Splunk SIEM

---

## 🔐 Security Relevance

Active Directory is a primary target in enterprise environments.

This lab builds a realistic environment to:
- Simulate credential-based attacks
- Generate authentication logs (Event IDs like 4624 / 4625)
- Analyze login behavior and detect anomalies
- Understand how attackers move within a domain

---

## 🎯 Key Skills Demonstrated

- Active Directory setup and administration
- Identity and Access Management (IAM)
- Network troubleshooting (IP configuration, DNS, connectivity)
- Domain authentication and user management
- Privilege assignment and escalation (Domain Admins)
- Security-focused lab design and documentation

---

## 📌 Outcome

Successfully deployed and validated a working enterprise domain environment with:

- Functional domain authentication
- Structured user and group management
- Networked client-server communication
- A foundation for attack simulation and detection

This lab will be expanded into a full SOC-style detection and response environment.
