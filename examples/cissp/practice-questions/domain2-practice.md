**Q1.** An organization is classifying its data assets. Who bears ultimate responsibility for assigning data classification levels?

A) The data custodian
B) The data owner
C) The security administrator
D) The end user

<details><summary>Answer</summary>

**B) The data owner**

The data owner (typically a business manager or executive) is responsible for classifying data and determining its value to the organization. The data custodian (often IT) is responsible for implementing controls to protect data as directed by the owner. End users consume data following classification-based rules. The security administrator implements technical controls.

</details>

---

**Q2.** Which data destruction method is MOST appropriate for highly sensitive data stored on a solid-state drive (SSD)?

A) Degaussing
B) Overwriting with zeros
C) Physical destruction
D) Low-level formatting

<details><summary>Answer</summary>

**C) Physical destruction**

SSDs use wear-leveling algorithms that distribute writes across flash cells, making traditional overwriting unreliable — data may remain in cells that were bypassed. Degaussing is ineffective on SSDs (no magnetic media). Physical destruction (shredding, crushing) is the most reliable method for SSDs. Encryption before disposal (crypto-erasure) is an alternative if destruction is impractical.

</details>

---

**Q3.** A company is retiring old laptops. Before donating them, the IT team reformats the drives. Why is this insufficient for protecting sensitive data?

A) Reformatting only deletes file system pointers, not the actual data
B) Donated devices are covered by data breach insurance
C) Reformatting is only ineffective for government-classified data
D) The drives were already encrypted, making reformatting unnecessary

<details><summary>Answer</summary>

**A) Reformatting only deletes file system pointers, not the actual data**

A standard reformat (quick format) removes the file allocation table and directory structure but leaves the actual data on disk. The data can be recovered with common forensic tools. Proper sanitization requires secure overwriting (e.g., DoD 5220.22-M), degaussing, or physical destruction. Full encryption prior to use makes reformatting sufficient, but that condition isn't stated here.

</details>

---

**Q4.** What is the MAIN purpose of data retention policies?

A) To maximize storage capacity utilization
B) To ensure data is kept as long as legally or operationally required, then destroyed
C) To prevent unauthorized access to archived data
D) To reduce backup costs by eliminating redundant copies

<details><summary>Answer</summary>

**B) To ensure data is kept as long as legally or operationally required, then destroyed**

Data retention policies define how long data must be kept based on legal, regulatory, and business requirements, and when it must be destroyed. Keeping data longer than required increases liability and cost. The policy addresses both retention minimums (legal compliance) and maximums (privacy risk reduction). Storage optimization and access control are separate concerns.

</details>

---

**Q5.** Which privacy principle requires organizations to collect only the minimum amount of personal data necessary for the stated purpose?

A) Purpose limitation
B) Data minimization
C) Storage limitation
D) Accountability

<details><summary>Answer</summary>

**B) Data minimization**

Data minimization (from GDPR and privacy frameworks) requires collecting only the data necessary for the specified purpose. Purpose limitation means data collected for one purpose cannot be repurposed. Storage limitation requires data not be kept longer than needed. Accountability requires organizations to demonstrate compliance. Data minimization specifically addresses the quantity of data collected.

</details>

---

**Q6.** A healthcare provider stores patient records in a cloud service. The cloud provider suffers a breach exposing the records. Who bears regulatory responsibility under HIPAA?

A) The cloud provider only, as the breach occurred in their infrastructure
B) Both the covered entity and the business associate bear responsibility
C) The healthcare provider only, as they contracted with the cloud provider
D) The patients, as they consented to cloud storage in their treatment agreements

<details><summary>Answer</summary>

**B) Both the covered entity and the business associate bear responsibility**

Under HIPAA, the healthcare provider is the covered entity; the cloud provider is a business associate. Both have legal obligations: the covered entity must have a signed Business Associate Agreement (BAA) and the business associate must implement required safeguards. Both can face penalties. Patients bear no regulatory responsibility.

</details>

