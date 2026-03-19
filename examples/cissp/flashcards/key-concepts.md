## Security and Risk Management

**CIA Triad** → Confidentiality (prevent unauthorized disclosure), Integrity (prevent unauthorized modification), Availability (ensure systems are accessible when needed) | Every security control maps to one or more of these three properties

**Non-repudiation** → The ability to prove that an action was performed by a specific party — they cannot credibly deny it; achieved via digital signatures and audit logs | Repudiate = deny; non-repudiation = cannot deny

**Due Care** → Taking action to prevent foreseeable harm — doing the right thing | Due Diligence = knowing the right thing; Due Care = doing it; both needed to avoid negligence

**Due Diligence** → Investigating and understanding risks before taking action — knowing the risks | Precedes due care; together they establish reasonable behavior

**Risk** → The probability that a threat will exploit a vulnerability and cause harm; Risk = Probability × Impact | Not all risk can be eliminated; the goal is managing it to acceptable levels

**Threat** → Any potential danger to an asset (natural disaster, human attacker, system failure) | Distinguished from threat agent (the entity causing the threat)

**Threat Agent** → The entity that exploits a vulnerability (hacker, disgruntled employee, nation-state, flood) | Also called threat actor

**Vulnerability** → A weakness in a system, process, or control that could be exploited by a threat | Not all vulnerabilities are exploitable in a given environment

**Risk Treatment Options** → Avoid (eliminate the activity), Mitigate (reduce likelihood/impact), Transfer (insurance), Accept (document and proceed) | Also called risk response strategies

**Residual Risk** → The risk remaining after controls have been applied; must be formally accepted by management | Total risk - control effectiveness = residual risk

**Annual Loss Expectancy (ALE)** → ALE = Single Loss Expectancy (SLE) × Annual Rate of Occurrence (ARO); used for quantitative risk analysis | Compare ALE to cost of countermeasure to determine cost-effectiveness

**Business Impact Analysis (BIA)** → Identifies critical business functions and determines RTO, RPO, and MTD for each | Foundation of business continuity planning

**RTO (Recovery Time Objective)** → Maximum acceptable time to restore a system after a disruption | How long can we be down?

**RPO (Recovery Point Objective)** → Maximum acceptable data loss measured in time; drives backup frequency | How much data can we afford to lose?

**MTD (Maximum Tolerable Downtime)** → The longest period the organization can survive without a critical function | MTD ≥ RTO; if RTO > MTD, the business cannot survive the outage

**Security Policy** → High-level management document expressing security intent and direction; strategic level | Policy → Standard → Guideline → Procedure (hierarchy)

**Administrative Controls** → Management-based controls: policies, procedures, training, background checks, job rotation | Also called management controls; govern people and processes

**Technical Controls** → Technology-based controls: firewalls, encryption, IDS, access control systems | Also called logical controls; implemented in hardware and software

**Physical Controls** → Controls protecting physical access: locks, cameras, mantraps, guards, fences | Protect the physical layer of the CIA triad

**Preventive Control** → Stops an incident before it occurs (firewall, lock, training) | Example: requiring badge access prevents unauthorized physical entry

**Detective Control** → Identifies incidents that have occurred (CCTV, IDS, audit logs) | Example: security cameras detect after the fact

**Corrective Control** → Restores systems after an incident (patches, backups, incident response) | Fixes the problem after detection

**Deterrent Control** → Discourages attacks without physically preventing them (warning signs, security cameras visible) | Psychological effect rather than physical barrier

## Asset Security

**Data Owner** → Business manager responsible for classifying data and determining its value and handling requirements | Accountable for data; delegates implementation to custodian

**Data Custodian** → IT/operations staff responsible for implementing and maintaining controls as directed by the owner | Implements the owner's policies; does not make classification decisions

**Data Classification** → Process of categorizing data based on its value and the impact of unauthorized disclosure | Government: Top Secret, Secret, Confidential, Unclassified; Corporate: Restricted, Confidential, Internal, Public

**Data at Rest** → Data stored on disk, tape, or other storage media; protected primarily by encryption and access controls | Encryption of storage media is the primary defense

**Data in Transit** → Data moving across networks; protected by TLS, VPN, IPsec | Encryption of the communication channel is the primary defense

