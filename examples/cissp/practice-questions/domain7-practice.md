**Q1.** Which phase of the incident response lifecycle focuses on limiting the spread and impact of a security incident?

A) Identification
B) Containment
C) Eradication
D) Recovery

<details><summary>Answer</summary>

**B) Containment**

Containment limits the damage and prevents the incident from spreading to additional systems. This phase includes both short-term containment (isolating affected systems) and long-term containment (implementing temporary fixes). Identification confirms an incident has occurred. Eradication removes the root cause. Recovery restores systems to normal operation. The order is: Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned.

</details>

---

**Q2.** A forensic investigator collects digital evidence from a compromised server. What is the MOST important principle to follow during evidence collection?

A) Collect all available data as quickly as possible
B) Maintain chain of custody and preserve evidence integrity
C) Power down the system immediately to prevent further damage
D) Run antivirus software before collecting evidence

<details><summary>Answer</summary>

**B) Maintain chain of custody and preserve evidence integrity**

Chain of custody documents who handled evidence, when, and how — ensuring integrity from collection through legal proceedings. Any gap in chain of custody can make evidence inadmissible. Forensic investigators use write blockers, hash verification, and detailed documentation. Immediately powering down may destroy volatile evidence (RAM, running processes). Antivirus can alter evidence. Collecting quickly at the expense of integrity defeats the purpose.

</details>

---

**Q3.** What is the order of volatility in digital forensics evidence collection?

A) Network traffic → Disk → Memory → Swap space
B) Memory → Swap space → Network traffic → Disk
C) Memory → Network connections → Disk → Backup media
D) Disk → Memory → Swap space → Network traffic

<details><summary>Answer</summary>

**C) Memory → Network connections → Disk → Backup media**

Evidence must be collected in order of volatility — most volatile (disappears first) to least volatile. RAM (memory) is lost immediately when power is cut. Active network connections disappear when sessions end. Disk data persists but can be overwritten. Backup media is the most durable. Following volatility order ensures the most transient evidence is captured first. RFC 3227 documents these guidelines.

</details>

---

**Q4.** Which concept describes an organization's plan for resuming normal IT operations after a disaster, focusing specifically on technology systems?

A) Business continuity plan
B) Disaster recovery plan
C) Crisis management plan
D) Continuity of operations plan

<details><summary>Answer</summary>

**B) Disaster recovery plan**

A disaster recovery plan (DRP) focuses specifically on restoring IT systems, data, and infrastructure after a disaster. It includes RPO/RTO targets, backup procedures, alternate processing sites, and recovery procedures for specific systems. A BCP focuses on maintaining business functions during disruption. A crisis management plan handles the human/communications aspects. COOP is a government-focused continuity framework.

</details>

---

**Q5.** An organization's RTO for its core banking system is 4 hours and its RPO is 1 hour. What do these metrics mean?

A) The system must be restored within 4 hours; no more than 1 hour of data can be lost
B) Recovery must begin within 1 hour; the system must be fully restored within 4 hours
C) Data backups must occur every 4 hours; recovery takes 1 hour
D) 4 hours of downtime is acceptable; 1 hour of data loss has occurred

<details><summary>Answer</summary>

**A) The system must be restored within 4 hours; no more than 1 hour of data can be lost**

RTO (Recovery Time Objective) is the maximum acceptable time to restore a system or process after a disruption — the system must be back within 4 hours. RPO (Recovery Point Objective) is the maximum acceptable amount of data loss measured in time — at most 1 hour of transactions can be lost, meaning backups/replication must occur at least hourly. Both drive backup frequency and recovery site requirements.

</details>

---

**Q6.** What type of recovery site has all necessary hardware, software, and network connectivity installed and ready to operate on short notice?

A) Cold site
B) Warm site
C) Hot site
D) Mobile site

<details><summary>Answer</summary>

**C) Hot site**

A hot site is a fully operational alternate facility with up-to-date hardware, software, network connectivity, and near-real-time data replication. Failover can occur within minutes to hours. Cold sites have space and power but no equipment. Warm sites have hardware but may need software installation and data restoration. Hot sites have the lowest RTO but highest cost. Mobile sites are transportable facilities deployed to any location.

</details>

