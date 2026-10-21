# Task 1 Business Impact Analysis
- Build a BIA covering F1 to F5. For each function, record the owner role, users affected, critical resources, dependencies, impact over time, minimum acceptable service, and proposed recovery priority. Include people, premises, suppliers, and information needs.
- Calculate the total estimated disruption cost for 8 hours and 24 hours using the supplied rates and the one-off examination trigger. Show the calculation for each function and the combined total. Explain two limitations of these estimates and distinguish financial impact from learner welfare, reputation, and data integrity.
- Explain how the 11:00 examination and later deadlines affect priorities. Separate business priority from the technical restoration order required by shared infrastructure. Identify at least three important dependency risks.

## 1.1 Purpose and scenario
> The purpose of this Business Impact Analysis (BIA) is to identify the institute’s critical functions, assess the effects of disruption over time, and establish recovery priorities.

> At 08:00 WAT on Day 0, flooding and power failure make the main site and local systems unavailable for 72 hours. Microsoft 365 remains accessible through mobile internet, but local applications depend on AUTH01. An alternate facility offers 25 workstations from 10:00, and two technicians are available for recovery.

## 1.2 Business impact assessment
| Evidence | Time WAT | Confirmed observation | Working hypothesis or unresolved question |
| :---- | :---: | :---- | :---- |
| E01 | Day -1, 16:40 | A finance officer opened an unexpected payroll attachment on FIN-PC07. | The payroll attachment may have introduced malware, but the malicious code execution is yet to be verified. |
| E02 | Day 0, 01:15 | The finance officer account signed in from an unfamiliar IP and new device. | The account may have been compromised, but the MFA status and the user involvement is yet to be known. |
| E03 | Day 0, 01:35 | The `svc_backup` made remote administrator logons to FS01 and BAK01 outside its usual schedule. | The admin account may have been misused to access backups and file server. |
| E04 | Day 0, 01:50 | FIN-PC07 uploaded 1.2 GB over HTTPS to unfamiliar cloud storage. | This could be data exfiltration, but the uploaded contents are currently unknown. |
| E05 | Day 0, 02:00 | Backup jobs for FS01 and LMS01 reports success. | The backups may be unusable or compromised. However, a successful job does not confirm recoverability. |
| E06 | Day 0, 08:30 | Mass file changes occur on FIN-PC07 and FS01 shared folders contain `.locked` files and a ransom note. | There is a suspected ransomware, but the malware family is yet to be confirmed. |
| E07 | Day 0, 08:40 | The portal login page loads, but learners cannot open materials or submit assessments. | The portal may have been affected by the `locked` files on FS01, as the portal login page is on the server. |
| E08 | Day 0, 08:45 | The incident contact list on FS01 is inaccessible. Staff phones are available.  | The trustworthiness of corporate email is unverified, and the incident team cannot rely on the stored contact lists . |
