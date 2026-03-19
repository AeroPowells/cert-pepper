**Q1.** Which software development methodology incorporates security activities throughout every sprint, with security requirements treated like any other user story?

A) Waterfall
B) DevSecOps
C) Spiral model
D) Agile with security integrated

<details><summary>Answer</summary>

**D) Agile with security integrated**

Integrating security into Agile development means treating security requirements as user stories, performing security reviews within sprints, and conducting automated security testing in CI/CD pipelines. DevSecOps is the broader cultural practice of embedding security into the DevOps workflow. Waterfall is sequential and typically separates security review to late stages. The Spiral model explicitly includes risk analysis but is not Agile.

</details>

---

**Q2.** An attacker discovers that a web application directly includes user input in a database query without sanitization. Which vulnerability is being exploited?

A) Cross-site scripting (XSS)
B) Cross-site request forgery (CSRF)
C) SQL injection
D) XML injection

<details><summary>Answer</summary>

**C) SQL injection**

SQL injection occurs when unvalidated user input is incorporated into SQL queries, allowing attackers to manipulate the query logic. Attackers can bypass authentication, extract data, modify records, or execute operating system commands. Prevention: parameterized queries (prepared statements) and stored procedures. XSS injects malicious scripts into web pages. CSRF tricks users into making unintended requests.

</details>

---

**Q3.** Which SDLC phase is MOST effective for identifying and eliminating security vulnerabilities at the lowest cost?

A) Testing phase
B) Deployment phase
C) Requirements and design phase
D) Maintenance phase

<details><summary>Answer</summary>

**C) Requirements and design phase**

The cost to fix a security vulnerability increases dramatically as development progresses. Fixing a design flaw during requirements/design costs 1x; fixing it during testing may cost 10–100x; fixing it in production may cost 100x or more (plus reputation damage). This is the "shift left" principle — identify and address security issues as early as possible in the SDLC.

</details>

---

**Q4.** What type of attack injects malicious scripts into web pages viewed by other users, potentially stealing session cookies or credentials?

A) SQL injection
B) Cross-site scripting (XSS)
C) Cross-site request forgery (CSRF)
D) Buffer overflow

<details><summary>Answer</summary>

**B) Cross-site scripting (XSS)**

XSS injects malicious client-side scripts (usually JavaScript) into web pages. When other users view the page, the script executes in their browser — potentially stealing session cookies, redirecting users, or performing actions on their behalf. Prevention: output encoding, Content Security Policy (CSP), input validation. Reflected XSS is non-persistent; stored (persistent) XSS is more dangerous.

</details>

---

**Q5.** What is the purpose of input validation in secure coding?

A) To improve application performance by pre-processing user input
B) To ensure all user input conforms to expected formats, types, and ranges before processing
C) To log all user input for security monitoring
D) To encrypt sensitive input fields before storage

<details><summary>Answer</summary>

**B) To ensure all user input conforms to expected formats, types, and ranges before processing**

Input validation ensures that data received from users or external sources conforms to expected patterns before being processed. This prevents injection attacks (SQL, XSS, command injection), buffer overflows, and format string vulnerabilities. The principle: never trust input from any external source. Validation should occur server-side (client-side validation can be bypassed). Use allowlists (what's acceptable) rather than denylists.

</details>

---

**Q6.** Which attack exploits the trust a web application has in an authenticated user's browser to perform unauthorized actions?

A) Cross-site scripting (XSS)
B) Cross-site request forgery (CSRF)
C) Session hijacking
D) Clickjacking

<details><summary>Answer</summary>

**B) Cross-site request forgery (CSRF)**

CSRF exploits a website's trust in the authenticated user's browser. An attacker tricks the user's browser into sending a malicious request to a site where the user is authenticated — the site processes it as legitimate because it has the user's valid session cookie. Prevention: anti-CSRF tokens (synchronizer tokens), SameSite cookie attribute, and checking the Referer header. XSS exploits users' trust in a website.

</details>

---

**Q7.** What is the MAIN security benefit of using parameterized queries (prepared statements) in database interactions?

A) They improve query execution speed through caching
B) They separate SQL code from user-supplied data, preventing SQL injection
C) They encrypt data before storing it in the database
D) They validate that users have appropriate database permissions

<details><summary>Answer</summary>

