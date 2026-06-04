# VirusTotal Integration with Wazuh

## Objective

Integrate VirusTotal Threat Intelligence with Wazuh SIEM to automatically analyze file hashes detected through File Integrity Monitoring (FIM) and identify malicious files.

---

## Lab Environment

| Component | Details |
|------------|-----------|
| SIEM | Wazuh v4.7.5 |
| Wazuh Manager | Ubuntu Server |
| Agent | Ubuntu Endpoint |
| Threat Intelligence | VirusTotal API |
| Monitoring | File Integrity Monitoring (FIM) |
| Test Malware | EICAR Test File |

---

## Detection Flow

File Created/Modified
↓
Wazuh FIM Detection
↓
Hash Calculation (MD5/SHA1)
↓
VirusTotal API Lookup
↓
Threat Intelligence Analysis
↓
Malicious/Benign Verdict
↓
Alert Generated in Wazuh Dashboard

---

## 1. Backup Existing Configuration

Created backup of Wazuh configuration file before modifications.

### Evidence

![01](../Screenshots/VirusTotal/01_OSSEC_Config_Backup.png)

---

## 2. Configure VirusTotal Integration

Added VirusTotal API integration in:

```xml
/var/ossec/etc/ossec.conf
```

```xml
<integration>
  <name>virustotal</name>
  <api_key>YOUR_API_KEY</api_key>
  <group>syscheck</group>
  <alert_format>json</alert_format>
</integration>
```

### Evidence

![02](../Screenshots/VirusTotal/02_VirusTotal_Integration_Files_Verified.png)

---

## 3. Restart Wazuh Manager

Validated configuration and restarted Wazuh services.

### Evidence

![03](../Screenshots/VirusTotal/03_VirusTotal_Config_Validated.png)

---

## 4. File Integrity Monitoring Test

Created a test file in monitored directory.

Command:

```bash
sudo touch /root/vt_test_file.txt
```

### Evidence

![04](../Screenshots/VirusTotal/04_FIM_Test_File_Created.png)

---

## 5. FIM Alert Detection

Wazuh detected file creation successfully.

### Evidence

![05](../Screenshots/VirusTotal/05_FIM_File_Creation_Detected.png)

---

## 6. VirusTotal Lookup Result

VirusTotal checked the file hash and returned a clean verdict.

Result:

```text
No positives found
```

### Evidence

![06](../Screenshots/VirusTotal/06_VirusTotal_Lookup_Result.png)

---

## 7. Malware Simulation using EICAR

Downloaded EICAR test malware file.

Command:

```bash
curl -O https://secure.eicar.org/eicar.com.txt
```

### Evidence

![07](../Screenshots/VirusTotal/07_EICAR_File_Downloaded.png)

---

## 8. EICAR File Detected by FIM

Wazuh detected file creation in real time.

### Evidence

![08](../Screenshots/VirusTotal/08_EICAR_FIM_Detected.png)

---

## 9. VirusTotal Malware Detection

VirusTotal identified the EICAR file as malicious.

Detection Result:

```text
65 / 67 Security Engines Detected Malware
```

### Evidence

![09](../Screenshots/VirusTotal/09_EICAR_VirusTotal_Detected.png)

---

## 10. File Deletion Detection

Deleted EICAR file and verified FIM alert generation.

Command:

```bash
rm eicar.com.txt
```

### Evidence

![10](../Screenshots/VirusTotal/10_EICAR_File_Deleted.png)

---

## Outcome

Successfully integrated VirusTotal Threat Intelligence with Wazuh SIEM.

Capabilities demonstrated:

- File Integrity Monitoring (FIM)
- Real-Time File Monitoring
- Hash-Based Reputation Analysis
- Threat Intelligence Integration
- Malware Detection
- Security Event Correlation
- Incident Investigation Workflow

---

## Skills Demonstrated

- Wazuh SIEM Administration
- Threat Intelligence Integration
- VirusTotal API Configuration
- File Integrity Monitoring (FIM)
- Linux Administration
- Malware Detection
- Security Monitoring
- Incident Analysis
