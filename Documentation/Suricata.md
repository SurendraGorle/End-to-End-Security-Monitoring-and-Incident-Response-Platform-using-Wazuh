# Suricata IDS Integration

## Objective

Integrate Suricata IDS with Wazuh to monitor network traffic, detect suspicious activities, and forward alerts to the Wazuh Dashboard.

---

## Environment

| Component        | Details            |
| ---------------- | ------------------ |
| Wazuh Server     | Ubuntu             |
| Ubuntu Agent     | Suricata Installed |
| Kali Linux       | Attack Simulation  |
| Suricata Version | 6.0.4              |

---

## Installation

### Verify Existing Configuration

* Checked existing network interface configuration.
* Verified connectivity and prerequisites.

### Install Suricata

* Installed Suricata IDS.
* Verified successful installation.

### Rule Management

* Verified ET Open rule set.
* Updated Suricata rules.
* Created configuration backups before modifications.

---

## Configuration

### Interface Configuration

Configured Suricata to monitor:

```yaml
af-packet:
  - interface: ens33
```

### EVE JSON Logging

Verified EVE JSON logging configuration and output generation.

### Service Validation

Validated configuration using:

```bash
sudo suricata -T -c /etc/suricata/suricata.yaml
```

Restarted and verified Suricata service status.

---

## Traffic Validation

Generated network traffic and verified logging for:

* HTTP
* DNS
* TLS
* Flow
* Alert Events

Confirmed event generation in:

```text
/var/log/suricata/eve.json
```

---

## Wazuh Integration

Configured Wazuh Agent to monitor Suricata logs.

Verified:

* Event collection
* Alert forwarding
* Dashboard visibility

---

## Attack Simulation

### Nmap Reconnaissance

Source:

* Kali Linux

Target:

* Ubuntu Agent

Activities:

* TCP SYN Scan
* Service Enumeration

Results:

* Nmap traffic detected by Suricata.
* Events written to eve.json.
* Alerts successfully forwarded to Wazuh.

---

## Outcome

Successfully implemented and validated end-to-end Suricata IDS integration with Wazuh for centralized security monitoring and alert management.

---

## Screenshots

### 01_Pre_Installation_Check
![01_Pre_Installation_Check](../Screenshots/Suricata/01_Pre_Installation_Check.png)

### 02_Suricata_Installed
![02_Suricata_Installed](../Screenshots/Suricata/Suricata/02_Suricata_Installed.png)

### 03_Suricata_Config_Test_Failed
![03_Suricata_Config_Test_Failed](../Screenshots/Suricata/03_Suricata_Config_Test_Failed.png)

### 04_Rules_Directory_Verification
![04_Rules_Directory_Verification](../Screenshots/Suricata/04_Rules_Directory_Verification.png)

### 05_Missing_Rule_File_Verification
![05_Missing_Rule_File_Verification](../Screenshots/Suricata/05_Missing_Rule_File_Verification.png)

### 06_Suricata_Rules_Updated
![06_Suricata_Rules_Updated](../Screenshots/Suricata/06_Suricata_Rules_Updated.png)

### 07_Suricata_Rule_File_Verified
![07_Suricata_Rule_File_Verified](../Screenshots/Suricata/07_Suricata_Rule_File_Verified.png)

### 08_Suricata_Config_Backup
![08_Suricata_Config_Backup](../Screenshots/Suricata/08_Suricata_Config_Backup.png)

### 09_Rule_Path_Updated
![09_Rule_Path_Updated](../Screenshots/Suricata/09_Rule_Path_Updated.png)

### 10_Config_Test_Success
![10_Config_Test_Success](../Screenshots/Suricata/10_Config_Test_Success.png)

### 11_Suricata_Service_Running
![11_Suricata_Service_Running](../Screenshots/Suricata/11_Suricata_Service_Running.png)

### 12_Eve_JSON_Verified
![12_Eve_JSON_Verified](../Screenshots/Suricata/12_Eve_JSON_Verified.png)

### 13_Eve_JSON_Monitoring_Check
![13_Eve_JSON_Monitoring_Check](../Screenshots/Suricata/13_Eve_JSON_Monitoring_Check.png)

### 14_Wazuh_Config_Backup
![14_Wazuh_Config_Backup](../Screenshots/Suricata/14_Wazuh_Config_Backup.png)

### 15_Eve_JSON_Added_To_Wazuh
![15_Eve_JSON_Added_To_Wazuh](../Screenshots/Suricata/15_Eve_JSON_Added_To_Wazuh.png)

### 16_Wazuh_Agent_Restart
![16_Wazuh_Agent_Restart](../Screenshots/Suricata/16_Wazuh_Agent_Restart.png)

### 17_Wazuh_Agent_Log_Check
![17_Wazuh_Agent_Log_Check](../Screenshots/Suricata/17_Wazuh_Agent_Log_Check.png)

### 18_Eve_JSON_Event_Verification
![18_Eve_JSON_Event_Verification](../Screenshots/Suricata/18_Eve_JSON_Event_Verification.png)

### 19_Interface_Mismatch_Identified
![19_Interface_Mismatch_Identified](../Screenshots/Suricata/19_Interface_Mismatch_Identified.png)

### 20_Interface_Config_Updated
![20_Interface_Config_Updated](../Screenshots/Suricata/20_Interface_Config_Updated.png)

### 21_Packet_Capture_Verified
![21_Packet_Capture_Verified](../Screenshots/Suricata/21_Packet_Capture_Verified.png)

### 22_Suricata_Traffic_Inspection_Verified
![22_Suricata_Traffic_Inspection_Verified](../Screenshots/Suricata/22_Suricata_Traffic_Inspection_Verified.png)

### 23_Suricata_Alert_Received_In_Wazuh
![23_Suricata_Alert_Received_In_Wazuh](../Screenshots/Suricata/23_Suricata_Alert_Received_In_Wazuh.png)

### 24_Nmap_Scan_From_Kali
![24_Nmap_Scan_From_Kali](../Screenshots/Suricata/24_Nmap_Scan_From_Kali.png)

### 25_Nmap_Traffic_Detected_By_Suricata
![25_Nmap_Traffic_Detected_By_Suricata](../Screenshots/Suricata/25_Nmap_Traffic_Detected_By_Suricata.png)

### 26_Suricata_Alert_Forwarded_To_Wazuh
![26_Suricata_Alert_Forwarded_To_Wazuh](../Screenshots/Suricata/26_Suricata_Alert_Forwarded_To_Wazuh.png)