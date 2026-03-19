**Q1.** Which access control model grants or denies access based on the sensitivity label of the object and the clearance of the subject?

A) Discretionary access control (DAC)
B) Mandatory access control (MAC)
C) Role-based access control (RBAC)
D) Attribute-based access control (ABAC)

<details><summary>Answer</summary>

**B) Mandatory access control (MAC)**

MAC is policy-driven access control enforced by the system based on security labels (subject clearance vs. object sensitivity). Users cannot override the policy — the system administrator sets it. DAC allows owners to grant access to others at their discretion. RBAC grants access based on job role. ABAC considers multiple attributes (role, time, location, etc.) to make access decisions.

</details>

---

**Q2.** A company implements a policy where all employees are granted access to resources based solely on their job function. Which access control model is being applied?

A) Mandatory access control
B) Discretionary access control
C) Role-based access control
D) Rule-based access control

<details><summary>Answer</summary>

**C) Role-based access control**

RBAC assigns users to roles, and permissions are assigned to roles rather than individuals. Users inherit permissions based on their job role. This simplifies administration (especially when employees change roles) and aligns with least privilege. DAC lets owners assign permissions. MAC uses labels. Rule-based access control uses if-then rules (often implemented in firewalls) regardless of user role.

</details>

---

**Q3.** During an access review, a security team discovers that employees who transferred departments still have access to their previous department's resources. Which control failure does this represent?

A) Inadequate segregation of duties
B) Failure to enforce the principle of least privilege through access recertification
C) Missing preventive controls at the application layer
D) Inadequate logging and monitoring

<details><summary>Answer</summary>

**B) Failure to enforce the principle of least privilege through access recertification**

This is a classic access creep (privilege creep) scenario — users accumulate permissions over time without revocation. Access recertification (periodic review and validation of access rights) is the control that should catch and remediate this. The principle of least privilege requires that access be limited to what is currently needed, requiring revocation when roles change.

</details>

---

**Q4.** Which authentication factor category does a fingerprint scanner represent?

A) Something you know
B) Something you have
C) Something you are
D) Somewhere you are

<details><summary>Answer</summary>

**C) Something you are**

Biometrics (fingerprints, iris scans, facial recognition, voice patterns) represent "something you are" — inherence factors. "Something you know" includes passwords and PINs. "Something you have" includes smart cards, hardware tokens, and mobile devices. "Somewhere you are" is location-based authentication (geolocation). MFA combines two or more of these categories.

</details>

---

**Q5.** A user's account is locked after five consecutive failed login attempts. Which authentication security control is being applied?

A) Account lockout policy
B) Password complexity requirement
C) Multi-factor authentication
D) Session timeout

<details><summary>Answer</summary>

**A) Account lockout policy**

Account lockout policies prevent brute force attacks by disabling an account after a specified number of failed authentication attempts. This makes online password attacks impractical. Password complexity requirements govern what passwords contain. MFA adds additional authentication factors. Session timeout terminates inactive sessions. Account lockout must be balanced against denial-of-service risk from intentional lockouts.

</details>

---

**Q6.** Which identity management concept allows a user to authenticate once and access multiple applications without re-authenticating?

A) Federated identity
B) Single sign-on (SSO)
C) Multi-factor authentication
D) Identity federation

<details><summary>Answer</summary>

**B) Single sign-on (SSO)**

SSO allows a user to authenticate once and access multiple applications within a domain without re-authenticating. Federated identity and identity federation extend SSO across organizational boundaries using trust relationships (e.g., SAML, OAuth). MFA adds authentication factors. SSO improves user experience and can improve security by reducing password fatigue, though it also creates a single point of compromise risk.

</details>

---

**Q7.** An organization uses SAML to enable employees to access partner company applications with their corporate credentials. Which concept does this describe?

A) Single sign-on within the organization
B) Federated identity management across organizations
C) Role-based access control enforcement
D) Privileged identity management

<details><summary>Answer</summary>

**B) Federated identity management across organizations**

Federated identity management uses trust relationships and standards (SAML, OAuth, OpenID Connect) to allow users from one organization (identity provider) to access resources at another organization (service provider) using their home credentials. SAML is specifically designed for web-based SSO in federated environments. This differs from intra-organizational SSO, which doesn't cross organizational boundaries.

