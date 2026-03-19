**Q1.** Which type of security assessment involves actively attempting to exploit vulnerabilities to determine the actual security posture of a target system?

A) Vulnerability assessment
B) Penetration testing
C) Security audit
D) Risk assessment

<details><summary>Answer</summary>

**B) Penetration testing**

Penetration testing goes beyond identifying vulnerabilities — it actively exploits them (with authorization) to demonstrate real-world impact. A vulnerability assessment identifies and rates vulnerabilities without exploiting them. A security audit reviews compliance with policies and standards. A risk assessment evaluates threats, vulnerabilities, and impacts to prioritize security investments.

</details>

---

**Q2.** A penetration tester is provided with full documentation of the target organization's systems, network diagrams, and source code before beginning the engagement. Which type of penetration test is this?

A) Black box test
B) Gray box test
C) White box test
D) Crystal box test

<details><summary>Answer</summary>

**C) White box test**

A white box test (also called crystal box) provides the tester with full knowledge of the target environment: architecture, source code, credentials, documentation. This simulates an insider threat or allows comprehensive testing. Black box testing provides no prior knowledge (simulates an external attacker). Gray box testing provides partial knowledge. White box tests are more thorough but less realistic for external threat simulation.

</details>

---

**Q3.** Which standard provides a common language for describing and scoring security vulnerabilities?

A) CVE
B) CVSS
C) CWE
D) OWASP

<details><summary>Answer</summary>

**B) CVSS**

CVSS (Common Vulnerability Scoring System) provides a standardized numerical score (0–10) reflecting the severity of vulnerabilities. CVE (Common Vulnerabilities and Exposures) is a list of known vulnerability identifiers. CWE (Common Weakness Enumeration) categorizes types of software weaknesses. OWASP is an organization that produces security resources including the Top 10 web vulnerability list.

</details>

---

**Q4.** During a security assessment, a tester uses automated tools to identify open ports, running services, and operating system versions on target systems. Which phase of penetration testing is this?

A) Exploitation
B) Reconnaissance
C) Scanning and enumeration
D) Post-exploitation

<details><summary>Answer</summary>

**C) Scanning and enumeration**

Scanning and enumeration uses tools (Nmap, Nessus, etc.) to identify active hosts, open ports, services, operating systems, and potential vulnerabilities. Reconnaissance (OSINT) gathers information through passive means. Exploitation attempts to take advantage of discovered vulnerabilities. Post-exploitation activities occur after successful compromise (lateral movement, data exfiltration, persistence).

</details>

---

**Q5.** What is the PRIMARY purpose of test coverage analysis in software security testing?

A) To measure the execution speed of test cases
B) To determine what percentage of code, branches, or conditions are exercised by tests
C) To identify the number of developers who contributed to the codebase
D) To calculate the cost of the testing effort

<details><summary>Answer</summary>

**B) To determine what percentage of code, branches, or conditions are exercised by tests**

Code coverage analysis measures how thoroughly tests exercise the application's code — what percentage of lines, branches, functions, and conditions are executed during testing. Higher coverage means fewer untested code paths that could contain vulnerabilities. 100% coverage doesn't guarantee security, but low coverage indicates significant untested attack surface.

</details>

---

**Q6.** An organization conducts quarterly reviews of user access rights to ensure they still require the access they have. What is this practice called?

A) Access provisioning
B) Identity reconciliation
C) Access recertification (access review)
D) Role mining

<details><summary>Answer</summary>

**C) Access recertification (access review)**

Access recertification (also called access review or certification campaigns) is the periodic process of reviewing user access rights and confirming or revoking them based on current business need. This detects access creep, orphaned accounts, and excessive privileges. It is a key compensating control for least privilege enforcement and is required by regulations like SOX, PCI DSS, and HIPAA.

</details>

---

**Q7.** Which testing method examines an application's behavior by providing invalid, unexpected, or random inputs to discover vulnerabilities?

A) Static analysis
B) Dynamic analysis
C) Fuzzing
D) Regression testing

