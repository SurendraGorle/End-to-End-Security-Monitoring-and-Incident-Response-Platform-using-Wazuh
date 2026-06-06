# End-to-End Security Monitoring and Incident Response Platform using Wazuh

## Project Overview

This project demonstrates the implementation of an enterprise-style Security Monitoring and Incident Response platform using Wazuh.

The lab includes:

* File Integrity Monitoring (FIM)
* Network Intrusion Detection (Suricata)
* Vulnerability Detection
* Custom Detection Rules
* SSH Brute Force Detection
* VirusTotal Integration
* Active Response
* Auditd Monitoring
* Phishing Detection
* Host Isolation
* Windows Sysmon Integration

## Lab Environment

| Component    | IP Address      |
| ------------ | --------------- |
| Wazuh Server | 192.168.163.130 |
| Ubuntu Agent | 192.168.163.133 |
| Kali Linux   | 192.168.163.129 |

## Current Progress

- [x] Architecture Setup
- [x] File Integrity Monitoring (FIM)
- [x] Network Intrusion Detection (Suricata)
- [x] Vulnerability Detection
- [x] Custom Rules
- [X] SSH Brute Force Detection
- [X] VirusTotal Integration
- [X] Active Response
- [ ] Auditd Monitoring
- [ ] Phishing Detection
- [ ] Host Isolation
- [ ] Sysmon Integration

## Documentation

| Module | Documentation |
|----------|----------|
| File Integrity Monitoring | Documentation/FIM.md |
| Suricata IDS Integration | Documentation/Suricata.md |
| Vulnerability Detection | Documentation/Vulnerability_Detection.md |
| Custom Rules | Documentation/Custom_Rules.md |
| SSH Brute Force Detection | Documentation/Ssh_Bruteforce.md |
| VirusTotal | Documentation/VirusTotal.md |
| Active Response | Documentation/Active_Response.md |

## Completed Security Validations

### File Integrity Monitoring
- File Creation Detection
- File Modification Detection
- File Deletion Detection
- Alert Verification in Wazuh

### Suricata IDS
- Suricata Installation
- Rule Management
- Traffic Monitoring
- Wazuh Integration
- Nmap Reconnaissance Detection
- Alert Correlation

### Vulnerability Detection

- Vulnerability Module Enabled
- Vulnerability Feed Download Verification
- Syscollector Inventory Collection
- Agent Package Inventory Verification
- Vulnerability Scan Execution
- Vulnerability Detection Troubleshooting

### Custom Rules

- Local Rule Creation
- Rule Syntax Validation
- Test Log Generation
- Alert Detection in Wazuh

### SSH Brute Force Detection

- SSH Service Verification
- Failed Login Detection
- Authentication Failure Alert
- Brute Force Correlation Alert

### VirusTotal Integration

- VirusTotal API Configuration
- Wazuh Integration Validation
- File Integrity Monitoring (FIM)
- Benign File Hash Analysis
- EICAR Malware Simulation
- VirusTotal Threat Intelligence Lookup
- Malware Detection Alert
- File Deletion Detection

### Active Response

- Active Response Configuration Backup
- Active Response Script Verification
- Firewall Environment Validation
- firewall-drop Configuration
- Configuration Validation
- Wazuh Manager Restart
- SSH Rule 5710 Verification
- Hydra SSH Brute Force Simulation
- SSH Authentication Failure Detection
- Automated IP Blocking
- Nmap Block Verification
- IPTables Rule Verification

## Project Status

Currently implementing and documenting each security monitoring component with real-world testing, alert generation, investigation workflows, incident response scenarios, and automated response mechanisms.