</details>

---

**Q8.** What is the PRIMARY purpose of privileged access management (PAM)?

A) To prevent all privileged accounts from being used
B) To control, monitor, and audit the use of privileged accounts and credentials
C) To encrypt all communications from privileged accounts
D) To restrict privileged accounts to physically secured workstations

<details><summary>Answer</summary>

**B) To control, monitor, and audit the use of privileged accounts and credentials**

PAM solutions manage highly privileged accounts (administrators, root, service accounts) by vaulting credentials, enforcing just-in-time access, recording privileged sessions, and providing audit trails. Privileged accounts are the highest-value targets for attackers. PAM reduces the risk of credential theft, insider threats, and lateral movement after a compromise.

</details>

---

**Q9.** Which protocol is specifically designed for federated identity and is widely used for web-based SSO between organizations?

A) LDAP
B) RADIUS
C) SAML
D) Kerberos

<details><summary>Answer</summary>

**C) SAML**

SAML (Security Assertion Markup Language) is an XML-based open standard for exchanging authentication and authorization data between an identity provider (IdP) and a service provider (SP). It is widely used for web-based SSO across organizational boundaries. LDAP is a directory protocol. RADIUS is used for network access authentication. Kerberos is used for intra-domain authentication (Active Directory).

</details>

---

**Q10.** What is the security concern with using shared accounts?

A) Shared accounts are more difficult for attackers to target
B) Shared accounts make it impossible to attribute actions to specific individuals, defeating accountability
C) Shared accounts require more complex password policies
D) Shared accounts consume more network bandwidth

<details><summary>Answer</summary>

**B) Shared accounts make it impossible to attribute actions to specific individuals, defeating accountability**

When multiple users share an account, individual accountability is impossible — you cannot determine which person performed a specific action. This undermines audit trails, incident investigation, and non-repudiation. Individual accounts with unique identifiers are required for proper accountability. The only acceptable shared accounts are true service accounts not used for interactive logins.

</details>

---

**Q11.** A user must provide their username, password, and a one-time code from a mobile app to log in. This is an example of:

A) Two-step verification using single-factor authentication
B) Multi-factor authentication combining something you know and something you have
C) Biometric authentication combined with knowledge-based authentication
D) Single sign-on with enhanced security

<details><summary>Answer</summary>

**B) Multi-factor authentication combining something you know and something you have**

This uses two factors from different categories: the password (something you know) and the mobile app OTP (something you have — the enrolled device). MFA requires factors from at least two different categories. Two-step verification using the same factor category (e.g., two passwords) is not true MFA. This is a key distinction in CISSP: factors must be from different categories.

</details>

---

**Q12.** Which directory service protocol is most commonly used for authentication in enterprise environments when centralized user management is needed?

A) RADIUS
B) TACACS+
C) LDAP
D) OAuth

<details><summary>Answer</summary>

**C) LDAP**

LDAP (Lightweight Directory Access Protocol) is the standard protocol for accessing and maintaining directory information, including user accounts and authentication data. Active Directory uses LDAP (and Kerberos). RADIUS provides centralized authentication for network access. TACACS+ is used for network device administration (Cisco). OAuth is an authorization framework (not authentication) for API access delegation.

</details>

---

**Q13.** In identity management, what is the role of the identity provider (IdP)?

A) To store and manage application data on behalf of users
B) To authenticate users and provide identity assertions to service providers
C) To manage service-level agreements between organizations
D) To encrypt credentials before transmission to service providers

<details><summary>Answer</summary>

**B) To authenticate users and provide identity assertions to service providers**

The identity provider (IdP) authenticates the user and issues identity assertions (e.g., SAML tokens, JWT tokens) to service providers (SPs). The SP trusts the IdP's assertion without requiring the user to authenticate again. Examples of IdPs: Microsoft Azure AD, Okta, Google Workspace. The IdP is the foundation of federated identity and SSO architectures.

</details>

---

**Q14.** What is a time-based one-time password (TOTP) and why is it more secure than a static password?

