# Windows Brute-Force Attack Investigation

## 1. Incident Overview
- Alert: Multiple Failed Windows Logons
- Severity: Medium — preliminary
- Host: WIN-SRV-01 (192.0.2.10)
- Source IP: 203.0.113.25
- Time: 09 October 2026, 10:00–10:10 UTC
- Event ID: 4625
- MITRE ATT&CK: T1110 — Brute Force
- Environment: Simulated lab

All IP addresses and activity in this report are illustrative.

## 2. Alert Description
A Windows server generated repeated failed authentication events from one source IP. The objective is to assess whether the activity is consistent with brute-force behavior and check for evidence of successful authentication.

## 3. Evidence Collected
- 30 simulated failed logon events in the scenario.
- Three targeted usernames.
- One source IP in the sample.
- No Event ID 4624 success event in the supplied sample.
- No evidence provided to establish account compromise.

## 4. Investigation
### Validate the alert
Event ID 4625 records a failed Windows logon. The repeated events warrant further investigation.

### Identify source and accounts
Repeated attempts from one source against multiple accounts are consistent with possible password guessing or brute-force behavior.

### Check successful authentication
No matching Event ID 4624 is present in the supplied sample. This does not prove that no successful login occurred outside the available dataset or time window.

### Assess impact
The sample does not establish account compromise, privilege escalation, or unauthorized access. Correlate with other authentication, endpoint, and network logs before reaching a final determination.

## 5. MITRE ATT&CK
T1110 — Brute Force is a plausible mapping. The available sample does not establish a specific sub-technique.

## 6. Findings
- Repeated failed logons appear in the simulated dataset.
- The pattern is consistent with potential brute-force activity.
- No successful authentication was identified in the supplied sample.
- Compromise is not confirmed.

## 7. Recommended Actions
1. Search for successful logons from the source during and after the alert window.
2. Validate targeted accounts and check for account lockouts.
3. Correlate with firewall, VPN, EDR, and SIEM records.
4. Apply blocking or account-protection measures according to organizational policy.
5. Tune alert thresholds against the normal baseline.

## 8. SOC Disposition
Suspicious authentication activity — further validation required. The sample supports a possible brute-force attempt but does not establish compromise. A real incident should be closed or escalated according to correlated evidence and SOC procedures.

## 9. Disclaimer
This is a simulated educational case study. It does not describe a real client incident.
