
### Privilege Escalation Detection Rules

Add rule on /etc/audit/rules.d/privilege-escalation.rules

```bash
nano /etc/audit/rules.d/privilege-escalation.rules
```
Add this rules:
```bash
-a always,exit -F path=/usr/bin/sudo -F perm=x -k sudo_exec
-a always,exit -F path=/bin/su -F perm=x -k su_exec
-a always,exit -F path=/bin/bash -F euid=0 -F perm=x -k root_shell
-a always,exit -F path=/bin/sh -F euid=0 -F perm=x -k root_shell
-a always,exit -F path=/usr/bin/pkexec -F perm=x -k pkexec_exec
```

Apply Rules:
```bash
augenrules --load
systemctl restart auditd
auditctl -l
```
