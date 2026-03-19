**Q1.** Which security model enforces mandatory access control using sensitivity labels and prevents information from flowing to a lower classification level?

A) Biba model
B) Bell-LaPadula model
C) Clark-Wilson model
D) Brewer-Nash model

<details><summary>Answer</summary>

**B) Bell-LaPadula model**

The Bell-LaPadula (BLP) model enforces confidentiality by preventing upward reading and downward writing: "no read up, no write down." A subject cannot read data above their clearance level, and cannot write data to a lower classification. Biba focuses on integrity (no read down, no write up). Clark-Wilson enforces integrity through well-formed transactions. Brewer-Nash (Chinese Wall) prevents conflicts of interest.

</details>

---

**Q2.** A system design requires that stored data remain accurate and unmodified by unauthorized users. Which security model BEST supports this requirement?

A) Bell-LaPadula model
B) Biba model
C) Clark-Wilson model
D) Both B and C

<details><summary>Answer</summary>

**D) Both B and C**

Both Biba and Clark-Wilson address integrity. The Biba model uses integrity levels with "no read down, no write up" rules to prevent contamination from less trusted sources. Clark-Wilson enforces integrity through constrained data items, access triple rules, and well-formed transactions. Both are more appropriate for integrity requirements than Bell-LaPadula, which focuses on confidentiality.

</details>

---

**Q3.** What is the PRIMARY security concern with a trusted computing base (TCB)?

A) It must be large enough to include all security-relevant functions
B) It must be as small as possible to minimize the attack surface
C) It must run on dedicated hardware separate from user processes
D) It must be certified by a government agency before deployment

<details><summary>Answer</summary>

**B) It must be as small as possible to minimize the attack surface**

The TCB is the totality of mechanisms responsible for enforcing security policy. A smaller TCB means fewer lines of code to audit, fewer potential vulnerabilities, and easier formal verification. The principle of minimizing the TCB reduces attack surface. It does not need to be large — smaller is better. Dedicated hardware and government certification are desirable but not the primary concern.

</details>

---

**Q4.** Which design principle states that security mechanisms should not be hidden but should remain secure even if their implementation is publicly known?

A) Defense in depth
B) Fail secure
C) Open design
D) Least common mechanism

<details><summary>Answer</summary>

**C) Open design**

Open design (Saltzer and Schroeder principle) states that security should not depend on secrecy of design — only secrecy of keys and passwords. This contrasts with security through obscurity. Systems following open design can be publicly reviewed, allowing broader scrutiny. This is why public cryptographic algorithms (AES, RSA) are considered stronger than proprietary secret ones.

</details>

---

**Q5.** A system fails in a way that denies access to all users. Which design principle is being demonstrated?

A) Fail open
B) Fail secure (fail closed)
C) Defense in depth
D) Separation of privilege

<details><summary>Answer</summary>

**B) Fail secure (fail closed)**

Fail secure (fail closed) means that when a system fails, it defaults to denying access — the secure state. This is appropriate for high-security systems where unauthorized access is worse than unavailability. Fail open defaults to permitting access during failure, which is appropriate for life-safety systems (e.g., emergency exits) but not security systems. Both approaches are valid in different contexts.

</details>

---

**Q6.** Which attack specifically targets vulnerabilities in the relationship between memory addresses and their contents in a system?

A) Buffer overflow
B) SQL injection
C) Cross-site scripting
D) Race condition

<details><summary>Answer</summary>

**A) Buffer overflow**

Buffer overflow attacks write data beyond the allocated memory buffer, corrupting adjacent memory. This can overwrite return addresses, allowing attackers to redirect execution to malicious code. Modern mitigations include address space layout randomization (ASLR), data execution prevention (DEP), and stack canaries. SQL injection targets databases; XSS targets web browsers; race conditions exploit timing between checks and actions.

</details>

---

**Q7.** An organization deploys a security architecture using multiple independent layers of controls. Which principle does this BEST exemplify?