---

**Q7.** What term describes the process of replacing sensitive data with a non-sensitive equivalent that has no meaningful value outside the application?

A) Encryption
B) Masking
C) Tokenization
D) Anonymization

<details><summary>Answer</summary>

**C) Tokenization**

Tokenization replaces sensitive data (e.g., a credit card number) with a surrogate value (token) that maps back to the original in a secure vault. Unlike encryption, the token itself has no mathematical relationship to the original data. Masking replaces data with realistic but fake data for testing. Anonymization irreversibly removes identifying information. Encryption transforms data using a key and is reversible.

</details>

---

**Q8.** An organization is developing a data handling policy. Which factor MOST influences where data falls in the classification scheme?

A) The size of the data set
B) The value, sensitivity, and potential impact if disclosed
C) The age of the data
D) The format (structured vs. unstructured) of the data

<details><summary>Answer</summary>

**B) The value, sensitivity, and potential impact if disclosed**

Data classification is based on the potential impact of unauthorized disclosure, modification, or destruction. Higher-impact data receives higher classification. Data size, age, and format are relevant to storage and retention but do not drive classification level. The key questions are: Who should see this? What happens if it's exposed?

</details>

---

**Q9.** A company implements a policy requiring that customer credit card numbers stored in a database be replaced with tokens. Which privacy-enhancing technique does this BEST represent?

A) Pseudonymization
B) Anonymization
C) Data masking
D) Tokenization

<details><summary>Answer</summary>

**D) Tokenization**

Tokenization substitutes sensitive data with a non-sensitive placeholder (token). The original data is stored separately in a secure token vault. This is widely used for PCI DSS compliance. Pseudonymization replaces identifying fields with pseudonyms (still reversible with a key). Anonymization irreversibly removes all identifying information. Data masking obscures data for display or testing but may retain structure.

</details>

---

**Q10.** Which of the following is a responsibility of the data custodian?

A) Determining the classification level of data
B) Implementing and maintaining controls to protect data
C) Granting access rights to data based on business need
D) Defining the data retention schedule

<details><summary>Answer</summary>

**B) Implementing and maintaining controls to protect data**

The data custodian (typically IT or operations staff) is responsible for the technical implementation and maintenance of controls as directed by the data owner. The data owner determines classification, grants access, and sets retention requirements. Custodians follow owner-defined policies but do not make classification or access decisions independently.

</details>

---

**Q11.** What is the PRIMARY goal of data sovereignty considerations in cloud computing?

A) Ensuring data is encrypted in transit and at rest
B) Ensuring data remains subject to the laws of the jurisdiction where it resides
C) Ensuring cloud providers maintain SLA commitments
D) Ensuring data can be accessed from any geographic location

<details><summary>Answer</summary>

**B) Ensuring data remains subject to the laws of the jurisdiction where it resides**

Data sovereignty means that data is subject to the laws of the country where it physically resides. Organizations must consider this when choosing cloud regions — storing EU citizen data in the US may trigger GDPR complications, and vice versa. Encryption and SLAs are separate concerns. Geographic accessibility is the opposite concern — sovereignty is about control, not access.

</details>

---

**Q12.** During asset inventory, a team discovers an unregistered server processing financial data. What FIRST step should be taken?

A) Immediately shut down the server to contain potential risk
B) Identify the owner, purpose, and classification of the data it holds
C) Report the server to law enforcement as a potential rogue device
D) Scan the server for vulnerabilities and apply patches

<details><summary>Answer</summary>

**B) Identify the owner, purpose, and classification of the data it holds**

The first step is discovery and classification — determine what the asset is, who owns it, and what data it contains. This informs subsequent decisions. Immediately shutting it down could disrupt legitimate business operations. Law enforcement involvement is premature without evidence of malicious activity. Patching without understanding the system's purpose could cause harm.

</details>

---

**Q13.** Which data state requires the MOST focus on access controls and authentication?

A) Data at rest
B) Data in transit
C) Data in use
D) Data in archive