**B) They separate SQL code from user-supplied data, preventing SQL injection**

Parameterized queries define the SQL structure first, then supply user data as parameters — the database engine never interprets user input as SQL code. This fundamentally eliminates SQL injection by construction. Stored procedures with parameterized inputs achieve the same result. String concatenation of user input into SQL queries is the root cause of SQL injection vulnerabilities.

</details>

---

**Q8.** A developer stores user passwords as SHA-1 hashes in the database. Why is this INSUFFICIENT for password storage?

A) SHA-1 is not a widely supported algorithm
B) SHA-1 is fast, making it susceptible to brute force and rainbow table attacks; salting and slow hash functions are required
C) SHA-1 hashes are too long to store efficiently in databases
D) SHA-1 cannot handle special characters in passwords

<details><summary>Answer</summary>

**B) SHA-1 is fast, making it susceptible to brute force and rainbow table attacks; salting and slow hash functions are required**

Fast cryptographic hashes (MD5, SHA-1, SHA-256) are designed for speed, which makes them poor for password storage — attackers can compute billions of hashes per second. Password hashing requires slow adaptive functions (bcrypt, scrypt, Argon2) with per-password salts to defeat rainbow tables. Salts make identical passwords produce different hashes. The goal is to make brute force computationally expensive.

</details>

---

**Q9.** Which concept in secure software development ensures that software components can only perform actions explicitly permitted by their design?

A) Defense in depth
B) Principle of least privilege for software components
C) Secure defaults
D) Fail secure

<details><summary>Answer</summary>

**B) Principle of least privilege for software components**

Software components (processes, services, modules) should run with the minimum permissions required for their function. A web server process shouldn't run as root. A database account used by an application should have only SELECT/INSERT/UPDATE on specific tables — not DBA privileges. This limits the blast radius if a component is compromised: an attacker gains only the permissions of the compromised component.

</details>

---

**Q10.** What is the purpose of threat modeling in secure software development?

A) To identify security requirements for regulatory compliance
B) To systematically identify, prioritize, and address potential threats to an application during design
C) To document security incidents that occurred in previous versions
D) To train developers on secure coding practices

<details><summary>Answer</summary>

**B) To systematically identify, prioritize, and address potential threats to an application during design**

Threat modeling is a proactive process performed during design to identify potential threats, attack vectors, and vulnerabilities before code is written. Methodologies include STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege) and PASTA. Threat modeling produces a prioritized list of security requirements and mitigations. It enables "security by design" rather than bolted-on security.

</details>

---

**Q11.** An organization discovers that a third-party library used in its application contains a known vulnerability. Which software supply chain risk does this represent?

A) Zero-day vulnerability in internal code
B) Third-party component risk / dependency vulnerability
C) Insider threat from the development team
D) Misconfigurated development environment

<details><summary>Answer</summary>

**B) Third-party component risk / dependency vulnerability**

Modern applications depend heavily on third-party libraries and components. Vulnerabilities in these dependencies (like Log4Shell in Log4j) affect all applications using them. Software composition analysis (SCA) tools identify known vulnerabilities in dependencies. Maintaining a software bill of materials (SBOM) enables rapid identification of affected systems when new vulnerabilities are disclosed.

</details>

---

**Q12.** Which software development practice involves automatically building, testing, and (optionally) deploying code changes, with security tests integrated into the pipeline?

A) Agile development
B) Test-driven development
C) DevSecOps / CI/CD with security gates
D) Pair programming

<details><summary>Answer</summary>

**C) DevSecOps / CI/CD with security gates**

CI/CD (Continuous Integration/Continuous Deployment) pipelines automate build, test, and deployment processes. Integrating security tools (SAST, DAST, SCA, container scanning) into the pipeline creates security gates — code that fails security checks is blocked from deployment. This is the core of DevSecOps: automating security at the speed of development without slowing delivery.

</details>

---

**Q13.** What type of vulnerability occurs when an application executes operating system commands using unsanitized user input?

A) SQL injection
B) Command injection
C) LDAP injection
D) XML injection

<details><summary>Answer</summary>

**B) Command injection**

