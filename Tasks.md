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