A) TOTP is valid for only a short time window (typically 30 seconds), making captured credentials useless after expiration
B) TOTP is longer than static passwords, providing more entropy
C) TOTP is generated server-side, eliminating client-side credential storage
D) TOTP requires biometric verification before generation

<details><summary>Answer</summary>

**A) TOTP is valid for only a short time window (typically 30 seconds), making captured credentials useless after expiration**

TOTP generates a new code every 30 seconds using a shared secret and the current time (RFC 6238). Even if an attacker captures the OTP, it expires almost immediately, making replay attacks ineffective. Static passwords remain valid indefinitely after capture. TOTP is a "something you have" factor when implemented via an authenticator app tied to a specific device.

</details>

---

**Q15.** An organization implements just-in-time (JIT) access for privileged accounts. What is the PRIMARY security benefit?

A) Eliminating the need for multi-factor authentication for privileged users
B) Reducing the window of exposure for privileged credentials by granting access only when needed
C) Improving system performance by reducing active privileged session overhead
D) Simplifying access review processes for auditors

<details><summary>Answer</summary>

**B) Reducing the window of exposure for privileged credentials by granting access only when needed**

JIT access provisions privileged access only when required for a specific task, then revokes it afterward. Standing privileged access (always-on admin accounts) creates persistent high-value targets. JIT dramatically reduces the attack surface: even if credentials are compromised, they expire after the authorized task. This is a core PAM strategy aligned with zero-trust principles.

</details>

---

**Q16.** What type of attack involves an attacker guessing or cracking account credentials by systematically trying many password combinations?

A) Social engineering attack
B) Password spraying attack
C) Credential stuffing attack
D) Brute force attack

<details><summary>Answer</summary>

**D) Brute force attack**

A brute force attack systematically tries every possible password combination. A dictionary attack uses common words. Password spraying tries a few common passwords against many accounts (avoiding lockout). Credential stuffing uses username/password pairs from previous breaches against other services. Social engineering manipulates people rather than systems. All are password attacks, but brute force specifically exhausts all combinations.

</details>

---

**Q17.** Which access control concept ensures that employees cannot perform all steps of a sensitive process alone?

A) Least privilege
B) Need to know
C) Separation of duties
D) Job rotation

<details><summary>Answer</summary>

**C) Separation of duties**

Separation of duties (SoD) divides a sensitive task or process among multiple individuals so no single person can complete a harmful action unilaterally. It prevents fraud and errors. Examples: the person who requests a payment cannot also approve and execute it. Least privilege limits permissions. Need to know limits access to information. Job rotation detects fraud through personnel movement.

</details>

---

**Q18.** An organization uses a directory service to manage user accounts, groups, and access policies centrally. Which technology BEST describes this?

A) PKI
B) Identity and Access Management (IAM) system
C) Security information and event management (SIEM)
D) Network access control (NAC)

<details><summary>Answer</summary>

**B) Identity and Access Management (IAM) system**

An IAM system centralizes the management of user identities, authentication, authorization, and access policies. It encompasses directory services, SSO, MFA, role management, and access review. PKI manages cryptographic keys and certificates. SIEM aggregates and analyzes security logs. NAC controls which devices can connect to the network.

</details>

---

**Q19.** What is a key security concern with OAuth 2.0 when used for authorization?

A) OAuth 2.0 cannot be used with mobile applications
B) OAuth 2.0 tokens can be intercepted if not properly protected, enabling token theft attacks
C) OAuth 2.0 does not support refresh tokens for long-lived sessions
D) OAuth 2.0 requires users to share passwords with third-party applications

<details><summary>Answer</summary>

**B) OAuth 2.0 tokens can be intercepted if not properly protected, enabling token theft attacks**

OAuth 2.0 access tokens are bearer tokens — whoever possesses the token can use it. If tokens are transmitted over unencrypted channels or stored insecurely, they can be stolen and reused. Protections include HTTPS for all token exchanges, short token lifetimes, and PKCE (Proof Key for Code Exchange) for public clients. OAuth 2.0 actually solved the password sharing problem (answer D describes the old approach).

</details>

---

