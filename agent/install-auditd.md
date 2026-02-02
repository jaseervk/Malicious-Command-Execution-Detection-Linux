# 🧩 Install & Configure Auditd (Agent Side)

## 1️⃣ Install Auditd
```bash
apt install -y auditd
```

### Enable and Start
```bash
systemctl enable auditd
systemctl start auditd
```

### Verify Status
```bash
auditctl -s
```

