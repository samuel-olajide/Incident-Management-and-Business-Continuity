**INTERNATIONAL CYBERSECURITY AND DIGITAL FORENSICS ACADEMY**

# **Business Continuity and Disaster Recovery Assignment**

## GRC205  Incident Management and Business Continuity  Week 21

Act as the Business Continuity and Disaster Recovery Coordinator for a fictional training institute whose main site becomes unavailable. Use the supplied data to assess business impact, set recovery objectives, select an affordable strategy, and demonstrate whether the proposed recovery sequence can meet business needs.

| Assessment detail | Requirement |
| :---- | :---- |
| Assessment type | Individual assignment  |  Complete all six tasks |
| Total marks and weighting | 100 marks  |  30% of the final course grade |
| Submission | One Word document through the E-Campus assessment page |
| Deadline | As published for this assessment in E-Campus |
| Suggested effort | 12 to 16 hours |

## **Learning outcomes**

* Conduct a Business Impact Analysis (BIA) and prioritise critical functions.  
* Justify recovery time and recovery point objectives using business requirements.  
* Compare alternate sites and backup strategies against cost and capability.  
* Coordinate continuity, disaster recovery, and incident response responsibilities.  
* Test recovery assumptions and turn findings into measurable improvements.

## **Report requirements**

Submit 3,000 to 3,500 words, excluding the cover, tables, reference list, and appendices. Present the six tasks in order. Include calculations, the BIA and recovery objective matrices, a strategy comparison and budget, a coordinated plan, a recovery schedule, an exercise log, and a performance dashboard.

The six tasks carry 95 marks. Report quality and referencing carry 5 marks. A score of 80 out of 100 contributes 24 out of the available 30 points to your final course score.

# **Business context and impact data**

## **Northbridge Skills Institute**

Northbridge is a fictional education provider with 1,800 learners and 90 staff. At 08:00 WAT on Day 0, a Monday, flooding and a power failure make the main site and its local systems unavailable. Facilities estimates that the site will remain inaccessible for 72 hours. No cyberattack has been confirmed. You coordinate continuity and recovery from the time of disruption.

Microsoft 365 identity and email remain available through mobile internet. Local applications use a separate local directory, AUTH01. An alternate facility can provide 25 workstations from 10:00. Of the 120 learners scheduled for an 11:00 examination, 40 need centre workstations and 80 can use their own devices. Two technicians are available for disaster recovery. Business coordinators can organise temporary services and learner support.

## **Functions requiring a BIA**

| Function and local systems | Operational constraint and impact | NGN per hour |
| :---- | :---- | :---: |
| F1  Teaching and assessmentLMS01 and DB01 | The examination starts at 11:00. If no acceptable assessment service is available by then, add a one-off rescheduling cost of NGN 120,000. Learner access and assessment integrity matter. | 60,000 |
| F2  Fees and financeFIN01 and DB01 | Fee confirmation is due by 16:00 on Day 0\. The external payment provider remains available, but local receipts and wallet records cannot be updated. Reconciliation is necessary. | 40,000 |
| F3  Admissions and registrationREG01 and DB01 | Admissions close at 18:00 on Day 0\. New applications and registration changes cannot be entered into the local system. | 20,000 |
| F4  Staff payrollHR01 and DB01 | The bank submission deadline is 12:00 on Day 1\. Incorrect or duplicate payroll instructions could affect staff and require manual correction. | 10,000 |
| F5  Records and certificatesFS01 | Certificate and record requests have a 48-hour internal service commitment. Files must retain integrity and access restrictions. | 5,000 |

For Task 1, treat the hourly amounts as separate, non-overlapping incremental disruption costs. Apply them for the first 24 hours and add the examination rescheduling cost once when its trigger is met. Calculate the 8-hour and 24-hour impact assuming no recovery or continuity measures. These are exercise estimates, not observed losses.

## **Dependencies and minimum service**

