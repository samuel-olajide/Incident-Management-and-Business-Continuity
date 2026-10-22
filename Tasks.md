# Task 1 Business Impact Analysis
- Build a BIA covering F1 to F5. For each function, record the owner role, users affected, critical resources, dependencies, impact over time, minimum acceptable service, and proposed recovery priority. Include people, premises, suppliers, and information needs.
- Calculate the total estimated disruption cost for 8 hours and 24 hours using the supplied rates and the one-off examination trigger. Show the calculation for each function and the combined total. Explain two limitations of these estimates and distinguish financial impact from learner welfare, reputation, and data integrity.
- Explain how the 11:00 examination and later deadlines affect priorities. Separate business priority from the technical restoration order required by shared infrastructure. Identify at least three important dependency risks.

## 1.1 Purpose and scenario
> The purpose of this Business Impact Analysis (BIA) is to identify the institute’s critical functions, assess the effects of disruption over time, and establish recovery priorities.

> At 08:00 WAT on Day 0, flooding and power failure make the main site and local systems unavailable for 72 hours. Microsoft 365 remains accessible through mobile internet, but local applications depend on AUTH01. An alternate facility offers 25 workstations from 10:00, and two technicians are available for recovery.

## 1.2 Business impact assessment

### BIA: Ownership, users, resources and dependencies
| Function | Owners role | Affected users | Critical resources and dependencies |
| :---- | :---: | :---- | :---- |
| F1: Teaching and assessment | Head of Academics, supported by the Examinations Officer and Assessment Coordinator | 1,800 learners, teaching staff and 120 examination candidates. | LMS01, DB01, exam papers, learner accounts, invigilators, network, AUTH01 and alternate premises. Microsoft 365 and mobile internet support the proposed temporary arrangement. |
| F2: Fees and finance | Finance Manager | Learners, sponsors and finance staff. | FIN01, DB01, payment records, finance officers, network, AUTH01, external payment provider and bank. |
| F3: Admissions and registration | Registrar | Applicants, enrolled learners and registry staff. | REG01, DB01, application records, registry officers, network, AUTH01 and an approved temporary intake method. |
| F4: Staff payroll | HR Manager, supported by the Finance Manager | 90 staff | HR01, DB01, last approved payroll records, HR and finance officers, network, AUTH01 and bank submission process. |
| F5: Records and certificates | Records Officer, accountable to the Registrar | Learners, alumni and registry staff. | FS01, stored records, access lists, request logs, network, AUTH01 and authorised records staff. |

### BIA: Impacts, minimum service and business priority
| Function | Impact over time | Minimum acceptable service and controls | Priority |
| :---- | :---: | :---- | :---- |
| F1 | Examination begins at 11:00. If it cannot proceed acceptably, rescheduling costs ₦120,000. Further disruption increases teaching delays, assessment backlogs and complaints. Rate: ₦60,000/hour. | Provide the assessment through an approved, secure arrangement. The 80 learners using their own devices may access the service through Microsoft 365 if validated. Only 25 of the 40 learners requiring centre workstations can be accommodated at once; arrange additional approved workstations or an authorised alternative for the remaining 15. Maintain identity checks, invigilation, submission logs and controlled release of examination papers. | 1 |
| F2 | Fee confirmation is due at 16:00. Delays may leave learners unable to confirm payments and increase reconciliation disputes. Rate: ₦40,000/hour. | Maintain a restricted temporary payment register using provider reports and numbered provisional receipts. Require maker-checker review, reconcile totals against provider records and record all changes. | 2 |
| F3 | Admissions close at 18:00. Disruption may delay applications and registration changes. Rate: ₦20,000/hour. | Use approved, timestamped Microsoft 365 Forms or another authorised intake method. The Registrar reviews submissions, checks duplicates and verifies records before importing them into REG01. | 3 |
| F4 | Bank submission is due at 12:00 on Day 1. Errors or duplicate instructions could result in incorrect payments. Rate: ₦10,000/hour. | Use the last approved payroll run and verified change forms. HR prepares the file, Finance checks it and an authorised approver signs off. Log the single approved submission to prevent duplicates. | 4 |
| F5 | Records requests have a 48-hour service commitment. Impact increases if requests remain unresolved beyond this period. Rate: ₦5,000/hour. | Log and queue requests. Release records only from verified sources, apply access restrictions and record every release. Urgent requests require Registrar approval if handled using verified copies. | 5 |

