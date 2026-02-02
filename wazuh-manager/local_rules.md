<!-- Custom Wazuh Rules for Malicious Commands -->
Add rules on local_rules.xml

```bash
nano /var/ossec/etc/rules/local_rules.xml
```

Add rules:
```bash
<group name="malicious_commands">

  <rule id="100200" level="13">
    <if_sid>80700</if_sid>
    <field name="audit.key">netcat_exec</field>
    <description>Netcat execution detected</description>
    <mitre>T1046</mitre>
  </rule>

  <rule id="100201" level="12">
    <if_sid>80700</if_sid>
    <field name="audit.key">data_exfil</field>
    <description>Potential data exfiltration command executed</description>
    <mitre>T1041</mitre>
  </rule>

  <rule id="100202" level="12">
    <if_sid>80700</if_sid>
    <field name="audit.key">script_exec</field>
    <description>Scripting language execution detected</description>
    <mitre>T1059</mitre>
  </rule>

</group>

<group name="privilege_escalation">

  <rule id="100101" level="14">
    <if_sid>80700</if_sid>
    <field name="audit.key">su_exec</field>
    <description>su command executed – root shell attempt</description>
    <mitre>T1548</mitre>
  </rule>

</group>
```

Restart Manager:
```bash
systemctl restart wazuh-manager
```