F1 to F4 require the recovery network, AUTH01, DB01, and their respective application. F5 requires the network, AUTH01, and FS01. All functions also depend on available staff, secure access, and communication. Define a workable minimum service for each function, including the approval and record controls for any manual process.

# **Recovery evidence and planning options**

## **Available backup checkpoints**

At the 08:00 disruption, the offsite backup catalogue contains the following items. Task 5 uses a baseline drill in which these items pass integrity checks. The tabletop injects later test what happens when that assumption fails.

| Item | Data checkpoint WAT | Recovery dependency |
| :---- | :---- | :---- |
| B01  DB01 full backup | 23:00, Day minus 1 | Base for all four business applications. |
| B02  DB01 incremental chain | 07:00, Day 0 | Requires B01 and every required incremental through 07:00. This is the latest recoverable business-data point. |
| B03  AUTH01 snapshot | 00:00, Day 0 | Local directory and configuration state. |
| B04  FS01 full backup | 23:00, Day minus 1 | Record and certificate files. |

A further disconnected full backup exists at 17:00 on Day minus 3\. Production and network backup administration share an administrator identity. The offsite provider holds the encrypted copies, but its access-independence controls are undocumented. Investigate these weaknesses in your backup design.

## **Next year strategy options**

The annual planning limit is NGN 3,000,000. Each package covers all five functions and shared infrastructure. Add NGN 400,000 annually for independent protected backups and NGN 200,000 for training and tests. Package timings are estimates requiring validation. Use the current drill timings on the next page for Task 5\.

| Package | Annual base cost NGN | Estimated first critical service | Data-loss window |
| :---- | :---- | :---- | :---- |
| Cold | 600,000 | 24 to 48 hours | Up to 24 hours |
| Warm | 1,500,000 | 3 to 5 hours | 1 to 6 hours |
| Hot | 2,400,000 | About 1 hour | Up to 15 minutes |

# **Recovery drill data and business impact**

## **Current warm site drill timings**

Start at 08:00. Each action occupies one technician for its full duration. Two actions may run in parallel only when all prerequisites are complete and technicians are free. Actions cannot be split. Durations include their local validation; a function is available after its application or file action completes.

| Action | Minutes | Prerequisite |
| :---- | :---: | :---- |
| Recovery network | 30 | None |
| AUTH01 restoration | 30 | Recovery network |
| Security and backup checks | 30 | AUTH01 restoration |
| DB01 restoration | 90 | Security and backup checks |
| LMS01 restoration | 45 | DB01 restoration |
| FIN01 restoration | 30 | DB01 restoration |
| REG01 restoration | 30 | DB01 restoration |
| HR01 restoration | 45 | DB01 restoration |
| FS01 restoration | 60 | AUTH01 restoration and security and backup checks |

## **Task 1 Business Impact Analysis**

**20 marks**

* Build a BIA covering F1 to F5. For each function, record the owner role, users affected, critical resources, dependencies, impact over time, minimum acceptable service, and proposed recovery priority. Include people, premises, suppliers, and information needs.  
* Calculate the total estimated disruption cost for 8 hours and 24 hours using the supplied rates and the one-off examination trigger. Show the calculation for each function and the combined total. Explain two limitations of these estimates and distinguish financial impact from learner welfare, reputation, and data integrity.  
* Explain how the 11:00 examination and later deadlines affect priorities. Separate business priority from the technical restoration order required by shared infrastructure. Identify at least three important dependency risks.

**Required outputs: five-function BIA, worked impact calculations, and a justified priority sequence.**

# **Recovery objectives and strategy selection**

## **Task 2 Recovery objectives and backup design**

**15 marks**