<details><summary>Answer</summary>

**C) Fuzzing**

Fuzzing (fuzz testing) supplies malformed, random, or boundary-condition inputs to an application to find bugs and vulnerabilities (crashes, memory corruption, unexpected behavior). It is particularly effective at finding buffer overflows and input validation flaws. Static analysis examines source code without executing it. Dynamic analysis tests running applications under controlled conditions. Regression testing verifies that changes don't break existing functionality.

</details>

---

**Q8.** A security team reviews firewall logs, IDS alerts, and authentication logs for signs of compromise. What type of assessment activity is this?

A) Penetration testing
B) Log analysis / security monitoring
C) Vulnerability scanning
D) Configuration review

<details><summary>Answer</summary>

**B) Log analysis / security monitoring**

Reviewing logs from multiple sources (firewalls, IDS, authentication systems) for signs of compromise is log analysis, a core component of security monitoring. This is a detective control. Penetration testing actively attacks systems. Vulnerability scanning identifies weaknesses without exploitation. Configuration review assesses system settings against security baselines.

</details>

---

**Q9.** What is the purpose of a security baseline in configuration management?

A) To define the minimum acceptable security configuration for systems
B) To document the current state of all systems at a point in time
C) To provide a rollback point for failed software updates
D) To measure system performance under normal operating conditions

<details><summary>Answer</summary>

**A) To define the minimum acceptable security configuration for systems**

A security baseline defines the minimum set of security configurations required for a system type (e.g., all Windows servers must have specific settings enabled). Systems are built to meet or exceed the baseline. Deviations from the baseline indicate potential security issues. Baselines are derived from standards like CIS Benchmarks, DISA STIGs, and vendor security guides.

</details>

---

**Q10.** Which type of security control verification tests whether specific control objectives are met without actively testing systems?

A) Penetration test
B) Vulnerability scan
C) Control audit
D) Red team exercise

<details><summary>Answer</summary>

**C) Control audit**

A control audit reviews whether security controls meet their stated objectives, typically through examination of documentation, interviews, and observation — without actively testing systems. Penetration tests and vulnerability scans actively probe systems. Red team exercises simulate sophisticated adversaries. Audits assess control effectiveness and compliance, and are often performed by internal or external audit functions.

</details>

---

**Q11.** An organization is required to demonstrate compliance with PCI DSS. What type of third-party assessment validates compliance for large merchants?

A) Internal audit
B) Qualified Security Assessor (QSA) assessment
C) Penetration test only
D) Self-assessment questionnaire (SAQ)

<details><summary>Answer</summary>

**B) Qualified Security Assessor (QSA) assessment**

Large merchants and service providers are required to undergo annual PCI DSS assessments by a Qualified Security Assessor (QSA) — a certified independent assessor approved by the PCI Security Standards Council. Smaller merchants may use a Self-Assessment Questionnaire (SAQ). Penetration testing is required as part of PCI DSS but is not sufficient alone for compliance validation.

</details>

---

**Q12.** Which automated testing approach analyzes source code without executing it to identify potential vulnerabilities?

A) Dynamic application security testing (DAST)
B) Static application security testing (SAST)
C) Interactive application security testing (IAST)
D) Runtime application self-protection (RASP)

<details><summary>Answer</summary>

**B) Static application security testing (SAST)**

SAST analyzes source code, bytecode, or binaries without executing the application — a "white box" approach that can find vulnerabilities early in development (shift left). DAST tests the running application from outside (black box). IAST instruments the application during testing to observe internal behavior. RASP protects applications at runtime by intercepting attacks.

</details>

---

**Q13.** What is the MAIN purpose of a bug bounty program?

A) To reward internal developers for writing bug-free code
B) To incentivize external security researchers to responsibly disclose vulnerabilities
C) To replace the organization's internal penetration testing program
D) To detect performance issues in production applications

<details><summary>Answer</summary>

**B) To incentivize external security researchers to responsibly disclose vulnerabilities**