**Data in Use** → Data being actively processed in memory or applications; most difficult state to protect | Access controls and application security are primary defenses

**Tokenization** → Replacing sensitive data with a non-sensitive surrogate (token) that maps back to the original in a secure vault | Token has no mathematical relationship to original; used heavily in PCI DSS compliance

**Data Masking** → Replacing real data with structurally similar fake data for testing environments | Protects real data from being exposed in non-production environments

**Anonymization** → Irreversible removal of all identifying information from data | True anonymization removes data from privacy law scope; cannot be reversed

**Pseudonymization** → Replacing identifiers with pseudonyms; reversible with the right key | Still subject to privacy laws (GDPR treats as personal data with appropriate keys)

**Data Retention** → Policies defining how long data must be kept (legal minimum) and when it must be destroyed (maximum) | Keeping data longer than required increases liability

**Data Remanence** → Residual data that remains on storage media after deletion; requires secure overwriting or physical destruction | SSDs are particularly challenging due to wear-leveling

**Data Sovereignty** → Data is subject to the laws of the jurisdiction where it physically resides | Critical consideration for cloud storage location decisions

## Security Architecture and Engineering

**Bell-LaPadula Model** → Confidentiality model: No Read Up (NRU), No Write Down (NWD); prevents classified data from flowing to lower levels | Security clearance model used in government; focused on keeping secrets secret

**Biba Model** → Integrity model: No Read Down (NRD), No Write Up (NWU); prevents contamination from less trusted sources | Opposite of Bell-LaPadula; used where data accuracy matters most

**Clark-Wilson Model** → Integrity model using well-formed transactions, CDIs (constrained data items), and access triples | Commercial integrity model; separates users from data through transformation procedures

**Brewer-Nash (Chinese Wall) Model** → Prevents conflicts of interest; once you access data from Company A, you cannot access competitor Company B's data | Used in consulting and financial services

**Trusted Computing Base (TCB)** → All hardware, software, and firmware responsible for enforcing security policy; must be as small as possible | Smaller TCB = smaller attack surface = easier to verify

**Reference Monitor** → Abstract concept of the access control enforcement mechanism; must be always-invoked, tamper-proof, and verifiable | The security kernel implements the reference monitor concept

**Defense in Depth** → Multiple independent layers of security controls so that failure of one layer doesn't compromise the system | No single point of failure; also called layered security

**Open Design** → Security should not depend on the secrecy of the design; only on the secrecy of keys | Public cryptographic algorithms (AES, RSA) are stronger than proprietary secret ones

**Fail Secure (Fail Closed)** → System defaults to denying access when it fails | Appropriate for security-critical systems; opposite of fail open

**Separation of Privilege** → Operations require multiple conditions/parties to be satisfied | Prevents any single entity from having all necessary permissions

**Least Common Mechanism** → Minimize shared resources and mechanisms between subjects; reduces covert channel risk | Shared resources can become covert channels

**Symmetric Encryption** → Same key for encryption and decryption; fast; key distribution is the challenge | Examples: AES, 3DES, RC4; used for bulk data encryption

**Asymmetric Encryption** → Different keys (public/private pair) for encryption and decryption; slower; solves key distribution | Examples: RSA, ECC; used for key exchange and digital signatures

**AES** → Advanced Encryption Standard; FIPS 197; key sizes 128/192/256 bits; current US federal standard | Replaced DES; block cipher used for protecting sensitive data

**RSA** → Asymmetric algorithm based on factoring large prime numbers; used for key exchange and digital signatures | Key length typically 2048+ bits; being supplemented by ECC

**Digital Signature** → Created using sender's private key; verified with sender's public key; provides authenticity, integrity, non-repudiation | Does not encrypt content; proves who signed and that content wasn't altered

**Certificate Authority (CA)** → Issues and revokes digital certificates binding public keys to identities | Root of trust in PKI; must be highly secured; compromise affects all issued certificates

**PKI** → Public Key Infrastructure; framework for managing digital certificates and keys | Includes CAs, RAs, certificate repositories, CRL/OCSP, and certificate policies

**Hash Function** → One-way function producing fixed-length output (digest) from any input; cannot be reversed | Used for integrity verification and password storage; SHA-256/SHA-3 are current standards