---

**Q7.** During incident response, who is typically responsible for declaring an incident a "major incident" and activating the incident response team?

A) Any employee who suspects a security issue
B) The SOC analyst who first detects the anomaly
C) The incident response manager or CISO based on predefined severity criteria
D) External law enforcement when criminal activity is suspected

<details><summary>Answer</summary>

**C) The incident response manager or CISO based on predefined severity criteria**

Major incident declarations should follow predefined criteria (severity levels, impact thresholds, affected systems) and be made by the incident response manager, CISO, or designated authority. This ensures consistent, appropriate response activation. While any employee can report suspicious activity and SOC analysts triage, formal escalation follows the defined process. Law enforcement involvement may follow, but they don't trigger internal response.

</details>

---

**Q8.** A security operations team receives an alert that an employee's workstation is communicating with a known malicious IP address. What is the FIRST action they should take?

A) Immediately block the employee's account
B) Contain the workstation by isolating it from the network, then investigate
C) Notify law enforcement of potential criminal activity
D) Reimage the workstation to remove potential malware

<details><summary>Answer</summary>

**B) Contain the workstation by isolating it from the network, then investigate**

The first priority is containment — isolating the affected workstation prevents potential malware from spreading laterally or exfiltrating additional data. After isolation, the team investigates (collects forensic data, analyzes malware). Blocking the account addresses identity but not the compromised endpoint. Law enforcement is premature. Reimaging destroys forensic evidence and should occur during eradication, after investigation.

</details>

---

**Q9.** Which monitoring approach uses predefined patterns and signatures to detect known malicious activity in security logs?

A) Anomaly-based detection
B) Behavior analytics
C) Signature-based detection
D) Heuristic analysis

<details><summary>Answer</summary>

**C) Signature-based detection**

Signature-based detection matches events against known patterns (attack signatures, IOCs). It is highly effective for known threats with low false positive rates, but cannot detect unknown threats. Anomaly-based detection identifies deviations from normal behavior — it can detect novel attacks but has higher false positive rates. Behavior analytics (UEBA) looks for anomalous user behavior patterns. Heuristic analysis uses rules-based pattern matching for novel threats.

</details>

---

**Q10.** Which type of malware remains dormant until triggered by a specific date, time, or event?

A) Worm
B) Trojan
C) Logic bomb
D) Rootkit

<details><summary>Answer</summary>

**C) Logic bomb**

A logic bomb is malicious code that remains dormant until triggered by a specific condition — a date (time bomb), user action, or system event. It is often planted by insiders. A worm self-replicates across networks. A Trojan disguises itself as legitimate software. A rootkit hides its presence in the operating system. Logic bombs are particularly dangerous because they can be planted by privileged insiders.

</details>

---

**Q11.** What is the purpose of a SIEM system in security operations?

A) To prevent attacks by blocking malicious traffic in real time
B) To aggregate, correlate, and analyze security logs from multiple sources to detect threats
C) To manage vulnerability scanning schedules and results
D) To encrypt and protect sensitive log data from unauthorized access

<details><summary>Answer</summary>

**B) To aggregate, correlate, and analyze security logs from multiple sources to detect threats**

A SIEM (Security Information and Event Management) system collects logs from firewalls, endpoints, servers, applications, and other sources, normalizes the data, correlates events across sources, and generates alerts for suspicious activity. It enables detection of complex attacks that span multiple systems and provides the visibility needed for effective security monitoring. SIEMs don't block traffic (that's IPS/firewalls).

</details>

---

**Q12.** An organization discovers a zero-day vulnerability being actively exploited in its systems. Which incident response phase is most critical to address IMMEDIATELY?

A) Preparation
B) Identification
C) Containment
D) Recovery

<details><summary>Answer</summary>

**C) Containment**

When an active exploit is confirmed, containment is the immediate priority — stopping the attack from spreading and causing additional damage. In a zero-day scenario with no patch available, containment typically involves isolating affected systems, blocking IOCs at the perimeter, and implementing compensating controls (WAF rules, additional monitoring). Preparation should have already occurred. Identification has already happened. Recovery comes after eradication.

</details>

---

**Q13.** What is the PRIMARY goal of the eradication phase in incident response?

