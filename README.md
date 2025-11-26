# Home-SOC-Wazuh-Sysmon-Detection-Lab
Threat Detection Lab using Wazuh SIEM, Sysmon, and Kali Linux
# 🛡️ Home SOC Project – Wazuh + Sysmon + Kali Linux  
**Threat Detection | Incident Response | MITRE ATT&CK Mapping**

This project simulates real-world attack behavior in a controlled home lab using Wazuh SIEM and Sysmon to detect and analyze malicious events across multiple techniques.  
It includes brute force attacks, PowerShell misuse, malware staging, persistence mechanisms, and privilege escalation attempts.

---

# 🏗️ Lab Architecture

```
Kali Linux (Attacker)
       ↓  (Simulated Attacks)
Windows 11 Endpoint (Sysmon + Wazuh Agent)
       ↓
Wazuh SIEM (Ubuntu Server)
       ↓
Wazuh Dashboard / MITRE ATT&CK Mapping
```

---

# 📦 Tools Used
- **Wazuh SIEM** (server, indexer, dashboard)
- **Sysmon v15+** (process, network, file telemetry)
- **Windows Event Logging**
- **Kali Linux** (Hydra, PowerShell payloads, malware simulation)
- **MITRE ATT&CK Navigator**

---

# 🚨 **Attack Scenarios & Detections**

Below are all 6 attack simulations with screenshots and MITRE mappings.

---

# 🟦 Scenario 1 — Unauthorized Software Installation  
**Goal:** Detect installation of a legitimate application generating suspicious service activity.  
**Technique:** *T1059 – Execution*, *T1543 – Service Installation*

### 📸 Screenshots
#### Wazuh Agent Overview  
![Scenario 1 Agent List](screenshots/scenario1/scenario1/s1 windos security event.png)

#### Alerts (Filtered View)  
![Scenario 1 Alerts](screenshots/scenario1/scenario1/s1-alerts-overview.png)

#### Event JSON  
![Scenario 1 Event JSON](screenshots/scenario1/scenario1/s1-event-json.png)

#### Executable File Creation  
![Scenario 1 File Create](screenshots/scenario1/scenario1/s1-file-create.png)

#### Installation Execution  
![Scenario 1 Installation](screenshots/scenario1/scenario1/s1-chrome-install.png)

#### Windows Event Log  
![Scenario 1 Security Log](screenshots/scenario1/scenario1/s1-security-log.png)

---

# 🟩 Scenario 2 — Hydra RDP Brute Force Attack  
**Goal:** Detect repeated failed authentication attempts and account compromise.  
**Technique:** *T1110 – Brute Force*, *T1078 – Valid Accounts*

### 📸 Screenshots
#### Hydra Attack Execution  
![Scenario 2 Hydra](screenshots/scenario2/scenario2/s2-hydra-bruteforce.png)

#### MITRE T1110 Mapping  
![Scenario 2 MITRE](screenshots/scenario2/scenario2/s2-mitre-t1110.png)

#### Windows Admin Terminal  
![Scenario 2 Admin Terminal](screenshots/scenario2/scenario2/s2-admin-terminal.png)

#### Wazuh Brute Force Alerts  
![Scenario 2 Wazuh Alerts](screenshots/scenario2/scenario2/s2-wazuh-alerts.png)

#### Windows Machine IP  
![Scenario 2 Windows IP](screenshots/scenario2/scenario2/s2-windows-ip.png)

---

# 🟥 Scenario 3 — PowerShell Attack (Encoded Commands)  
**Goal:** Detect malicious PowerShell activity, encoded commands, payload execution.  
**Technique:** *T1059.001 – PowerShell*

### 📸 Screenshots
#### PowerShell Execution  
![Scenario 3 Admin PowerShell](screenshots/scenario3/scenario3/s3-admin-powershell.png)

#### Encoded Command  
![Scenario 3 Encoded Command](screenshots/scenario3/scenario3/s3-encoded-command.png)