**Salting** → Adding a unique random value to each password before hashing to defeat rainbow table attacks | Each user gets a unique salt; prevents identical passwords from producing identical hashes

**Perfect Forward Secrecy (PFS)** → Session keys are derived independently so compromise of long-term key doesn't compromise past sessions | Achieved via ephemeral Diffie-Hellman key exchange

**HSM** → Hardware Security Module; tamper-resistant hardware for generating, storing, and using cryptographic keys | Keys never leave the HSM in usable form; used for high-assurance cryptographic operations

**DMZ** → Demilitarized Zone; perimeter network between the internet and internal network for public-facing servers | If a DMZ server is compromised, attackers cannot directly reach internal systems

## Communication and Network Security

**OSI Model** → 7 layers: Physical, Data Link, Network, Transport, Session, Presentation, Application | Remember: "Please Do Not Throw Sausage Pizza Away" (P-D-N-T-S-P-A)

**TCP** → Transmission Control Protocol; connection-oriented, reliable, ordered delivery via 3-way handshake (SYN, SYN-ACK, ACK) | Layer 4; used for web, email, file transfer; adds reliability overhead

**UDP** → User Datagram Protocol; connectionless, unreliable, low overhead | Layer 4; used for real-time applications (VoIP, DNS, streaming) where speed > reliability

**SYN Flood** → DoS attack sending many SYN packets without completing handshake, exhausting server connection table | Mitigated by SYN cookies, rate limiting, firewall state tracking

**ARP Poisoning** → Attacker sends fake ARP replies linking their MAC to a legitimate IP, redirecting traffic | Enables man-in-the-middle on local network; mitigated by Dynamic ARP Inspection (DAI)

**DNS Poisoning** → Injecting false records into DNS cache to redirect users to malicious IP addresses | Mitigated by DNSSEC (digital signatures on DNS records)

**WPA3** → Wi-Fi Protected Access 3; uses SAE (Simultaneous Authentication of Equals) for stronger password-based authentication with forward secrecy | Current standard; replaces WPA2; provides protection against offline dictionary attacks

**IPsec** → Protocol suite for securing IP communications; provides authentication (AH) and encryption (ESP) at the network layer | Tunnel mode encrypts entire packet including headers; transport mode encrypts only payload

**TLS** → Transport Layer Security; successor to SSL; provides encrypted communication at the transport layer | Current standard: TLS 1.3; used for HTTPS, secure email, VPN

**802.1X** → Port-based Network Access Control; requires authentication before granting network access | Three components: supplicant (client), authenticator (switch/AP), authentication server (RADIUS)

**VLAN** → Virtual Local Area Network; logical segmentation of a physical network at Layer 2 | VLANs require routing to communicate; reduce broadcast domains and enable network segmentation

**Stateful Inspection Firewall** → Maintains connection state table; only allows packets matching established connections | More secure than packet filtering; knows context of traffic, not just individual packets

**IDS** → Intrusion Detection System; monitors and alerts on suspicious activity; cannot block | Passive monitoring; generates alerts for human review; in-band or out-of-band

**IPS** → Intrusion Prevention System; monitors and automatically blocks detected threats | Inline with traffic; active prevention; may cause false positive blocking of legitimate traffic

**NAT** → Network Address Translation; translates private to public IP addresses; hides internal network structure | Conserves public IPs; provides obscurity but not security; doesn't prevent inbound attacks

## Identity and Access Management

**Authentication Factors** → Something you know (password/PIN), something you have (token/card), something you are (biometric), somewhere you are (location) | MFA requires two or more different factor categories

**MFA** → Multi-Factor Authentication; requires two or more factors from different categories | Primarily mitigates password-based attacks; compromised password alone is insufficient

**SSO** → Single Sign-On; authenticate once, access multiple applications | Improves UX; reduces password fatigue; creates single point of compromise risk

**SAML** → Security Assertion Markup Language; XML-based standard for federated SSO between organizations | IdP authenticates user and issues assertions to SPs; widely used for enterprise federated identity

**OAuth 2.0** → Authorization framework allowing applications to access resources on behalf of users without sharing credentials | Access token authorizes specific scopes; bearer token — possession grants access

**LDAP** → Lightweight Directory Access Protocol; standard for accessing directory information (user accounts, groups) | Active Directory uses LDAP; port 389 (plain), 636 (LDAPS)