<details><summary>Answer</summary>

**C) Data in use**

Data in use (data being actively processed in memory or applications) is the most vulnerable state because it is decrypted and accessible in plaintext to authorized (and potentially unauthorized) processes. Access controls and strong authentication limit who can interact with data while it's in use. Data at rest relies on encryption. Data in transit relies on transport encryption. Archives rely on access controls and retention management.

</details>

---

**Q14.** An organization uses synthetic data for software testing. What security benefit does this provide?

A) It eliminates the need for encryption in the test environment
B) It prevents exposure of real sensitive data in non-production environments
C) It reduces the storage footprint of test databases
D) It ensures test results match production results exactly

<details><summary>Answer</summary>

**B) It prevents exposure of real sensitive data in non-production environments**

Test environments typically have weaker security controls than production. Using synthetic (fake but realistic) data prevents real customer or business data from being exposed in those environments. This is a key data protection principle. Synthetic data does not eliminate encryption needs, may not reduce storage, and rarely matches production results exactly.

</details>

---

**Q15.** Which regulation requires organizations operating in California to honor consumer requests to delete their personal data?

A) HIPAA
B) GDPR
C) CCPA
D) PCI DSS

<details><summary>Answer</summary>

**C) CCPA**

The California Consumer Privacy Act (CCPA) grants California residents the right to request deletion of their personal data. GDPR has a similar "right to erasure" for EU residents. HIPAA governs healthcare data. PCI DSS governs payment card data security. Organizations serving California residents must implement CCPA-compliant deletion processes.

</details>

---

**Q16.** A security team is conducting a data flow analysis. What is the PRIMARY reason for mapping how data moves through an organization?

A) To optimize network bandwidth utilization
B) To identify where sensitive data is stored, processed, and transmitted so appropriate controls can be applied
C) To document system architecture for new developer onboarding
D) To verify that backups are performed correctly

<details><summary>Answer</summary>

**B) To identify where sensitive data is stored, processed, and transmitted so appropriate controls can be applied**

Data flow analysis (also called data flow mapping) is essential for applying the right controls at each stage of data's lifecycle. Without knowing where data travels, organizations cannot ensure it is properly protected at rest, in transit, and in use. This is foundational to privacy impact assessments and security architecture design.

</details>

---

**Q17.** What term describes the irreversible process of removing all identifying information from a dataset so that individuals cannot be identified?

A) Pseudonymization
B) Tokenization
C) Anonymization
D) Data masking

<details><summary>Answer</summary>

**C) Anonymization**

Anonymization is the irreversible removal of identifying information, meaning the data can no longer be linked to specific individuals even with additional information. Pseudonymization replaces identifiers with pseudonyms but is reversible with the right key. Tokenization substitutes values with tokens. Data masking obscures data for display. True anonymization removes data from privacy law scope under many regulations.

</details>

---

**Q18.** An organization's backup tapes are transported offsite by a third-party courier. Which control BEST protects the data during transit?

A) Requiring the courier to sign a non-disclosure agreement
B) Encrypting the data on the tapes before transport
C) Tracking the courier vehicle with GPS
D) Labeling tapes with their classification level

<details><summary>Answer</summary>

**B) Encrypting the data on the tapes before transport**

Encryption is the primary technical control for protecting data in transit. If tapes are lost or stolen, encrypted data cannot be read without the decryption key. An NDA provides legal recourse after a breach but does not prevent disclosure. GPS tracking helps with physical security but doesn't protect the data itself. Classification labeling informs handling but doesn't protect content.

</details>

---

**Q19.** Which concept describes the full lifecycle of data from creation through destruction?

A) Data governance
B) Data provenance
C) Information lifecycle management
D) Records management

<details><summary>Answer</summary>

**C) Information lifecycle management**

Information lifecycle management (ILM) covers the entire lifespan of data: creation/collection, storage, use, sharing, archiving, and destruction. Data governance is the overarching framework of policies. Data provenance tracks data origins and transformations. Records management focuses specifically on formal records and regulatory retention. ILM is the broadest term for the complete lifecycle.