## 1.2 Financial impact calculations

> This calculations assume that all five functions remain disrupted from 08:00 and that the supplied hourly rates are separate and non-overlapping. The one-off examination rescheduling cost is added once because the 11:00 deadline falls within both the 8-hour and 24-hour periods.
### Estimated disruption cost without recovery or continuity measures
| Function | Rate per hour | 8-hour working | 8-hour total | 24-hour working | 24-hour total |
| :---- | :---: | :---- | :---- | :---- | :---- |
| F1 | ₦60,000 | ₦60,000 * 8 + ₦120,000 | ₦600,000 | ₦60,000 * 24 + ₦120,000 | ₦1,560,000 |
| F2 | ₦40,000 | ₦40,000 * 8 | ₦320,000 | ₦40,000 * 24 | ₦960,000 |
| F3 | ₦20,000 | ₦20,000 * 8 | ₦160,000 | ₦20,000 * 24 | ₦480,000 |
| F4 | ₦10,000 | ₦10,000 * 8 | ₦80,000 | ₦10,000 * 24 | ₦240,000 |
| F5 | ₦5,000 | ₦5,000 * 8 | ₦40,000 | ₦5,000 * 24 | ₦120,000 |
| Total | ₦135,000 | ₦1,080,000 + ₦120,000 | ₦1,200,000 | ₦3,240,000 + ₦120,000 | ₦3,360,000 |

#### Limitations
The estimates have two limitations:
  1. The rates are fixed, but actual losses can vary. For example, a missed fee confirmation or duplicated payroll file could cost more than the estimated amount, and the cost of correcting errors is not included.
  2. The figures do not measure learner welfare, reputational damage, privacy or data integrity.
**Financial impact** is only one part of the problem. **Learner welfare** is affected when 120 candidates experience exam disruptions. The **institution’s reputation** with parents and sponsors may also suffer. **Data integrity** is equally important because altered certificates or exam records can cause problems for years. Unlike financial losses, these effects are difficult to measure in naira, so learner welfare, reputation, and data integrity must also guide recovery decisions.

## 1.3 Recovery priorities and dependency risks

Business priorities depend on deadlines, the impact of disruption and the consequences of errors. F1 comes first because the examination is at 11:00, only three hours after the disruption. Followed by F2 because fee confirmation is due at 16:00, then F3 because admissions close at 18:00. F4 has a bank-file deadline at 12:00 on Day 1, while F5 has a 48-hour service commitment.

However, business priority is different from technical restoration order. F1–F4 depend on the recovery network, AUTH01 and DB01. The technical sequence is to restore the network, recover AUTH01, complete security and backup checks, restore DB01, and then recover the applications. This means temporary workarounds are needed while technical recovery continues, especially for the 11:00 examination.

**Three key dependency risks are:**
1. **Shared database:** DB01 supports four functions, so a delayed or failed restoration could disrupt several critical services.
2. **Backup security:** The same administrator identity is used for production and network backup administration. If compromised, it could expose both, and the independence of offsite backup access is unclear.
3. **Limited resources:** Only two technicians are available, limiting the ability to work on multiple recovery tasks at once. The alternate facility also has only 25 workstations for 40 learners, which could disrupt the examination.

Later deadlines also require workarounds. Fee and admissions records stop at 07:00, so provider statements and form logs may be needed. Although payroll has more time, an incorrect bank file could be difficult to reverse, making strict approval checks essential.


# Task 2 Recovery objectives and backup design