Bug bounty programs offer monetary rewards to external security researchers who discover and responsibly disclose vulnerabilities. This harnesses the skills of the global security community to find issues that internal teams miss. Bug bounties complement (not replace) internal testing. They require a clear scope, rules of engagement, and responsible disclosure process.

</details>

---

**Q14.** Which assessment approach simulates an advanced persistent threat (APT) by combining offensive tactics with deception testing of defensive teams?

A) Vulnerability assessment
B) Penetration test
C) Red team exercise
D) Purple team exercise

<details><summary>Answer</summary>

**C) Red team exercise**

A red team exercise simulates a sophisticated adversary (APT) using realistic attack techniques against an organization, often with full adversary simulation including social engineering, physical access, and long-term persistence. The defending team (blue team) responds without knowing the exercise is happening. A purple team combines red and blue teams working together to improve defenses collaboratively.

</details>

---

**Q15.** A developer runs a tool that identifies SQL injection vulnerabilities by testing the running application with crafted HTTP requests. Which testing approach is this?

A) SAST
B) DAST
C) IAST
D) Fuzzing

<details><summary>Answer</summary>

**B) DAST**

DAST (Dynamic Application Security Testing) tests the running application from outside — sending HTTP requests, analyzing responses, and identifying vulnerabilities like SQL injection, XSS, and authentication flaws without source code access. It simulates an attacker's perspective. SAST requires source code access. IAST instruments the application during runtime. Fuzzing is a specific technique of providing unexpected inputs.

</details>

---

**Q16.** What is the purpose of log retention policies in a security program?

A) To reduce storage costs by deleting old logs quickly
B) To ensure logs are available for forensic investigation and compliance requirements
C) To improve SIEM performance by reducing the volume of stored data
D) To prevent log tampering by automatically deleting logs after review

<details><summary>Answer</summary>

**B) To ensure logs are available for forensic investigation and compliance requirements**

Log retention policies define how long security logs must be kept. Regulations like PCI DSS (1 year), HIPAA (6 years), and SOX (7 years) require specific retention periods. In forensic investigations, historical logs are critical for reconstructing attack timelines. Logs should be immutable (write-once) and protected from tampering, not deleted to prevent discovery.

</details>

---

**Q17.** Which concept describes the process of ensuring that test results from a previous system state are still valid after a change?

A) Regression testing
B) Unit testing
C) Integration testing
D) Acceptance testing

<details><summary>Answer</summary>

**A) Regression testing**

Regression testing verifies that changes (patches, new features, configuration changes) did not introduce new vulnerabilities or break existing security controls. It re-runs previous tests after modifications. Unit testing tests individual code components. Integration testing verifies components work together. Acceptance testing verifies the system meets business requirements. Regression testing is essential after any system change.

</details>

---

**Q18.** An auditor reviews system configurations and compares them against CIS Benchmarks. What type of assessment is this?

A) Penetration test
B) Configuration (hardening) audit
C) Vulnerability scan
D) Code review

<details><summary>Answer</summary>

**B) Configuration (hardening) audit**

Comparing system configurations against security standards (CIS Benchmarks, DISA STIGs, vendor security guides) is a configuration or hardening audit. This ensures systems are built to minimum security baselines. Penetration tests actively exploit vulnerabilities. Vulnerability scans identify known vulnerabilities automatically. Code reviews examine application source code.

</details>

---

**Q19.** What is a key limitation of automated vulnerability scanning compared to manual penetration testing?

A) Automated scanners are slower than manual testing
B) Automated scanners cannot determine the true exploitability or business impact of vulnerabilities in context
C) Automated scanners require more expertise to operate
D) Automated scanners only work on external-facing systems

<details><summary>Answer</summary>

**B) Automated scanners cannot determine the true exploitability or business impact of vulnerabilities in context**

Automated scanners identify potential vulnerabilities but cannot assess whether they are actually exploitable in the specific environment, what the real business impact would be, or whether compensating controls reduce the effective risk. They generate many false positives and false negatives. Manual penetration testing provides the contextual judgment that automated tools lack. Both approaches are complementary.