#### MITRE Mapping  
![Scenario 3 MITRE](screenshots/scenario3/scenario3/s3-mitre-t1059.png)

#### Wazuh Alerts  
![Scenario 3 Wazuh Alerts](screenshots/scenario3/scenario3/s3-wazuh-alerts.png)

---

# 🟨 Scenario 4 — File Integrity Monitoring (Malware Drop Simulation)  
**Goal:** Detect malware-like file writes and unauthorized changes.  
**Technique:** *T1565 – Data Manipulation*, *T1105 – Ingress Tool Transfer*

### 📸 Screenshots
#### File Modification Command  
![Scenario 4 Admin File Change](screenshots/scenario4/scenario4/s4-admin-file-change.png)

#### Sysmon Event ID 11 (FileCreate)  
![Scenario 4 Event 11](screenshots/scenario4/scenario4/s4-filecreate-event11.png)

#### Sysmon Event ID 1  
![Scenario 4 Event 1](screenshots/scenario4/scenario4/s4-eventid1.png)

#### MITRE Mapping  
![Scenario 4 MITRE](screenshots/scenario4/scenario4/s4-mitre-t1565.png)

#### Windows Security Log  
![Scenario 4 Security Log](screenshots/scenario4/scenario4/s4-security-log.png)

---

# 🟧 Scenario 5 — Privilege Escalation Attempt  
**Goal:** Detect elevated processes, UAC interaction, and privileged execution.  
**Technique:** *T1547 – Boot/Logon Autostart*, *T1055 – Process Injection*

### 📸 Screenshots
#### Admin + Privilege Escalation Testing  
![Scenario 5 Admin PrivEsc](screenshots/scenario5/scenario5/s5-admin-priv-esc.png)

#### Windows Security Info  
![Scenario 5 Security Info](screenshots/scenario5/scenario5/s5-security-info.png)

#### Wazuh Alerts  
![Scenario 5 Wazuh](screenshots/scenario5/scenario5/s5-wazuh-alerts.png)

#### MITRE Mapping  
![Scenario 5 MITRE](screenshots/scenario5/scenario5/s5-mitre-priv-esc.png)

---

# 🟪 Scenario 6 — Malware Dropper Simulation  
**Goal:** Detect staged malware components, suspicious commands, and file writes.  
**Technique:** *T1105 – Ingress Tool Transfer*, *T1059 – Execution*

### 📸 Screenshots
#### First Command Execution  
![Scenario 6 First Command](screenshots/scenario6/scenario6/s6-admin-first-command.png)

#### Second Command Execution  
![Scenario 6 Second Command](screenshots/scenario6/scenario6/s6-second-command.png)

#### Third Command Execution  
![Scenario 6 Third Command](screenshots/scenario6/scenario6/s6-third-command.png)

#### MITRE Mapping  
![Scenario 6 MITRE](screenshots/scenario6/scenario6/s6-mitre-t1105.png)

#### Security Log Details  
![Scenario 6 Security Log Info](screenshots/scenario6/scenario6/s6-security-log-info.png)

#### Security Log Summary  
![Scenario 6 Security Log](screenshots/scenario6/scenario6/s6-security-log.png)

---

# 🧠 Skills Demonstrated

- SIEM Configuration (Wazuh)  
- Sysmon Telemetry Tuning  
- Detection Engineering  
- Windows Log Analysis  
- MITRE ATT&CK Mapping  
- Threat Simulation & Red Team Tactics  
- Incident Triage & Event Correlation  
- Blue Team Analysis  

---

# 🎯 Conclusion

This project replicates SOC workflows and demonstrates hands-on experience with real detection pipelines, attacker simulation, alert triage, and log correlation using Wazuh + Sysmon.

---

# 📎 Contact & Collaboration

If you're working on threat detection, blue-team projects, or SIEM engineering — reach out.  
Always happy to collaborate.