- Define Recovery Time Objective (RTO), Recovery Point Objective (RPO), and Maximum Tolerable Downtime (MTD). Propose and justify numerical targets for each function. State the service level at which you will declare recovery and leave a justified buffer between technical recovery and the tolerable business disruption limit.
- Calculate the age of the latest recoverable DB01, AUTH01, and FS01 checkpoints at 08:00. Map the resulting potential data-loss windows to the affected functions and compare them with your proposed RPOs. Use the disruption time as the reference point. Explain what can be reconciled from temporary records and what cannot be assumed recoverable.
- Design a backup schedule that addresses the RPO gaps. Specify full and incremental or differential backups, retention, offsite placement, and the exact chain needed to restore DB01. Apply the 3-2-1 principle and include an independent offline or immutable copy, restricted access, encryption, and restoration tests.
- Explain why offsite storage or a live replica alone does not establish recoverability. Define how you will check backup integrity, access independence, and the usability of restored data. Label any unverified assumptions.

## 2.1 Recovery targets

The Recovery Time Objective (RTO) is the target time within which a service should be restored after a disruption. The Recovery Point Objective (RPO) is the maximum acceptable amount of data loss, measured in time before the disruption. The Maximum Tolerable Downtime (MTD) is the longest period a function can remain unavailable before the impact becomes unacceptable.

I set the MTD based on each function’s deadline. I then set the RTO at about two-thirds of the MTD or less. This provides extra time in case restoration is delayed or a recovery step fails.

### Recovery objective matrix
| Function | Tier | RTO | RPO | MTD | Reason for MTD | When recovery is confirmed |
| :---- | :---: | :---- | :---- | :---- | :---- | :---- |
| F1 | T1 | 4H | 1H | 12 h | 11:00 exam, followed by teaching and assessment backlog | LMS01 is running; learner, tutor and exam logins work; rosters are available; Head of Academics approves |
| F2 | T1 | 5H | 1H | 8 h | 16:00 fee confirmation | FIN01 is running; balances match the provider report; Finance Manager approves |
| F3 | T2 | 6H | 1H | 10 h | 18:00 admissions deadline | REG01 is running; application count matches form records; Registrar approves |
| F4 | T2 | 12H | 4H | 24 h | 12:00 on Day 1, with a four-hour buffer before the 28-hour deadline | HR01 is running; staff count of 90 and last-run totals match; HR and Finance Managers approve |
| F5 | T3 | 24H | 24H | 48 h | 48-hour service commitment | FS01 is running; permissions are correct; sample files open; Records Officer approves |
| Supporting: network and AUTH01 | T1 | 2H | 4H | Based on F1 | Required before any application can work | Admin and test logins work; service accounts are valid |

## 2.2 Backup Checkpoint Ages and Data-Loss Gaps

At 08:00, the recoverable data for DB01’s is one hour old, AUTH01’s snapshot is eight hours old, FS01’s backup is nine hours old, and the disconnected full backup is 63 hours old.

DB01 meets the one-hour RPO for F1–F4 only if B01 and all hourly increments pass validation. If they fail, the next usable backup may be B01 at 23:00, causing nine hours of data loss and exceeding the RPO for F1–F3. AUTH01 exceeds its four-hour RPO by four hours, while FS01 meets F5’s 24-hour RPO.

Some missing data may be recovered from external records, emails, forms or resubmissions. However, recovery cannot be guaranteed for data that are only stored locally, including DB01 changes after 07:00, AUTH01 changes after midnight, FS01 changes after 23:00, and records without another copy.

### Checkpoint ages compared with RPOs
| Item | Checkpoint | Age | Calculation | Functions | RPO | Result |
| :---- | :---: | :---- | :---- | :---- | :---- | :---- |
| DB01: B01 + B02 chain	| 07:00 Day 0 |	1 h	| 08:00 − 07:00	| F1–F4	| 1 h (F4: 4 h) |	Meets the target with no margin. Falling back to B01 (9 h old) exceeds the RPO for F1–F3 |
| AUTH01: B03	| 00:00 Day 0	| 8 h	| 08:00 − 00:00	| All five | 4 h	Exceeds the target by 4 h |
| FS01: B04	| 23:00 Day −1 |	9 h	| 08:00 minus 23:00 on the previous day |	F5 | 24 h	| Meets the target |
| Disconnected full backup | 17:00 Day −3	| 63 h | 72 h − 9 h | All, last resort | 1–24 h | Exceeds every target. Use only if newer backups cannot be trusted |