* Define Recovery Time Objective (RTO), Recovery Point Objective (RPO), and Maximum Tolerable Downtime (MTD). Propose and justify numerical targets for each function. State the service level at which you will declare recovery and leave a justified buffer between technical recovery and the tolerable business disruption limit.  
* Calculate the age of the latest recoverable DB01, AUTH01, and FS01 checkpoints at 08:00. Map the resulting potential data-loss windows to the affected functions and compare them with your proposed RPOs. Use the disruption time as the reference point. Explain what can be reconciled from temporary records and what cannot be assumed recoverable.  
* Design a backup schedule that addresses the RPO gaps. Specify full and incremental or differential backups, retention, offsite placement, and the exact chain needed to restore DB01. Apply the 3-2-1 principle and include an independent offline or immutable copy, restricted access, encryption, and restoration tests.  
* Explain why offsite storage or a live replica alone does not establish recoverability. Define how you will check backup integrity, access independence, and the usability of restored data. Label any unverified assumptions.

**Required outputs: objective matrix, checkpoint calculations, and backup and restoration design.**

## **Task 3 Recovery strategy and budget**

**15 marks**

* Compare the Cold, Warm, and Hot packages against your RTO and RPO targets, staffing needs, geography, supplier dependencies, and the risk of propagating corruption or malicious changes. Treat the quoted recovery windows as planning estimates.  
* Calculate the complete annual cost of each package, including both required additions. Identify which options fit the NGN 3,000,000 limit. Recommend one option, justify the tradeoffs, and identify any objective it cannot meet. Document residual risks and who must accept them.  
* Compare your recommendation with the estimated 8-hour and 24-hour disruption costs. Explain why a single-outage estimate cannot by itself establish annual return on investment. Identify the evidence needed before approving expenditure or accepting supplier recovery claims.

**Required outputs: option matrix, itemised budget, and a justified recommendation.**

# **Coordinated continuity and recovery plan**

## **Task 4 Business continuity and disaster recovery plan**

**20 marks**

* Prepare a coordinated plan with scope, activation thresholds, an authorised decision maker and deputy, escalation, contact roles, alternative communication, and situation reporting. Define how the continuity team, technical recovery team, facilities staff, and incident response team work together.  
* Create a RACI matrix for at least six activities, including activation, temporary assessment delivery, backup validation, restoration, stakeholder communication, and return to the primary site. Give each activity exactly one accountable role and at least one responsible role. A combined A/R role is acceptable.  
* Design temporary procedures for F1 to F5 during the 72-hour site outage. Address the 25-workstation limit and 40 learners needing a centre workstation. Explain approvals, accessibility, assessment integrity, privacy, record keeping, and later reconciliation. Identify the minimum staff, equipment, and supplier support required.  
* Write a DR runbook with ordered actions, prerequisites, owners, completion checks, and contingency actions if a step fails. Include backup selection, validation, application and data checks, business acceptance, and rollback. Distinguish restoring technology from resuming an acceptable business service.  
* Provide a stakeholder communication matrix and a 120 to 180 word initial learner notice. Explain when possible compromise would trigger incident response involvement. Define safe return to the primary site, controlled transfer of new records, and final sign-off after facilities clearance and business validation.

**Required outputs: coordinated BC/DR plan, RACI, temporary procedures, DR runbook, communication matrix, and learner notice.**

# **Recovery validation and program governance**

## **Task 5 Recovery schedule and exercise**

**15 marks**

* Using the current warm site timings, produce a schedule with action, technician, start time, finish time, and prerequisite. Respect the two-technician limit. Determine the earliest possible restoration of assessment service and a feasible completion time for all five functions. Show the dependency path that controls the assessment finish time.  
* Calculate each function's elapsed recovery time from 08:00 and compare it with your RTO and MTD targets. Compare restored checkpoints with your RPO targets. Label these as modelled baseline results, not a live test. Explain which deadlines need a continuity workaround even when restoration is successful.

Design and walk through a 45 minute tabletop exercise using these injects. You may simulate all participant roles individually.

| Exercise time | Required inject |
| :---- | :---- |
| Minute 10 | The site closure extends from 72 hours to five days. |
| Minute 20 | The alternate facility can provide only 15 working workstations. |
| Minute 30 | A DB01 incremental backup fails its integrity check. An unexpected backup administrator logon also requires investigation. |
| Minute 40 | The payment provider reports successful payments absent from the restored finance records. |