A) Least privilege
B) Defense in depth
C) Separation of duties
D) Complete mediation

<details><summary>Answer</summary>

**B) Defense in depth**

Defense in depth (layered security) uses multiple independent security controls so that if one layer fails, others remain. No single point of failure can compromise the entire system. This principle recognizes that no single control is perfect. Least privilege limits access rights. Separation of duties divides tasks. Complete mediation checks every access request.

</details>

---

**Q8.** What type of cryptographic key is used in asymmetric encryption to encrypt data that only the key pair owner can decrypt?

A) Private key
B) Symmetric key
C) Public key
D) Session key

<details><summary>Answer</summary>

**C) Public key**

In asymmetric cryptography, data encrypted with a recipient's public key can only be decrypted with the corresponding private key. The public key is shared freely; the private key is kept secret. This enables secure communication without prior key exchange. Symmetric keys are the same for encryption and decryption. Session keys are temporary symmetric keys often established via asymmetric methods.

</details>

---

**Q9.** Which type of cryptographic attack attempts all possible key combinations until the correct one is found?

A) Known plaintext attack
B) Rainbow table attack
C) Brute force attack
D) Chosen ciphertext attack

<details><summary>Answer</summary>

**C) Brute force attack**

A brute force attack systematically tries every possible key or password until the correct one is found. The defense is using sufficiently long keys (making brute force computationally infeasible). Known plaintext attacks use known plaintext-ciphertext pairs. Rainbow table attacks use precomputed hash tables. Chosen ciphertext attacks submit chosen ciphertexts and analyze responses.

</details>

---

**Q10.** Which symmetric encryption algorithm is currently considered the standard for protecting sensitive government data in the United States?

A) DES
B) 3DES
C) AES
D) RC4

<details><summary>Answer</summary>

**C) AES**

AES (Advanced Encryption Standard) replaced DES as the US federal standard (FIPS 197) in 2001. It supports key sizes of 128, 192, and 256 bits. DES (56-bit key) is deprecated due to vulnerability to brute force. 3DES is being phased out. RC4 is a stream cipher with known vulnerabilities. AES is the current standard for protecting sensitive data.

</details>

---

**Q11.** What is the purpose of a digital signature?

A) To encrypt data for confidentiality
B) To verify the authenticity and integrity of a message and provide non-repudiation
C) To establish a shared symmetric key between two parties
D) To prevent replay attacks by adding timestamps

<details><summary>Answer</summary>

**B) To verify the authenticity and integrity of a message and provide non-repudiation**

A digital signature uses the sender's private key to sign a hash of the message. The recipient verifies using the sender's public key. This provides: authenticity (proof of sender), integrity (the message wasn't altered), and non-repudiation (sender cannot deny signing). Digital signatures do not provide confidentiality — they don't encrypt the message content.

</details>

---

**Q12.** What is a certificate authority (CA) responsible for in a PKI?

A) Generating private keys for end users
B) Issuing and revoking digital certificates that bind public keys to identities
C) Encrypting all network traffic using TLS
D) Storing private keys in a centralized key escrow

<details><summary>Answer</summary>

**B) Issuing and revoking digital certificates that bind public keys to identities**

A CA issues digital certificates that cryptographically bind a public key to an identity (person, organization, device). CAs also revoke certificates via CRL (Certificate Revocation List) or OCSP. CAs do not generate private keys for end users (the private key should never leave the owner's control). Key escrow is a separate function for recovery purposes.

</details>

---

**Q13.** Which security architecture concept describes an untrusted network zone between the internal network and the internet?

A) VLAN
B) Bastion host
C) DMZ
D) Proxy server

<details><summary>Answer</summary>

**C) DMZ**

A DMZ (Demilitarized Zone) is a perimeter network segment that sits between the internet (untrusted) and the internal network (trusted). Public-facing servers (web, email, DNS) are placed in the DMZ so that if they are compromised, attackers cannot directly reach internal systems. Firewalls segment the DMZ from both the internet and the internal network.

</details>

