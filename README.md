# Home-SOC-Wazuh-Sysmon-Detection-Lab
Threat Detection Lab using Wazuh SIEM, Sysmon, and Kali Linux
# 🛡️ Home SOC Project – Wazuh + Sysmon + Kali Linux  
**Threat Detection | Incident Response | MITRE ATT&CK Mapping**

This project simulates real-world attack behavior in a controlled home lab while using Wazuh SIEM and Sysmon to detect, analyze, and correlate malicious activity. It includes brute force attacks, PowerShell abuse, malware drops, persistence techniques, and unauthorized service installations.

---

## 🏗️ Environment Setup

### 🔹 Windows 11 Endpoint
- Sysmon installed + custom sysmonconfig.xml  
- Wazuh agent installed  
- PowerShell logging enabled

### 🔹 Kali Linux Attacker Machine
- Used Hydra, Nmap, PowerShell injection payloads, and persistence simulation

### 🔹 Wazuh SIEM
- Centralized log analysis  
- Custom rule tuning  
- MITRE ATT&CK–mapped alerts  
- JSON + correlation engine review  

---

## 🎯 Attack Scenarios Simulated

### 1️⃣ Unauthorized Software Installation  
**Event:** Chrome installer created a new Windows service  
**Detection:** Sysmon Event ID 7045  
**Alert:** "New Windows Service Created"

---

### 2️⃣ RDP Brute Force Attack (MITRE T1110 – Credential Access)  
**Tool:** Hydra  
**Behavior:** Multiple login failures followed by successful authentication  
**Detections:**  
- Multiple failed logon attempts  
- "Unknown user or bad password"  
- High-severity MITRE-mapped correlation  

---

### 3️⃣ PowerShell Execution Attacks (MITRE T1059)  
Simulated:
- Encoded commands  
- Download/execution payloads  
- PowerShell spawning PowerShell  

Wazuh Alerts:
- Suspicious encoded command  
- Possible malware execution  
- Script-block logging  

---

### 4️⃣ Malware Drop Simulation (Initial Access)  
**Behavior:** Custom executable placed into user temp/downloads folders  
**Detections:**  
- File creation (Event ID 11)  
- High severity “Executable file dropped in folder commonly used by malware”

---

### 5️⃣ Privilege Escalation Attempt  
Triggered events involving:
- `consent.exe`  
- Elevated process creation  
**Detection:** Sysmon Event ID 1 + Wazuh process creation alerts  

---

### 6️⃣ Persistence via Scheduled Task (MITRE T1053.005)  
**Command:**  
`SchTasks /Create /SC DAILY /TN "Updater" /TR "malware-test.exe"`  

**Detection:**  
- Task registration  
- Sysmon taskschd.dll module load  
- Wazuh scheduled-task rule firing  

---

## 🔍 Key Skills Demonstrated

- Detection engineering with Wazuh  
- Log analysis (Windows + Sysmon)  
- Endpoint monitoring  
- MITRE ATT&CK mapping  
- Incident response triage workflow  
- Hands-on adversary simulation  
- PowerShell for attacker tradecraft  
- Custom SIEM rule tuning  

---

## 📂 Repository Contents

- Attack screenshots  
- JSON event logs  
- Sysmon config  
- OSSEC/Wazuh rule customizations  
- Full write-up of each detection  
- MITRE technique references  

---

## 📎 Contact

If you're working on SOC, detection engineering, or threat hunting, feel free to reach out.  
Always happy to collaborate on blue-team projects.
