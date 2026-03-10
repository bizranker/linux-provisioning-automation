# ⚙️ Linux Provisioning Automation Toolkit

Zero-touch Linux host provisioning using **Kickstart (CentOS)** and **Preseed (Ubuntu)** automation.

This toolkit was designed for high-scale infrastructure environments where new hosts needed to be provisioned quickly, consistently, and with minimal manual intervention.

---

## 🧠 Overview

These scripts automate the full lifecycle of Linux server provisioning.

Given only a **hostname** and **MAC address**, the system automatically:

• Assigns the next available IP address  
• Updates DHCP configuration  
• Generates DNS forward records  
• Generates DNS reverse records  
• Increments zone serial numbers  
• Restarts DHCP and DNS services  
• Generates host build configuration  
• Executes automated OS installation  
• Applies post-install configuration  

The system supports both:

- **CentOS Kickstart**
- **Ubuntu Preseed**

---

## 🚀 Provisioning Workflow

Engineer → runs provisioning script
↓
MAC + Hostname passed as parameters
↓
Script assigns next available IP
↓
DHCP configuration updated
↓
DNS forward + reverse records created
↓
DHCP / DNS services restarted
↓
Kickstart / Preseed install triggered
↓
Post-install configuration applied
↓
Host ready for infrastructure onboarding


---

## 📂 Repository Contents

| Script | Purpose |
|------|------|
| `centos7-provision-new-kickstart-host.sh` | Creates new CentOS host provisioning entry |
| `centos7-backout-kickstart-host.sh` | Safely removes host configuration |
| `ubuntu1604-provision-new-preseed-host.sh` | Creates Ubuntu host provisioning entry |
| `ubuntu1604-backout-preseed-host.sh` | Rolls back Ubuntu host configuration |
| `ubuntu-preseed-post-install-script.sh` | Executes automated post-install configuration |

---

## 🔁 Rollback Safety

A key design principle of these scripts is **safe reversibility**.

Each provisioning action includes:

• Configuration backups  
• DNS serial tracking  
• DHCP state restoration  
• Automated rollback scripts

This ensures infrastructure changes can be **safely undone** if necessary.

---

## 🏗️ Design Goals

The toolkit was designed with several operational goals:

- Reduce manual provisioning errors
- Enable consistent infrastructure builds
- Support large distributed engineering teams
- Provide quick host provisioning for development environments
- Allow rapid rollback of configuration changes

---

## 📈 Real-World Usage

This automation was used to provision Linux hosts across a distributed enterprise infrastructure environment where development teams required rapid onboarding of systems for testing and platform engineering work.

The toolkit helped reduce manual provisioning effort while maintaining consistent network and configuration state across environments.

---

## 🧰 Technologies Used

- Bash
- Linux DHCP (ISC DHCP)
- BIND DNS
- CentOS Kickstart
- Ubuntu Preseed
- Automated configuration scripting

---

## 👤 Author

Brian Bills  
Senior DevOps / Site Reliability Engineer

GitHub: https://github.com/bizranker  
LinkedIn: https://www.linkedin.com/in/brianbills-devops

---

## 📜 License

MIT