**Q20.** During provisioning, a new employee is granted access to all resources accessible by other members of their team. What provisioning method is being used?

A) Manual provisioning based on job requirements
B) Role-based provisioning (cloning from similar users)
C) Self-service provisioning with manager approval
D) Automated provisioning via SCIM

<details><summary>Answer</summary>

**B) Role-based provisioning (cloning from similar users)**

Granting a new user the same access as their team members is user cloning — a common but risky approach. It can propagate excessive permissions that team members accumulated over time. Best practice is role-based provisioning from a defined role template representing minimum required access. Cloning is convenient but violates least privilege if existing accounts have excess access.

</details>

---

**Q21.** What is the function of a certificate revocation list (CRL) in PKI?

A) To list all valid certificates issued by a CA
B) To publish certificates that have been revoked before their expiration date
C) To manage key renewal requests from certificate holders
D) To encrypt certificate transmission between parties

<details><summary>Answer</summary>

**B) To publish certificates that have been revoked before their expiration date**

A CRL is a signed list published by a CA containing serial numbers of certificates that have been revoked before their expiration (due to key compromise, changed affiliation, etc.). Relying parties check the CRL before trusting a certificate. OCSP (Online Certificate Status Protocol) provides real-time revocation checking, replacing CRL polling in many modern deployments.

</details>

---

**Q22.** Which biometric characteristic has the HIGHEST False Acceptance Rate (FAR) concern from a security perspective?

A) Retinal scan
B) Fingerprint
C) Signature dynamics
D) Facial recognition

<details><summary>Answer</summary>

**D) Facial recognition**

Facial recognition systems, especially earlier generations, have been shown to have higher false acceptance rates (accepting unauthorized individuals) due to spoofing (photos, masks) and bias issues. Retinal scans have very low FAR due to the uniqueness of retinal patterns. Fingerprints have low FAR. Signature dynamics can be fooled with practice. However, modern facial recognition with liveness detection has improved significantly.

</details>

---

**Q23.** What does the crossover error rate (CER) measure in biometric systems?

A) The maximum number of failed authentication attempts before lockout
B) The point where false acceptance rate equals false rejection rate, indicating overall accuracy
C) The percentage of enrolled users who cannot be authenticated
D) The time required to process a biometric scan

<details><summary>Answer</summary>

**B) The point where false acceptance rate equals false rejection rate, indicating overall accuracy**

CER (Crossover Error Rate), also called Equal Error Rate (EER), is the point at which FAR (accepting unauthorized users) equals FRR (rejecting authorized users). Lower CER indicates a more accurate biometric system. This metric allows comparison between different biometric systems. Systems can be tuned to favor lower FAR (security-focused) or lower FRR (usability-focused), but CER represents the balance point.

</details>

---

**Q24.** An organization implements zero-trust architecture. Which access control principle is MOST central to zero trust?

A) All internal network traffic is trusted by default
B) Never trust, always verify — every request is authenticated and authorized regardless of source
C) Physical security perimeter controls are sufficient for internal resources
D) Users are granted broad access to improve productivity

<details><summary>Answer</summary>

**B) Never trust, always verify — every request is authenticated and authorized regardless of source**

Zero trust eliminates the concept of implicit trust based on network location. Every access request — regardless of whether it comes from inside or outside the network — must be explicitly authenticated, authorized, and continuously validated. Zero trust assumes breach and applies least privilege, micro-segmentation, and strong identity verification to all resources.

</details>

---

**Q25.** Which authentication vulnerability does multi-factor authentication PRIMARILY mitigate?

A) Social engineering attacks
B) Password-based attacks (stolen, guessed, or cracked passwords)
C) Session hijacking after successful authentication
D) Physical theft of devices

<details><summary>Answer</summary>

**B) Password-based attacks (stolen, guessed, or cracked passwords)**

MFA's primary value is that a compromised password alone is insufficient for access — the attacker also needs the second factor. This mitigates phishing, credential stuffing, brute force, and password reuse attacks. MFA does not fully prevent social engineering (an attacker can socially engineer MFA codes), session hijacking (the session after authentication), or physical device theft (though possession-based MFA adds complexity).

</details>

---
