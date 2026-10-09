# Windows Brute-Force Attack Investigation

## 📌 Project Overview

This project demonstrates a practical Security Operations Center (SOC) investigation of simulated Windows authentication logs to identify potential brute-force activity.

The investigation focuses on analyzing repeated failed logon attempts, identifying the source IP and targeted accounts, checking for successful authentication, and documenting findings and recommended response actions.

## 🎯 Objectives

* Investigate repeated Windows authentication failures.
* Analyze Windows Security Event ID 4625 (Failed Logon).
* Check for successful authentication using Event ID 4624.
* Identify suspicious source IP and targeted accounts.
* Map the observed behavior to MITRE ATT&CK.
* Document investigation findings and SOC recommendations.

## 🛠️ Tools and Technologies

* Windows Security Event Logs
* SIEM investigation concepts
* CSV log analysis
* MITRE ATT&CK Framework
* GitHub Markdown documentation

## 🔍 Investigation Scenario

A Windows server generates multiple failed logon events from a single source IP targeting several usernames within a short period.

The investigation examines whether the pattern is consistent with brute-force behavior and whether the available evidence indicates a successful login.

**Environment:** Simulated lab
**Host:** WIN-SRV-01
**Host IP:** 192.0.2.10
**Source IP:** 203.0.113.25
**Event ID:** 4625
**MITRE ATT&CK Technique:** [T1110 — Brute Force](https://attack.mitre.org/techniques/T1110/)

The IP addresses and activity in this scenario are illustrative and do not represent a real security incident.

## 🧪 Investigation Methodology

1. **Alert validation:** Review the failed authentication events and investigation time window.
2. **Source analysis:** Identify the source IP associated with repeated failures.
3. **Account analysis:** Determine which usernames were targeted and how frequently.
4. **Authentication validation:** Check the available logs for successful logons (Event ID 4624).
5. **Threat assessment:** Evaluate whether the observed pattern is consistent with brute-force activity.
6. **Incident documentation:** Record evidence, findings, limitations, and recommended actions.

## 📊 Key Findings

* The simulated scenario contains 30 failed logon events.
* Three usernames are targeted in the sample.
* The observed failures originate from one simulated source IP.
* No successful logon event is present in the supplied sample.
* The activity is consistent with potential brute-force behavior, but account compromise is not established.

These findings describe the exercise's simulated dataset, not independently verified production telemetry.

## 🛡️ Recommended Response

* Review authentication logs for successful logons from the same source.
* Validate targeted accounts and check for account lockouts.
* Correlate the activity with firewall, VPN, endpoint, and SIEM records.
* Apply blocking or account-protection measures according to organizational policy.
* Tune detection thresholds based on the environment's normal authentication baseline.

## 📁 Project Structure

```text
windows-brute-force-investigation/
├── README.md
├── windows-brute-force-investigation.md
└── windows-auth-events.csv
```

## 📚 Learning Outcomes

This project demonstrates fundamental SOC investigation practices, Windows authentication log analysis, suspicious activity assessment, MITRE ATT&CK mapping, and evidence-based incident documentation.

## ⚠️ Disclaimer

This project is intended for educational and portfolio purposes only. All activity and log data are simulated. No real client logs, confidential information, or production credentials are included.

