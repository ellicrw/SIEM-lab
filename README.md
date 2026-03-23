# Wazuh SIEM Homelab Project

## Overview

This project demonstrates the deployment and validation of a SIEM solution using Wazuh in a homelab. The focus is on File Integrity Monitoring (FIM) to detect unauthorized file activity on an endpoint.

The lab validates that Wazuh can generate actionable alerts from real file system changes, simulating a basic blue team detection use case.

---

## Objectives

* Deploy a working Wazuh SIEM environment
* Configure an endpoint with monitoring
* Implement File Integrity Monitoring (FIM)
* Generate real alerts from file activity
* Analyze and validate detection results

---

## Lab Architecture

**Components:**

* Wazuh Manager (SIEM server)
* Wazuh Agent (endpoint)
* Wazuh Dashboard (web interface)

**Environment:**

* Virtualized homelab
* Linux (server), Windows (agent)

---

## Installation Summary

### Wazuh Server

* Deployed Wazuh all-in-one stack
* Verified services were operational:

  * wazuh-manager
  * wazuh-indexer
  * wazuh-dashboard

### Agent Setup

* Installed Wazuh agent on endpoint
* Registered agent to manager
* Confirmed connectivity and log ingestion

---

## Configuration

### File Integrity Monitoring (FIM)

Configured real-time monitoring for a user directory:

```
<directories realtime="yes">C:\Users\revye\Documents\StudyLog</directories>
```

Additional monitoring included:

* Startup directory
* User-accessible file paths

---

## Detection Use Case: File Integrity Monitoring

### Scenario

Simulated unauthorized file activity within a monitored directory to test detection capabilities.

### Test Actions

* Created a file
* Modified a file
* Deleted a file

### Detection Results

Wazuh successfully generated alerts for:

* File creation
* File modification
* File deletion

Each alert included:

* File path
* Timestamp
* Type of change
* Reporting agent

---

## Detection Validation

This lab confirmed that Wazuh FIM can detect and log file system changes in real time.

**Observed Behavior:**

* Alerts triggered immediately after file activity
* Events visible in dashboard
* Multiple event types correctly categorized

**Conclusion:**
The SIEM effectively detects unauthorized file changes, demonstrating a core host-based detection capability used in SOC environments.

---

## Sample Alert (Example)

```
File added: C:\Users\<username>\Documents\StudyLog\test.txt
```

---

## Analysis

This detection use case is relevant for identifying:

* Persistence mechanisms (malicious files placed on system)
* Insider threats (unauthorized file manipulation)
* Suspicious activity in sensitive directories

FIM provides visibility into changes that are often missed by traditional logging alone.

---

## Screenshots

Include the following evidence:

* Wazuh dashboard overview
* File created alert
* File modified alert
* File deleted alert
* FIM configuration view

---

## Limitations

* Lab environment has been decommissioned
* Single data source (FIM only)
* No advanced correlation or custom rules

---

## Future Improvements

* Add Sysmon for detailed Windows telemetry
* Create custom Wazuh detection rules
* Map alerts to MITRE ATT&CK techniques
* Simulate attacker behavior (persistence, privilege escalation)
* Build dashboards for alert triage

---

## Skills Demonstrated

* SIEM deployment (Wazuh)
* Endpoint monitoring
* File Integrity Monitoring (FIM)
* Alert analysis
* Detection validation

---

## Conclusion

This project demonstrates the ability to deploy a SIEM, configure a detection control, and validate its effectiveness using real activity. It reflects foundational skills required for a Security Operations Center (SOC) Analyst role.

---

## Author

Homelab Security Project