</details>

---

**Q20.** A financial services firm classifies data as Public, Internal, Confidential, and Restricted. A spreadsheet containing merger and acquisition plans would MOST likely be classified as:

A) Public
B) Internal
C) Confidential
D) Restricted

<details><summary>Answer</summary>

**D) Restricted**

Merger and acquisition plans are among the most sensitive business information — premature disclosure could violate securities laws, harm competitive position, and damage negotiations. This warrants the highest classification level (Restricted). Only a very limited number of individuals should have access. Confidential data has broad business sensitivity; Restricted data has maximum sensitivity and legal implications.

</details>

---

**Q21.** During an asset management audit, which asset type is MOST commonly overlooked?

A) Physical servers
B) Network equipment
C) Software licenses
D) Information assets (data)

<details><summary>Answer</summary>

**D) Information assets (data)**

Data assets (databases, files, intellectual property, customer records) are frequently overlooked in asset inventories because they are intangible. Organizations often focus on hardware and software but fail to catalog what data exists, where it resides, and who owns it. This gap creates significant security and compliance risk. Information assets are often the most valuable assets an organization has.

</details>

---

**Q22.** What is the difference between data privacy and data security?

A) Data privacy is a technical control; data security is a policy requirement
B) Data privacy governs authorized use of personal data; data security protects data from unauthorized access
C) Data security applies only to digital data; data privacy applies to physical records too
D) Data privacy and data security are synonymous terms

<details><summary>Answer</summary>

**B) Data privacy governs authorized use of personal data; data security protects data from unauthorized access**

Data security focuses on preventing unauthorized access, use, or destruction (CIA triad). Data privacy focuses on ensuring personal data is collected, stored, and used in accordance with individuals' rights and applicable regulations. An organization can have strong security but poor privacy (e.g., employees accessing customer data without need). Both are necessary for comprehensive data protection.

</details>

---

**Q23.** Which of the following BEST describes the concept of "scoping" in the context of PCI DSS compliance?

A) Defining the geographic regions where card data is processed
B) Identifying all systems, people, and processes that store, process, or transmit cardholder data
C) Setting the timeline for achieving full PCI compliance
D) Determining which PCI DSS requirements apply to small merchants

<details><summary>Answer</summary>

**B) Identifying all systems, people, and processes that store, process, or transmit cardholder data**

PCI DSS scoping identifies the cardholder data environment (CDE) — all systems that store, process, or transmit cardholder data, plus systems that could impact their security. Reducing scope (through segmentation, tokenization) reduces compliance burden. Scoping is not about geography, timelines, or merchant size tiers.

</details>

---

**Q24.** A company stores employee performance reviews in a shared drive accessible to all managers. An employee requests to see what data the company holds about them. Under GDPR, what right is the employee exercising?

A) Right to erasure
B) Right to portability
C) Right of access
D) Right to rectification

<details><summary>Answer</summary>

**C) Right of access**

GDPR Article 15 grants data subjects the right of access — the right to obtain confirmation of whether personal data is being processed and to receive a copy of that data. Right to erasure (Article 17) is the right to be forgotten. Right to portability (Article 20) allows receiving data in a machine-readable format. Right to rectification (Article 16) allows correcting inaccurate data.

</details>

---

**Q25.** Which term describes classifying and protecting information based on the potential damage its unauthorized disclosure would cause?

A) Data labeling
B) Impact-based classification
C) Need-to-know access control
D) Sensitivity assessment

<details><summary>Answer</summary>

**B) Impact-based classification**

Impact-based classification assigns classification levels based on the potential harm (impact) from unauthorized disclosure, modification, or destruction. This is the foundational approach to data classification — higher potential harm = higher classification. Data labeling is the act of marking data with its classification. Need-to-know is an access control principle. Sensitivity assessment evaluates classification but is part of the broader impact-based approach.

</details>

---
