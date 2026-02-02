# 🚨 Malicious Command Execution Detection on Linux

This project demonstrates detection of **malicious command execution and privilege escalation** on Linux systems using **Auditd + Wazuh SIEM**.

## 🔍 What This Project Detects
- Privilege escalation attempts (`sudo`, `su`, root shells)
- Reconnaissance tools (`nmap`)
- Reverse shells / network tools (`netcat`)
- Data exfiltration (`curl`, `wget`)
- Script execution (`python`, `perl`)

## 🛠 Tools Used
- Auditd (Linux auditing framework)
- Wazuh Agent & Manager
- Linux (Ubuntu/Debian)

## 📊 Detection Flow
Linux Commands ➜ Auditd Logs ➜ Wazuh Agent ➜ Wazuh Manager ➜ Security Alerts

---

