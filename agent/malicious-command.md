# Malicious Command Execution Detection

```bash
-a always,exit -F path=/usr/bin/nc -F perm=x -k netcat_exec
-a always,exit -F path=/usr/bin/nmap -F perm=x -k recon_exec
-a always,exit -F path=/usr/bin/curl -F perm=x -k data_exfil
-a always,exit -F path=/usr/bin/wget -F perm=x -k data_exfil
-a always,exit -F path=/usr/bin/python -F perm=x -k script_exec
-a always,exit -F path=/usr/bin/perl -F perm=x -k script_exec
```

Reload Rules:
```bash
augenrules --load
systemctl restart auditd
```