**Kerberos** → Authentication protocol using tickets issued by Key Distribution Center (KDC) | Default authentication for Active Directory; tickets have limited lifetime; vulnerable to Pass-the-Ticket attacks

**RBAC** → Role-Based Access Control; permissions assigned to roles; users assigned to roles | Simplifies administration; scales well; aligns with job functions

**MAC** → Mandatory Access Control; system-enforced access based on sensitivity labels and clearance | Users cannot override; used in high-security government systems; Bell-LaPadula implements MAC

**DAC** → Discretionary Access Control; owner grants access to others at their discretion | Most common in commercial systems; flexible but difficult to manage at scale

**ABAC** → Attribute-Based Access Control; access decisions based on multiple attributes (role, time, location, device) | Most flexible; enables fine-grained policies; complex to implement and manage

**PAM** → Privileged Access Management; controls, monitors, and audits privileged account usage | Vaults credentials; enables just-in-time access; records privileged sessions; reduces insider threat risk

**Just-in-Time Access** → Privileged access provisioned only when needed for a specific task, then revoked | Reduces standing privilege; limits exposure window even if credentials are compromised

**Access Creep (Privilege Creep)** → Accumulation of excessive permissions over time as users change roles without access revocation | Mitigated by periodic access recertification and deprovisioning processes

**Separation of Duties** → Critical tasks divided among multiple individuals so no single person can complete a harmful action | Prevents fraud; requires collusion to circumvent; example: approval and execution of payments separated

**Crossover Error Rate (CER)** → Point where False Acceptance Rate equals False Rejection Rate; lower CER = more accurate biometric | Also called Equal Error Rate (EER); used to compare biometric system accuracy

**Zero Trust** → Security model where no user or system is implicitly trusted; verify every request explicitly | "Never trust, always verify"; assumes breach; applies least privilege and continuous validation

## Security Assessment and Testing

**Penetration Testing** → Authorized simulated attack to exploit vulnerabilities and demonstrate real-world impact | Goes beyond vulnerability assessment; requires explicit written authorization

**Black Box Test** → Tester has no prior knowledge of the target; simulates external attacker | Most realistic for external threat modeling; least efficient

**White Box Test** → Tester has full knowledge (architecture, source code, credentials); most thorough | Also called crystal box; simulates insider or allows comprehensive code review

**Gray Box Test** → Tester has partial knowledge; balances realism and thoroughness | Most common in practice; simulates an insider or authenticated user

**CVSS** → Common Vulnerability Scoring System; 0–10 score reflecting vulnerability severity | Must be contextualized with environment — air-gapped systems are lower risk despite high CVSS

**SAST** → Static Application Security Testing; analyzes source code without execution | Finds issues early (shift left); white box approach; can have many false positives

**DAST** → Dynamic Application Security Testing; tests running application from outside | Black box approach; finds runtime vulnerabilities; simulates attacker perspective

**Fuzzing** → Providing invalid/random inputs to applications to find crashes and vulnerabilities | Particularly effective for finding buffer overflows and input validation flaws

**Access Recertification** → Periodic review of user access rights to confirm or revoke based on current need | Detects access creep; required by PCI DSS, SOX, HIPAA; also called access certification

**Security Baseline** → Minimum acceptable security configuration for a system type | Derived from CIS Benchmarks, DISA STIGs; deviations indicate potential security issues

**Red Team** → Simulates advanced adversary; tests detection and response capabilities without blue team knowledge | Full adversarial simulation including social engineering and physical access

**Purple Team** → Red and blue teams working together to improve defenses collaboratively | Combines offensive knowledge with defensive improvement

## Security Operations

**Incident Response Lifecycle** → Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned | PICERL; each phase feeds the next; preparation is ongoing

**Chain of Custody** → Documentation of who handled evidence, when, and how; ensures admissibility | Gap in chain of custody can make evidence inadmissible in court

**Order of Volatility** → Collection order: Memory → Network connections → Running processes → Disk → Backup media | Collect most volatile evidence first; RAM disappears when power is cut

**SIEM** → Security Information and Event Management; aggregates, correlates, and analyzes logs from multiple sources | Enables detection of complex multi-system attacks; provides central visibility for SOC