---

**Q14.** A developer is designing a database system to protect sensitive fields. They decide to store only a one-way transformation of the data. Which technique are they using?

A) Encryption
B) Hashing
C) Tokenization
D) Steganography

<details><summary>Answer</summary>

**B) Hashing**

Hashing produces a fixed-length, one-way output from input data. It cannot be reversed to obtain the original. It is used for password storage (store hash, not plaintext) and integrity verification. Encryption is reversible. Tokenization replaces data with a non-sensitive token. Steganography hides data within other data. For password storage, hashing with salting (e.g., bcrypt, Argon2) is the correct approach.

</details>

---

**Q15.** Which concept describes the ability of a cryptographic system to protect data even if some of the underlying mechanisms are compromised?

A) Perfect forward secrecy
B) Key stretching
C) Cryptographic agility
D) Zero-knowledge proof

<details><summary>Answer</summary>

**A) Perfect forward secrecy**

Perfect forward secrecy (PFS) ensures that session keys are derived independently so that compromise of a long-term private key does not compromise past session keys. Each session uses a new ephemeral key pair (e.g., Diffie-Hellman ephemeral). Key stretching increases the cost of brute force on passwords. Cryptographic agility is the ability to swap algorithms without major changes. Zero-knowledge proofs prove knowledge without revealing the knowledge itself.

</details>

---

**Q16.** What is the MAIN advantage of a hardware security module (HSM) for key management?

A) It provides higher encryption speeds than software-only solutions
B) It protects cryptographic keys in tamper-resistant hardware and prevents key extraction
C) It enables multi-party computation across distributed environments
D) It eliminates the need for key rotation policies

<details><summary>Answer</summary>

**B) It protects cryptographic keys in tamper-resistant hardware and prevents key extraction**

HSMs are purpose-built hardware devices that generate, store, and use cryptographic keys within a tamper-resistant boundary. Private keys never leave the HSM in usable form. They are used for certificate authorities, payment systems, and other high-assurance scenarios. While HSMs do offer performance benefits, the primary advantage is key protection in tamper-evident/tamper-resistant hardware.

</details>

---

**Q17.** Which evaluation framework assigns security assurance levels (EAL1–EAL7) to IT products?

A) FIPS 140-2
B) Common Criteria (ISO/IEC 15408)
C) NIST RMF
D) DoD Orange Book (TCSEC)

<details><summary>Answer</summary>

**B) Common Criteria (ISO/IEC 15408)**

Common Criteria (CC) is an international standard for evaluating and certifying the security properties of IT products. It assigns Evaluation Assurance Levels (EAL1–EAL7), with higher levels representing more rigorous testing. FIPS 140-2 specifically evaluates cryptographic modules. NIST RMF is a risk management framework. The Orange Book (TCSEC) was the predecessor to Common Criteria.

</details>

---

**Q18.** A system is designed so that no single process has write access to its own executable code at runtime. Which security principle does this support?

A) Complete mediation
B) Separation of privilege
C) Least common mechanism
D) Economy of mechanism

<details><summary>Answer</summary>

**B) Separation of privilege**

Separation of privilege requires that operations require more than one condition to be satisfied. Preventing processes from writing their own executable code separates the execution privilege from the write privilege — a form of separation that prevents self-modifying code attacks. Complete mediation checks every access. Least common mechanism minimizes shared resources. Economy of mechanism favors simplicity.

</details>

---

**Q19.** An attacker intercepts and stores encrypted communications today, planning to decrypt them when quantum computers become powerful enough. What type of attack is this?

A) Replay attack
B) Harvest now, decrypt later attack
C) Man-in-the-middle attack
D) Side-channel attack

<details><summary>Answer</summary>

**B) Harvest now, decrypt later attack**

"Harvest now, decrypt later" (also called a store-now-decrypt-later attack) involves capturing encrypted data today with the intent to decrypt it once quantum computers can break current encryption (e.g., RSA, ECC). This drives the adoption of post-quantum cryptography (PQC) standards like those from NIST. Replay attacks reuse captured legitimate communications. Side-channel attacks exploit physical implementation details.