</details>

---

**Q20.** An organization contracts with an external firm to perform an independent assessment of its security controls and compliance posture. This is BEST described as:

A) Internal audit
B) Third-party security assessment
C) Penetration test
D) Red team engagement

<details><summary>Answer</summary>

**B) Third-party security assessment**

An independent external firm performing security control assessment and compliance review is a third-party security assessment. The independence is key — it provides objectivity that internal assessments may lack. Regulators and boards often require third-party assessments. This differs from penetration testing (active exploitation) and red team engagements (adversary simulation).

</details>

---

**Q21.** What is the FIRST step in designing a security assessment program?

A) Selecting assessment tools and technologies
B) Defining the scope, objectives, and rules of engagement
C) Scheduling the assessment calendar
D) Identifying and training assessment personnel

<details><summary>Answer</summary>

**B) Defining the scope, objectives, and rules of engagement**

Defining scope, objectives, and rules of engagement is the foundational step for any security assessment. Without clear scope (what's in/out), objectives (what questions to answer), and rules (what testers can/cannot do), assessments may cause harm, miss critical areas, or produce irrelevant results. Tool selection, scheduling, and staffing come after scope and objectives are defined.

</details>

---

**Q22.** Which metric measures the total number of vulnerabilities discovered in a system as a percentage of all potential vulnerabilities?

A) False positive rate
B) Mean time to remediate (MTTR)
C) Vulnerability detection coverage
D) Risk reduction rate

<details><summary>Answer</summary>

**C) Vulnerability detection coverage**

Vulnerability detection coverage measures what fraction of actual vulnerabilities in a system were discovered by the assessment. Low coverage means many vulnerabilities were missed. This metric helps evaluate the thoroughness of testing methods. False positive rate measures incorrectly identified vulnerabilities. MTTR measures remediation speed. Risk reduction rate measures the impact of security improvements.

</details>

---

**Q23.** A security team discovers that a production web application has a critical SQL injection vulnerability. What is the MOST appropriate immediate response?

A) Immediately shut down the application
B) Notify the development team and apply a WAF rule to block the attack vector while a permanent fix is developed
C) Document the vulnerability and schedule a fix in the next release cycle
D) Conduct a full penetration test to identify all SQL injection points before taking action

<details><summary>Answer</summary>

**B) Notify the development team and apply a WAF rule to block the attack vector while a permanent fix is developed**

For a critical production vulnerability, the immediate goal is to reduce risk as quickly as possible without unnecessarily disrupting the business. A WAF rule provides immediate interim protection while developers create a proper fix. Shutting down the application may cause unacceptable business disruption. Scheduling the fix for the next release ignores the critical severity. A full pentest can wait — the known critical issue needs addressing first.

</details>

---

**Q24.** Which process evaluates the effectiveness of security awareness training by testing whether employees take the bait in a simulated phishing campaign?

A) Social engineering penetration test
B) Security awareness phishing simulation
C) Red team exercise
D) Human risk assessment

<details><summary>Answer</summary>

**B) Security awareness phishing simulation**

Phishing simulations send fake phishing emails to employees to measure click rates, credential submission rates, and reporting rates. Results identify high-risk employees needing additional training and measure the effectiveness of awareness programs over time. This is a legitimate, authorized form of social engineering assessment specifically targeting the human layer of security.

</details>

---

**Q25.** What type of assessment evaluates privacy risks associated with the collection and use of personal data in a new system or process?

A) Business impact analysis
B) Privacy impact assessment (PIA)
C) Data flow diagram review
D) Threat modeling

<details><summary>Answer</summary>

**B) Privacy impact assessment (PIA)**

A Privacy Impact Assessment (PIA), also called Data Protection Impact Assessment (DPIA) under GDPR, systematically evaluates the privacy risks associated with a new system, process, or project that collects or processes personal data. PIAs identify risks, propose mitigations, and document compliance decisions. They are often required by regulation before deploying systems that process sensitive personal data.

</details>

---