* Record a decision and revised action for every inject, including its owner, rationale, and effect on service or recovery. Keep this stress scenario separate from the baseline schedule. Produce at least five corrective actions with priority, owner, target date, and measurable completion evidence.

## **Task 6 Governance and performance measures**

**10 marks**

* Assign plan ownership and approval. Propose a risk-based testing calendar with review triggers, training, version control, and distribution. Map at least four of your outputs to NIST SP 800-34 planning steps and four to the ISO 22301 themes covered in the slides. Explain one relevant flood or climate consideration.  
* Define at least four KPIs with formula or measurement method, data source, target, reporting frequency, and accountable owner. Include recovery performance, restoration-test coverage, corrective-action closure, and training. Assess current maturity using the slide 13 model and propose a realistic 12-month improvement target.

## **Submission and authorship**

Name your file GRC205\_BCDR\_Assignment\_StudentID.docx. Include your name, student ID, official email, word count, all tasks, calculations, and references. Cite the teaching slides and at least two authoritative sources. Acknowledge AI assistance under the course policy. Keep scenario data fictional and be ready to explain your decisions. Use the deadline and extension controls published in E-Campus.

# **Marking rubric and source guidance**

The maximum score is 100\. The assignment contributes 30% of the final course grade.

| Assessment area | Mark allocation and evidence expected | Marks |
| :---- | :---- | :---: |
| Task 1Business impact | Complete BIA and minimum-service requirements (6); correct, explained impact calculations (8); justified priorities and dependency risks (6). | 20 |
| Task 2Objectives and backups | Justified RTO, RPO, and MTD targets (5); correct checkpoint analysis and objective gaps (6); usable backup design and verification (4). | 15 |
| Task 3Strategy and cost | Accurate comparison of options (4); complete budget arithmetic (5); defensible choice, residual risks, and investment reasoning (6). | 15 |
| Task 4Coordinated plans | Activation, roles, and RACI (5); workable temporary business procedures (7); DR sequence, validation, communication, and controlled return (8). | 20 |
| Task 5Testing and validation | Feasible schedule, critical dependency path, and objective comparisons (7); reasoned responses to all injects (4); measurable corrective actions (4). | 15 |
| Task 6Governance and KPIs | Ownership, testing, framework mapping, and maintenance (5); measurable KPIs (3); justified maturity assessment and improvement target (2). | 10 |
| Report qualityand referencing | Clear structure and usable tables (2); credible sources and consistent citations (2); transparent assumptions and professional writing (1). | 5 |
| Total | Maximum course contribution: 30%. | 100 |

Full credit requires technically sound work applied to the supplied case, correct calculations, and decisions that can be carried out with the stated resources. Partial credit applies to incomplete, generic, or weakly supported elements. Missing or technically incorrect elements earn no credit for those elements. Different justified strategies can earn full marks.

## **Technical guidance**

Recovery targets are commitments to be justified and tested. A site label does not guarantee zero downtime or zero data loss. RPO concerns the recoverable data point before disruption; RTO concerns recovery time, and MTD concerns tolerable business disruption. Keep a recovery buffer within the business tolerance. Treat the proposed framework mapping as an educational alignment, without claiming certification.

## **Core reading**

ICDFA. Business Continuity and Disaster Recovery. GRC205, Week 21\. Teaching deck, slides 1 to 15\.

NIST (2010, updated November 2010). SP 800-34 Revision 1\. Contingency Planning Guide for Federal Information Systems. [Official guide and BIA templates](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final)

ISO. ISO 22301:2019. Business continuity management systems. [Official overview and preview](https://www.iso.org/standard/75106.html)

ISO. ISO 22301:2019 Amendment 1:2024. Climate action changes. [Official amendment page](https://www.iso.org/standard/88412.html)

Use publicly accessible official guidance for the required high-level mapping. Purchasing the full ISO standard is not required for this assignment.
