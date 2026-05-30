# File Integrity Monitoring (FIM)

## Objective

Implement File Integrity Monitoring (FIM) using Wazuh to detect file creation, modification, and deletion events in real time on the Ubuntu Agent.

---

## Architecture

Ubuntu Agent
↓
Wazuh Agent (Syscheck)
↓
Wazuh Manager
↓
Indexer
↓
Dashboard Alert

---

## Prerequisites

* Wazuh Server: 192.168.163.130
* Ubuntu Agent: 192.168.163.133
* Agent connected and active
* SSH access available

---

## Configuration

Backup existing configuration:

```bash
sudo cp /var/ossec/etc/ossec.conf /var/ossec/etc/ossec.conf.bak
```

Added the following entry inside the `<syscheck>` section:

```xml
<directories check_all="yes" report_changes="yes" realtime="yes">/root</directories>
```

Restarted Wazuh Agent:

```bash
sudo systemctl restart wazuh-agent
```

Verified service status:

```bash
sudo systemctl status wazuh-agent
```

Verified logs:

```bash
sudo tail -20 /var/ossec/logs/ossec.log
```

---

## Parameter Explanation

### check_all="yes"

Monitors:

* Permissions
* Owner
* Group
* File size
* Timestamps
* MD5 hash
* SHA1 hash
* SHA256 hash

### report_changes="yes"

Provides detailed information about modified files including changed attributes and hash differences.

### realtime="yes"

Uses Linux filesystem notifications to detect changes immediately instead of waiting for scheduled scans.

---

## Testing

### File Creation Test

Command:

```bash
sudo touch /root/test.txt
```

Result:

* File creation detected
* Decoder: syscheck_new_entry
* Rule ID: 554

---

### File Modification Test

Command:

```bash
echo "Hello Wazuh" | sudo tee -a /root/test.txt
```

Result:

* File modification detected
* Decoder: syscheck_integrity_changed
* Rule ID: 550

Changed attributes:

* Size
* Modification Time
* MD5
* SHA1
* SHA256

---

### File Deletion Test

Command:

```bash
sudo rm /root/test.txt
```

Result:

* File deletion detected
* Decoder: syscheck_deleted
* Rule ID: 553

---

## Alert Analysis

### File Created

Rule ID: 554

Decoder:

```text
syscheck_new_entry
```

Description:

```text
File added to the system
```

---

### File Modified

Rule ID: 550

Decoder:

```text
syscheck_integrity_changed
```

Description:

```text
Integrity checksum changed
```

---

### File Deleted

Rule ID: 553

Decoder:

```text
syscheck_deleted
```

Description:

```text
File deleted
```

---

## SOC Investigation Perspective

FIM helps analysts detect:

* Unauthorized file creation
* Malicious script deployment
* Configuration tampering
* Log deletion attempts
* Persistence mechanisms
* Malware activity

Example:

```text
/root/reverse-shell.py
```

or

```text
/etc/passwd
```

modification events can indicate compromise.

---

## Screenshots

* 01_FIM_Config_Backup.png
* 02_FIM_Config_After.png
* 03_FIM_Agent_Restart.png
* 04_FIM_Before_Test.png
* 05_FIM_Test_File_Created.png
* 06_FIM_File_Added_Alert.png
* 07_FIM_File_Modified.png
* 08_FIM_Modification_Alert.png
* 09_FIM_Before_Delete.png
* 10_FIM_File_Deleted.png
* 11_FIM_Deletion_Alert.png

---

## Key Learnings

* Understanding baseline creation
* File integrity validation using hashes
* Real-time monitoring using Syscheck
* Decoder → Rule → Alert workflow
* Wazuh built-in FIM rules
* SOC investigation using file events
