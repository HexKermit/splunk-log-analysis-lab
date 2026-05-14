# Suspicious Authentication Investigation Using Splunk

![Status](https://img.shields.io/badge/Status-Complete-green)
![Tools](https://img.shields.io/badge/Tools-Splunk%20%7C%20Linux%20CLI-blue)
![MITRE](https://img.shields.io/badge/MITRE-T1110-red)

## Threat Overview

This investigation focused on identifying suspicious authentication activity within IIS log data using Splunk and Linux command-line analysis techniques.

The objective was to validate failed authentication patterns and correlate suspicious login behavior across multiple analysis workflows.

---

## MITRE ATT&CK Mapping

| Technique | ID | Tactic |
|---|---|---|
| Brute Force | T1110 | Credential Access |
| Valid Accounts | T1078 | Defense Evasion |

---

## Investigation Timeline

1. Imported IIS authentication logs into Splunk
2. Validated source type parsing behavior
3. Searched failed authentication events
4. Correlated repeated login attempts
5. Parsed raw logs using Linux CLI tools
6. Validated suspicious authentication activity

---

## Technical Findings

### Key Findings

- Multiple failed authentication events were identified using IIS status code analysis
- Repeated login attempts indicated possible brute-force activity
- Linux CLI analysis validated authentication event frequency
- Splunk ingestion workflows successfully parsed IIS log data

---

## IOC Summary

| Indicator | Type |
|---|---|
| Status Code 530 | Failed Authentication |
| IIS Authentication Logs | Log Source |
| Repeated Login Attempts | Suspicious Activity |

---

## SPL Queries Used

```spl
index=main sourcetype=iis status=530
| stats count by src_ip, user
| where count > 10
```

---

## Detection Recommendations

- Monitor repeated IIS authentication failures
- Alert on abnormal login attempt spikes
- Correlate authentication failures across multiple systems
- Investigate unusual authentication behavior patterns

---

## Investigation Evidence

### Splunk Failed Login Analysis

![Splunk Failed Login Analysis](screenshots/splunk/splunk-failed-login-analysis.png)

---

### Linux Log Parsing Analysis

![Linux Log Parsing Analysis](screenshots/linux-analysis/linux-log-parsing-analysis.png)

---

### Splunk Log File Selection

![Splunk Log File Selection](screenshots/splunk/splunk-log-file-selection.png)

---

### Splunk Source Type Analysis

![Splunk Source Type Analysis](screenshots/splunk/splunk-source-type-analysis.png)

---

## Environment

| Component | Details |
|---|---|
| SIEM | Splunk |
| Operating System | Windows / Kali Linux |
| Analysis Tools | Splunk, Linux CLI |
| Log Source | IIS Logs |