Command injection occurs when an application passes unsanitized user input to a system shell or OS command interpreter. Attackers can append additional commands using shell metacharacters (`;`, `|`, `&&`). Prevention: avoid OS command execution where possible; use parameterized APIs; validate and sanitize all input; run with minimal privileges. Command injection can give attackers complete system control.

</details>

---

**Q14.** Which OWASP resource provides a standardized list of the most critical web application security risks?

A) OWASP Testing Guide
B) OWASP ASVS (Application Security Verification Standard)
C) OWASP Top 10
D) OWASP SAMM

<details><summary>Answer</summary>

**C) OWASP Top 10**

The OWASP Top 10 is a regularly updated list of the most critical web application security risks (e.g., injection, broken authentication, XSS). It is widely used as a baseline for secure development and assessment. The Testing Guide provides detailed testing procedures. ASVS provides security requirements for application verification. SAMM is a software assurance maturity model. The Top 10 is the most recognized awareness resource.

</details>

---

**Q15.** A web application displays an error message that includes the full SQL query that failed. What security issue does this represent?

A) Poor logging configuration
B) Information disclosure through verbose error messages
C) A SQL injection vulnerability in the error handling code
D) Improper session management

<details><summary>Answer</summary>

**B) Information disclosure through verbose error messages**

Verbose error messages that expose internal implementation details (database queries, file paths, stack traces, version information) help attackers understand the system's architecture and identify attack vectors. Best practice: generic user-facing error messages, detailed error logging to secure server-side logs (never to the client). Error message content is a classic information leakage vulnerability in the OWASP Top 10.

</details>

---

**Q16.** What is the purpose of code signing?

A) To encrypt application code during transmission and storage
B) To verify the authenticity and integrity of software using a digital signature
C) To license software for use within a specific organization
D) To obfuscate source code to prevent reverse engineering

<details><summary>Answer</summary>

**B) To verify the authenticity and integrity of software using a digital signature**

Code signing uses a digital signature to verify that code came from a known, trusted publisher and has not been modified since signing. Operating systems use code signing to warn users about or block unsigned software. This helps prevent supply chain attacks where legitimate software is replaced with malicious versions. Code signing doesn't encrypt the code — it just verifies its origin and integrity.

</details>

---

**Q17.** Which security testing technique analyzes software behavior at runtime by executing the program and observing its outputs?

A) Static analysis
B) Dynamic analysis
C) Code review
D) Formal verification

<details><summary>Answer</summary>

**B) Dynamic analysis**

Dynamic analysis tests software while it is running — executing code and observing behavior, resource usage, network traffic, and system calls. This can detect vulnerabilities that only appear during execution (race conditions, runtime memory issues). Static analysis examines code without execution. Code review is a manual static analysis approach. Formal verification uses mathematical proofs to verify correctness.

</details>

---

**Q18.** What is a race condition vulnerability in software?

A) A vulnerability where the application uses more CPU than expected
B) A timing-dependent vulnerability where the outcome depends on the relative timing of concurrent events
C) A vulnerability caused by slow network connections
D) A bug introduced by processing data too quickly

<details><summary>Answer</summary>

**B) A timing-dependent vulnerability where the outcome depends on the relative timing of concurrent events**

A race condition occurs when multiple processes or threads access shared resources concurrently, and the security outcome depends on the timing. A classic example is TOCTOU (Time-of-Check to Time-of-Use): a check is performed, then the condition changes before the action based on that check occurs. Exploiting race conditions can bypass security checks, escalate privileges, or corrupt data. Mutexes and atomic operations are common mitigations.

</details>

---

**Q19.** An organization requires all software libraries to be sourced from an approved internal repository and verified before use. What security concern does this address?

A) Code quality and style standards
B) Software supply chain integrity and preventing introduction of malicious dependencies
C) License compliance management
D) Development environment standardization

<details><summary>Answer</summary>

**B) Software supply chain integrity and preventing introduction of malicious dependencies**

An approved internal repository (artifact repository) with verified, vetted packages reduces supply chain risk — developers can only use approved components, reducing the chance of malicious packages, typosquatting attacks (maliciously named packages), or unvetted libraries with vulnerabilities. This is especially critical given the increasing sophistication of software supply chain attacks.

</details>

---

**Q20.** What is the purpose of a software bill of materials (SBOM)?

