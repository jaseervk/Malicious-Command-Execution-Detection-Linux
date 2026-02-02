<!-- Send Auditd Logs to Wazuh -->
### Add rules on ossec.conf

```bash
nano /var/ossec/etc/ossec.conf
```

Add this rule:

```bash
<localfile>
  <log_format>audit</log_format>
  <location>/var/log/audit/audit.log</location>
</localfile>
```

Restart Agent:
```bash
systemctl restart wazuh-agent
```