A) Restore affected systems to normal operation
B) Remove all traces of the attacker's tools, malware, and access methods from the environment
C) Document the timeline and impact of the incident
D) Notify affected customers and regulators of the breach

<details><summary>Answer</summary>

**B) Remove all traces of the attacker's tools, malware, and access methods from the environment**

Eradication focuses on completely removing the threat from the environment: deleting malware, closing backdoors, removing unauthorized accounts, patching exploited vulnerabilities, and ensuring no persistence mechanisms remain. Rushing to recovery without thorough eradication risks re-infection. Restoring systems is the recovery phase. Documentation happens throughout. Notification is handled separately.

</details>

---

**Q14.** What distinguishes a worm from a virus?

A) A worm requires user interaction to spread; a virus does not
B) A worm self-replicates and spreads automatically across networks; a virus requires a host file
C) A worm encrypts files; a virus deletes files
D) A worm targets operating systems; a virus targets applications only

<details><summary>Answer</summary>

**B) A worm self-replicates and spreads automatically across networks; a virus requires a host file**

A worm self-replicates and propagates autonomously across networks without requiring a host file or user action. A virus attaches itself to a host file and requires the host to be executed to spread. This is why worms (like WannaCry, Slammer) can spread exponentially fast in unpatched environments. Both can carry malicious payloads, but the propagation mechanism differs fundamentally.

</details>

---

**Q15.** A company's payroll database is unavailable for 3 hours due to ransomware. The organization restores from a backup taken 2 hours before the attack. What metrics are relevant to evaluate this event?

A) RTO and RPO only
B) MTD and BIA only
C) RTO, RPO, and MTD
D) MTTR and MTBF

<details><summary>Answer</summary>

**C) RTO, RPO, and MTD**

RTO (how long to restore — 3 hours actual vs. the defined target), RPO (how much data was lost — 2 hours of transactions), and MTD (maximum tolerable downtime — was 3 hours acceptable?). These three metrics together evaluate whether the recovery met acceptable thresholds. MTTR (mean time to repair) and MTBF (mean time between failures) are operational reliability metrics, more relevant for ongoing availability analysis.

</details>

---

**Q16.** Which physical security control is MOST effective at preventing tailgating (piggybacking)?

A) Security cameras
B) Security guards at reception
C) Mantrap (access control vestibule)
D) Badge-controlled doors

<details><summary>Answer</summary>

**C) Mantrap (access control vestibule)**

A mantrap is an enclosure with two interlocking doors — the second door only opens after the first closes and access is verified. This physically prevents tailgating because only one person can pass through at a time. Security cameras detect tailgating after the fact (detective). Security guards can be distracted or socially engineered. Badge doors alone don't prevent tailgating if an authorized user holds the door.

</details>

---

**Q17.** An organization implements a patch management process that requires all critical patches to be applied within 72 hours of release. Which security principle does this MOST directly support?

A) Defense in depth
B) Reducing the window of vulnerability
C) Configuration management
D) Change management

<details><summary>Answer</summary>

**B) Reducing the window of vulnerability**

Patching quickly reduces the time window during which attackers can exploit known vulnerabilities. The longer a patch remains unapplied, the greater the exploitation risk — especially after public disclosure. 72-hour SLA for critical patches is aggressive patching that minimizes exposure. Vulnerability management, patch management, and timely remediation all serve this goal.

</details>

---

**Q18.** What is the purpose of an after-action review (lessons learned) following a security incident?

A) To assign blame for the incident to responsible parties
B) To identify what worked well, what didn't, and how to improve future incident response
C) To document the incident for regulatory reporting purposes
D) To determine the total financial cost of the incident

<details><summary>Answer</summary>

**B) To identify what worked well, what didn't, and how to improve future incident response**

The lessons learned (after-action review) phase improves the organization's security program by analyzing what happened, why it happened, what was effective in the response, and what should be improved. It is blameless and constructive. Regulatory reporting is a separate obligation. Financial assessment is part of impact analysis. Blame assignment is counterproductive to effective security culture.

</details>

---

**Q19.** Which type of backup captures only the data that has changed since the last full backup?

A) Differential backup
B) Incremental backup
C) Full backup
D) Mirror backup