</details>

---

**Q20.** Which cloud deployment model provides dedicated resources to a single organization and is managed by the organization itself?

A) Public cloud
B) Private cloud
C) Community cloud
D) Hybrid cloud

<details><summary>Answer</summary>

**B) Private cloud**

A private cloud provides cloud infrastructure exclusively to a single organization. It can be on-premises or hosted by a third party but is not shared with other organizations. Public cloud resources are shared among multiple customers. Community cloud is shared among organizations with common interests. Hybrid cloud combines private and public cloud, connected by technology enabling data portability.

</details>

---

**Q21.** What is the purpose of an initialization vector (IV) in block cipher modes of operation?

A) To extend the effective key length
B) To ensure that identical plaintext blocks produce different ciphertext blocks
C) To authenticate the encrypted message
D) To enable parallel encryption of multiple blocks

<details><summary>Answer</summary>

**B) To ensure that identical plaintext blocks produce different ciphertext blocks**

An IV (or nonce) is a random value used with a cipher to ensure that the same plaintext encrypted multiple times produces different ciphertext. Without an IV (as in ECB mode), identical plaintext blocks produce identical ciphertext, leaking information. IVs must be unpredictable and unique per encryption operation. IVs extend randomness, not key length.

</details>

---

**Q22.** A system design uses reference monitors to enforce access control. Which property ensures the reference monitor cannot be bypassed?

A) Verifiability
B) Tamper-proof design
C) Always-invoked (non-bypassable)
D) Small size

<details><summary>Answer</summary>

**C) Always-invoked (non-bypassable)**

A reference monitor must have three properties: always-invoked (cannot be bypassed — every access goes through it), tamper-proof (cannot be modified by untrusted processes), and verifiable (small enough to be formally analyzed). The non-bypassable property is what ensures the reference monitor actually controls access. Without it, the other properties are meaningless since attackers could simply avoid the monitor.

</details>

---

**Q23.** Which protocol provides a cryptographic framework for establishing secure communication channels, including key exchange, authentication, and encryption negotiation?

A) IPsec
B) TLS
C) SSH
D) All of the above

<details><summary>Answer</summary>

**D) All of the above**

IPsec, TLS, and SSH all provide secure channel establishment through key exchange, authentication, and encryption negotiation. IPsec operates at the network layer (Layer 3). TLS operates at the transport layer (Layer 4/5). SSH provides secure remote access. All three follow similar phases: negotiation of algorithms, authentication, key establishment, and encrypted communication.

</details>

---

**Q24.** What is the security implication of using ECB (Electronic Codebook) mode for block cipher encryption?

A) It requires a unique IV for each encryption operation
B) Identical plaintext blocks produce identical ciphertext blocks, leaking patterns
C) It is vulnerable to padding oracle attacks
D) It only supports 64-bit block sizes

<details><summary>Answer</summary>

**B) Identical plaintext blocks produce identical ciphertext blocks, leaking patterns**

ECB mode encrypts each block independently without chaining, so identical plaintext blocks always produce identical ciphertext. This reveals data patterns — the famous "ECB penguin" image demonstrates this visually. CBC (Cipher Block Chaining), CTR (Counter), and GCM modes address this by introducing dependencies between blocks or using a counter/nonce.

</details>

---

**Q25.** A company is evaluating its physical security controls for its data center. Which control is considered a detective control?

A) Biometric door locks
B) Security cameras (CCTV)
C) Mantraps
D) Concrete bollards

<details><summary>Answer</summary>

**B) Security cameras (CCTV)**

CCTV cameras are detective controls — they record and detect incidents for investigation and evidence. Biometric locks and mantraps are preventive controls that deny unauthorized physical access. Concrete bollards are preventive controls that prevent vehicle-based attacks. Detective controls identify that something has happened; preventive controls stop incidents from occurring.

</details>

---
