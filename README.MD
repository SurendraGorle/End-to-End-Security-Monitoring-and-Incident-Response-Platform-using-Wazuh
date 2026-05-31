# End-to-End Security Monitoring and Incident Response Platform using Wazuh

## Project Overview

This project demonstrates the implementation of an enterprise-style Security Monitoring and Incident Response platform using Wazuh.

The lab includes:

* File Integrity Monitoring (FIM)
* Network Intrusion Detection (Suricata)
* Vulnerability Detection
* Auditd Monitoring
* Custom Detection Rules
* SSH Brute Force Detection
* Active Response
* VirusTotal Integration
* Phishing Detection
* Host Isolation
* Windows Sysmon Integration

## Lab Environment

| Component    | IP Address      |
| ------------ | --------------- |
| Wazuh Server | 192.168.163.130 |
| Ubuntu Agent | 192.168.163.133 |
| Kali Linux   | 192.168.163.129

## Current Progress

* [x] Architecture Setup
* [x] File Integrity Monitoring (FIM)
* [x] Network Intrusion Detection (Suricata)
* [ ] Vulnerability Detection
* [ ] Auditd Monitoring
* [ ] Custom Rules
* [ ] SSH Brute Force Detection
* [ ] Active Response
* [ ] VirusTotal Integration
* [ ] Phishing Detection
* [ ] Host Isolation
* [ ] Sysmon Integration

## Documentation

| Module | Documentation |
|----------|----------|
| File Integrity Monitoring | Documentation/FIM.md |
| Suricata IDS Integration | Documentation/Suricata.md |

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

## Project Status

Currently implementing and documenting each security monitoring component with real-world testing, alert generation, investigation workflows, and incident response scenarios.