## 2.3 Backup and Restoration Design

DB01 gets a daily full backup at 23:00, followed by hourly increments to meet the one-hour RPO. To restore the 07:00 recovery point, restore B01 and apply increments from 00:00 to 07:00 in order. The entire chain needs to be checked for any missing or damaged backups.
AUTH01 gets snapshots every four hours and after directory changes. FS01 keeps its nightly full backup and adds a 13:00 differential backup.
An additional immutable backup uses a retention lock, separate credentials, MFA and separately stored encryption keys. Backup administration uses a dedicated least-privilege account.
Offsite backups and replicas may still be damaged, undecryptable, compromised or replicate malicious changes.

To verify recovery, the following need to be checked:
- Integrity: Compare hashes, check backup chains and test restores weekly.
- Access: Test recovery with separate credentials and confirm the provider’s security controls.
- Usability: Restore in an isolated network and verify balances, record counts and sample transactions against external records.

### Backup schedule, retention and restore chain
| Data | Full backup | Incremental or differential backup | Retention | Offsite and independent copies | Restore chain |
| :---- | :---: | :---- | :---- | :---- | :---- |
| DB01 | Daily at 23:00 | Hourly increments | 14 daily, 8 weekly and 12 monthly full backups; increments kept for 14 days | Encrypted offsite copy after each job; immutable copies of full and incremental backups with a 30-day lock | B01 (23:00) + increments from 00:00 to 07:00 in order |
| AUTH01 | Daily snapshot at 00:00 | Snapshot every 4 hours and after directory changes | 30 Days | Offsite copy; weekly immutable copy | Latest snapshot + configuration export |
| FS01 | Nightly at 23:00 | Differential backup at 13:00 | 14 daily, 8 weekly and 12 monthly backups | Offsite copy; weekly immutable copy | Nightly full backup + latest differential backup |

### Security Controls and Restoration Tests
| Control | Design |
| :---- | :---: |
| Encryption | AES-256 for stored data and TLS for data in transit. Two key custodians hold the keys separately from the backup console and provider |
| Restricted access | Dedicated backup administrator account, MFA and minimum necessary permissions. Production and backup administration must not share an account |
| Integrity checks | Check hashes and backup catalogues for every job. Check that DB01's backup chain is complete before each daily full backup |
| Access independence | Every quarter, retrieve a backup using credentials that are completely separate from production. Keep written evidence of the provider's controls |
| Restoration tests | Weekly automated DB01 restore check; monthly full DB01 restore in isolation; quarterly tests of all five functions; annual timed recovery exercise from start to finish |
| Usability of restored data | The function owner checks balances, record counts and sample transactions against provider, form and HR records |

### Security Controls and Restoration Tests
| Ref | Assumption | How it will be tested |
| :---- | :---: | :---- |
| UA1 | B01–B04 pass integrity checks; this has only been assumed during the initial exercise | Run hash checks and a test restore. Introduce a simulated problem at minute 30 of the exercise. |
| UA2 | The offsite provider uses access credentials that are independent of production | Obtain written controls and perform a retrieval test using separate credentials. |
| UA3 | The shared administrator account has not been misused | Review sign-in and backup administration logs with the incident response lead. |
| UA4 | Hourly incremental backups can handle the amount of data involved | Review two weeks of backup job logs |
| UA5 | Encryption keys will be available if the main site goes down | Test key recovery with both custodians |
| UA6 | The supplier can meet the expected Warm recovery time of 3–5 hours | Run a timed recovery exercise at the supplier's site |

# Task 3 Recovery strategy and budget
