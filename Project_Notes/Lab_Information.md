Project Name:
End-to-End Security Monitoring and Incident Response Platform using Wazuh

Wazuh Server:
192.168.163.130

Ubuntu Agent:
192.168.163.133

Current Status:
Agent Connected

Start Date:
2026-05-30

## Completed Modules

### 1. File Integrity Monitoring (FIM)

Status: Completed

Validation:
- File Creation Detection
- File Modification Detection
- File Deletion Detection
- Alert Generation in Wazuh Dashboard

Documentation:
- Documentation/FIM.md

---

### 2. Suricata IDS Integration

Status: Completed

Validation:
- Suricata Installation
- Rule Updates
- eve.json Verification
- Wazuh Integration
- HTTP/DNS/TLS Traffic Monitoring
- Nmap Scan Detection
- Alert Forwarding to Wazuh

Documentation:
- Documentation/Suricata.md

---

### 3. Vulnerability 

Status: Completed

Process:

* Vulnerability Detection module enabled on Wazuh Manager.
* Vulnerability feeds downloaded successfully.
* Syscollector verified and collecting software inventory.
* Ubuntu Agent software inventory collected (732 packages).
* Vulnerability scans executed successfully.
* No CVE entries generated during lab testing.
* Documentation and screenshots completed.

Documentation:
  - Documentation/Vulnerability.md

  ---

  ### 4. Custom Rules:

Status : Completed

Process:

- Custom rule created in local_rules.xml
- Rule ID: 100100
- Trigger condition: Custom_Test_Alert
- Rule syntax validated using wazuh-logtest
- Test log generated using logger command
- Alert successfully detected in Wazuh Dashboard

Documentation:
   - Documentation/Custom_Rules.md

   ---

### SSH Brute Force Detection:

Status : Completed

Process:

• SSH Service Verification
• Failed Login Attempt Generation
• Authentication Failure Detection
• SSH Alert Generation in Wazuh
• Brute Force Correlation Detection

Documentation:
  - Documentation/Ssh_Bruteforce.md

---