A) To document the development team's contributions to a software project
B) To provide a complete inventory of components, libraries, and dependencies in a software product
C) To list software licenses purchased for development tools
D) To track bug counts and resolution status in a software project

<details><summary>Answer</summary>

**B) To provide a complete inventory of components, libraries, and dependencies in a software product**

An SBOM is a formal record of all open-source and commercial components in a software product — a "ingredients list" for software. When a new vulnerability is disclosed (e.g., Log4Shell), organizations with SBOMs can immediately identify which products are affected. US Executive Order 14028 and NTIA guidelines have made SBOMs a critical supply chain security requirement.

</details>

---

**Q21.** Which development practice involves two developers simultaneously working on the same code — one writes code while the other reviews it in real time?

A) Code review
B) Pair programming
C) Mob programming
D) Test-driven development

<details><summary>Answer</summary>

**B) Pair programming**

Pair programming has two developers working together at one workstation — a driver writes code while the navigator reviews, catches errors, and thinks ahead. This improves code quality and security by providing real-time review. Code review happens after code is written. Mob programming extends pairing to the whole team. Test-driven development involves writing tests before code. Pair programming is a preventive quality control that catches security issues early.

</details>

---

**Q22.** An application stores sensitive API keys in the source code repository. What security risk does this create?

A) Developers cannot access the API keys during development
B) API keys in source code can be exposed if the repository is accessed by unauthorized parties or made public
C) The API keys will expire faster due to repository encryption overhead
D) Continuous integration systems cannot process encrypted credentials in repositories

<details><summary>Answer</summary>

**B) API keys in source code can be exposed if the repository is accessed by unauthorized parties or made public**

Hardcoded credentials in source code are a critical security risk. If a repository is accidentally made public, or if an attacker gains access to source control, all credentials are compromised. Public GitHub repositories have been scanned by attackers to find API keys within hours of exposure. Best practice: use environment variables, secrets management systems (HashiCorp Vault, AWS Secrets Manager), and pre-commit hooks to detect secrets.

</details>

---

**Q23.** What is the security implication of improper session management in a web application?

A) Session data is stored inefficiently, causing performance issues
B) Attackers can steal, forge, or fixate session tokens to impersonate authenticated users
C) Users must re-authenticate too frequently, reducing productivity
D) Server-side session storage becomes a bottleneck

<details><summary>Answer</summary>

**B) Attackers can steal, forge, or fixate session tokens to impersonate authenticated users**

Improper session management enables session hijacking (stealing tokens via XSS, sniffing), session fixation (forcing a known token), and session replay attacks. Best practices: generate cryptographically random session tokens, use secure/HttpOnly/SameSite cookie flags, implement session timeout and invalidation on logout, and regenerate session ID on authentication state changes.

</details>

---

**Q24.** Which SDLC model uses a risk-driven approach where development proceeds in spirals, with each cycle including planning, risk analysis, engineering, and evaluation?

A) Waterfall model
B) Agile model
C) Spiral model
D) Prototype model

<details><summary>Answer</summary>

**C) Spiral model**

The Spiral model (Barry Boehm) combines iterative development with systematic risk management. Each spiral cycle includes: planning (objectives and constraints), risk analysis (identify and resolve risks), engineering (develop and test), and evaluation (customer review). Risk analysis at each iteration makes it suitable for large, high-risk projects. Waterfall is sequential. Agile is iterative with shorter cycles. The Spiral model's explicit risk focus makes it relevant to security-sensitive development.

</details>

---

**Q25.** A developer uses an ORM (Object-Relational Mapping) framework to interact with the database. Why does this STILL not completely eliminate SQL injection risk?

A) ORM frameworks are not compatible with modern databases
B) ORMs may allow raw queries or string concatenation in custom queries, reintroducing injection risk
C) ORM-generated queries are too slow for production use
D) ORMs do not support parameterized queries

<details><summary>Answer</summary>

**B) ORMs may allow raw queries or string concatenation in custom queries, reintroducing injection risk**

ORMs prevent SQL injection when used correctly with their standard query interfaces. However, most ORMs also allow raw SQL queries for complex scenarios — if developers concatenate user input into these raw queries, SQL injection risk returns. Additionally, ORM misconfigurations can expose injection points. Developers must understand the underlying SQL generated and avoid unsafe raw query construction even when using ORMs.

</details>

---