<details><summary>Answer</summary>

**A) Differential backup**

A differential backup captures all data changed since the last full backup. It grows in size over time as more changes accumulate. Restoration requires the last full backup plus the last differential backup (two pieces). An incremental backup captures only changes since the last backup of any type (smaller, but more pieces needed for restoration). Full backup copies everything. The trade-off: incremental = less storage, slower restore; differential = more storage, faster restore.

</details>

---

**Q20.** What is the primary purpose of security awareness training?

A) To make employees responsible for all security incidents
B) To reduce the human risk factor by educating employees about threats and secure behaviors
C) To eliminate the need for technical security controls
D) To comply with regulatory requirements only

<details><summary>Answer</summary>

**B) To reduce the human risk factor by educating employees about threats and secure behaviors**

Humans are often the weakest link in security — phishing, social engineering, poor password practices, and accidental data disclosure are human-layer risks. Security awareness training educates employees about threats, safe behaviors, and how to report incidents. It is a preventive administrative control that complements technical controls. Training alone doesn't eliminate the need for technical controls or ensure compliance.

</details>

---

**Q21.** An organization retains a law firm on standby to respond to security incidents. Which incident response function does this fulfill?

A) Technical response capability
B) Legal and regulatory guidance for incident response
C) Public relations management
D) Insurance claim processing

<details><summary>Answer</summary>

**B) Legal and regulatory guidance for incident response**

Legal counsel provides guidance on breach notification requirements, evidence preservation (to maintain attorney-client privilege), regulatory obligations, and potential litigation. Having legal counsel pre-engaged speeds response. Cyber insurance claims are handled by the insurance team. PR management handles stakeholder communications. Technical response is handled by the IR team.

</details>

---

**Q22.** Which term describes the concept of planning for how an organization will function if key personnel are unavailable during a crisis?

A) Personnel redundancy
B) Succession planning and cross-training
C) Emergency response planning
D) Workforce continuity

<details><summary>Answer</summary>

**B) Succession planning and cross-training**

Succession planning identifies who assumes leadership roles if key people are unavailable. Cross-training ensures multiple people can perform critical functions. These reduce the risk of single-person dependencies (key person risk). BCP and COOP must address personnel continuity, not just technical systems. Organizations with key-person dependencies have a critical continuity vulnerability.

</details>

---

**Q23.** During a major security incident, who is responsible for communicating with the media and external stakeholders?

A) The incident response team leader
B) The CISO directly
C) Designated spokesperson or public relations representative
D) Any available senior manager

<details><summary>Answer</summary>

**C) Designated spokesperson or public relations representative**

External communications during incidents should be handled by a designated spokesperson — typically from PR or communications — who has been briefed by legal and the security team. Ad-hoc or unauthorized communications risk legal exposure, contradictions, and damage to trust. The IR team and CISO should focus on technical response. All external communications should be pre-approved and consistent.

</details>

---

**Q24.** An organization wants to test whether its backup and recovery procedures actually work as documented. What activity should it perform?

A) Tabletop exercise
B) Recovery test (restore from backup to alternate system)
C) Vulnerability assessment of backup infrastructure
D) Business impact analysis update

<details><summary>Answer</summary>

**B) Recovery test (restore from backup to alternate system)**

The only way to know whether backups actually work is to test them by performing an actual restore to an alternate system and verifying data integrity. Many organizations discover backup failures only when they need to restore — too late. Regular restore testing (quarterly or annually) validates backup procedures. Tabletop exercises test response plans through discussion, not actual recovery. BIAs define requirements but don't test backups.

</details>

---

**Q25.** What is the term for malware that encrypts a victim's data and demands payment for the decryption key?

A) Spyware
B) Ransomware
C) Adware
D) Cryptojacker

<details><summary>Answer</summary>

**B) Ransomware**

Ransomware encrypts victim files and demands ransom payment (usually cryptocurrency) for the decryption key. Modern ransomware often combines encryption with data exfiltration for double extortion. Spyware silently monitors and exfiltrates data. Adware displays unwanted advertisements. Cryptojackers use victim computing resources to mine cryptocurrency. Ransomware is one of the most impactful malware categories for organizations.

</details>

---