**RTO** → Recovery Time Objective; maximum acceptable downtime before restoration must occur | How long can we be down?

**RPO** → Recovery Point Objective; maximum acceptable data loss in time | How much data can we afford to lose? Drives backup frequency

**Hot Site** → Fully operational alternate facility with real-time data; lowest RTO, highest cost | Ready to take over within minutes to hours

**Warm Site** → Has hardware but needs software/data restoration; moderate cost and RTO | Ready within hours to days

**Cold Site** → Space and power only; no equipment; lowest cost, highest RTO | Ready within days to weeks

**Differential Backup** → Captures changes since the last full backup; grows over time | Restore requires: last full + last differential (two pieces)

**Incremental Backup** → Captures changes since the last backup of any type; smaller but more restore pieces | Restore requires: last full + all incrementals since (more pieces, but each is smaller)

**Business Continuity Plan (BCP)** → Plan for maintaining essential business functions during a disruption | Focuses on continuing operations; broader than DRP

**Disaster Recovery Plan (DRP)** → Plan for restoring IT systems and data after a disaster | IT-focused subset of BCP; includes RTO/RPO targets and recovery procedures

**Ransomware** → Malware encrypting victim data and demanding payment for decryption key | Mitigated by: isolated backups, endpoint detection, network segmentation, patching

**Logic Bomb** → Malware that remains dormant until triggered by a condition (date, event, action) | Often planted by insiders; can be very destructive when triggered

**Worm** → Self-replicating malware that spreads automatically across networks without a host file | Spreads faster than viruses; classic examples: Slammer, WannaCry, Morris worm

## Software Development Security

**SDLC** → Software Development Lifecycle; phases: Requirements → Design → Development → Testing → Deployment → Maintenance | Security must be integrated at every phase (shift left)

**Shift Left** → Moving security activities earlier in the development lifecycle to find issues cheaper | Cost to fix: Requirements (1x) → Testing (10x) → Production (100x)

**Threat Modeling** → Systematically identifying and addressing threats during design; STRIDE methodology | STRIDE: Spoofing, Tampering, Repudiation, Information Disclosure, DoS, Elevation of Privilege

**SQL Injection** → Unvalidated user input incorporated into SQL queries, allowing manipulation of database | Prevention: parameterized queries (prepared statements), stored procedures, input validation

**XSS (Cross-Site Scripting)** → Injecting malicious scripts into web pages viewed by other users | Types: Reflected (non-persistent), Stored (persistent), DOM-based; prevention: output encoding, CSP

**CSRF (Cross-Site Request Forgery)** → Tricks user's browser into making unintended requests to an authenticated site | Prevention: anti-CSRF tokens, SameSite cookie attribute, checking Referer header

**Buffer Overflow** → Writing beyond allocated memory corrupts adjacent memory; can allow code execution | Prevention: ASLR, DEP/NX, stack canaries, bounds checking, safe languages

**Command Injection** → Unsanitized input executed as OS commands | Prevention: avoid shell execution; use safe APIs; validate and sanitize all input

**OWASP Top 10** → List of the most critical web application security risks; updated periodically | Current top risks include injection, broken authentication, XSS, insecure design, SSRF

**Input Validation** → Ensuring user input conforms to expected format before processing | Use allowlists (define what's acceptable); validate server-side; never trust client-side validation

**Parameterized Queries** → Separate SQL structure from user data; prevents SQL injection by design | Also called prepared statements; the primary defense against SQL injection

**Code Signing** → Digital signature on software verifying authenticity and integrity of publisher | Prevents supply chain attacks; OS may warn about or block unsigned software

**SBOM** → Software Bill of Materials; inventory of all components and dependencies in software | Enables rapid identification of affected systems when vulnerabilities are disclosed

**SAST** → Static Application Security Testing; analyzes source code without execution; finds issues early | White box approach; integrated into IDE and CI/CD pipeline

**Race Condition** → Timing-dependent vulnerability where outcome depends on relative timing of concurrent events | TOCTOU (Time-Of-Check Time-Of-Use) is a classic example; mitigated by mutexes and atomic operations

**DevSecOps** → Cultural practice of embedding security into DevOps workflows | Security is everyone's responsibility; automated security testing in CI/CD pipelines
