**Q1.** Which OSI layer is responsible for end-to-end communication, flow control, and error recovery?

A) Network layer (Layer 3)
B) Transport layer (Layer 4)
C) Session layer (Layer 5)
D) Data link layer (Layer 2)

<details><summary>Answer</summary>

**B) Transport layer (Layer 4)**

The Transport layer (Layer 4) is responsible for end-to-end communication, segmentation, flow control, and error recovery. TCP operates at Layer 4 providing reliable, connection-oriented communication. UDP also operates at Layer 4 but without reliability guarantees. The Network layer handles routing. The Session layer manages dialogue. The Data Link layer handles framing within a network segment.

</details>

---

**Q2.** A network administrator needs to prevent traffic from a specific subnet from reaching the internet while allowing all other traffic. Which network device is BEST suited for this task?

A) Switch
B) Hub
C) Router with access control lists
D) Load balancer

<details><summary>Answer</summary>

**C) Router with access control lists**

Routers with ACLs can filter traffic based on source/destination IP, port, and protocol — exactly what's needed to block a specific subnet from reaching the internet. Switches operate at Layer 2 and don't make routing decisions. Hubs are Layer 1 devices with no filtering capability. Load balancers distribute traffic but don't provide subnet-level blocking.

</details>

---

**Q3.** What is the PRIMARY security advantage of using IPv6 over IPv4?

A) IPv6 addresses are longer and harder to remember
B) IPv6 includes built-in support for IPsec
C) IPv6 eliminates the need for NAT
D) IPv6 is immune to denial-of-service attacks

<details><summary>Answer</summary>

**B) IPv6 includes built-in support for IPsec**

IPv6 was designed with IPsec (IP Security) as a mandatory component, providing authentication and encryption at the network layer. In IPv4, IPsec is optional. While IPv6 also eliminates NAT (answer C is partially correct), the security advantage is the built-in IPsec support. IPv6 is not immune to DoS attacks; in fact, the transition period creates new attack surfaces.

</details>

---

**Q4.** A security team captures network packets and discovers that all DNS queries from client machines are being redirected to a rogue DNS server. Which attack is MOST likely occurring?

A) ARP poisoning
B) DNS poisoning (DNS cache poisoning)
C) BGP hijacking
D) MAC flooding

<details><summary>Answer</summary>

**B) DNS poisoning (DNS cache poisoning)**

DNS cache poisoning (DNS spoofing) involves injecting false DNS records into a resolver's cache, redirecting users to malicious IP addresses when they look up legitimate domain names. ARP poisoning redirects Layer 2 traffic by corrupting ARP caches. BGP hijacking reroutes internet traffic at the routing protocol level. MAC flooding overwhelms switch MAC tables, causing traffic to flood all ports.

</details>

---

**Q5.** Which wireless security protocol is currently considered the MOST secure for enterprise Wi-Fi networks?

A) WEP
B) WPA
C) WPA2 with TKIP
D) WPA3 with SAE

<details><summary>Answer</summary>

**D) WPA3 with SAE**

WPA3 uses Simultaneous Authentication of Equals (SAE), replacing the PSK handshake vulnerable to offline dictionary attacks. WPA3 provides forward secrecy and stronger protection even with weak passwords. WEP is completely broken. WPA and WPA2 with TKIP are vulnerable to various attacks. WPA2 with AES/CCMP is acceptable but WPA3 is the current best practice for enterprise environments.

</details>

---

**Q6.** An organization implements network segmentation to isolate its payment card processing systems from the rest of the corporate network. What security benefit does this PRIMARILY provide?

A) Improved network performance through reduced broadcast domains
B) Reduced PCI DSS scope and prevention of lateral movement
C) Elimination of the need for firewalls within the network
D) Protection against external DDoS attacks

<details><summary>Answer</summary>

**B) Reduced PCI DSS scope and prevention of lateral movement**

Network segmentation isolating cardholder data environments (CDE) reduces PCI DSS scope — fewer systems in scope means fewer compliance requirements. Security-wise, it prevents lateral movement: if an attacker compromises a non-payment system, they cannot easily reach payment systems. Network performance improvement is a secondary benefit, not the primary security goal.

</details>

---

**Q7.** What is the function of Network Address Translation (NAT)?

A) To encrypt traffic between internal hosts and the internet
B) To translate private IP addresses to public IP addresses, hiding the internal network structure
C) To assign IP addresses dynamically to network hosts
D) To filter malicious traffic before it reaches internal hosts

<details><summary>Answer</summary>

**B) To translate private IP addresses to public IP addresses, hiding the internal network structure**

NAT translates private (RFC 1918) IP addresses to a public IP address when traffic leaves the network. This conserves public IP address space and provides a degree of obscurity (internal IP addresses are not visible on the internet). NAT does not encrypt traffic (that's IPsec/TLS), assign IPs (that's DHCP), or filter malicious traffic (that's firewalls/IPS).

</details>

---

**Q8.** A CISSP is designing a VPN solution for remote workers. Which protocol provides the STRONGEST security at the network layer?

A) PPTP
B) L2TP without IPsec
C) SSL/TLS VPN
D) IPsec in tunnel mode

<details><summary>Answer</summary>

**D) IPsec in tunnel mode**

IPsec in tunnel mode encrypts the entire original IP packet (including headers) and encapsulates it in a new IP packet, providing strong confidentiality, integrity, and authentication at the network layer. PPTP has known weaknesses in its MS-CHAPv2 authentication. L2TP without IPsec provides no encryption. SSL/TLS VPNs operate at Layer 4–7 and are excellent for remote access but operate at a higher layer than IPsec.

</details>

---

**Q9.** Which firewall type maintains a state table to track connection status and only allows packets that are part of established connections?

A) Packet filtering firewall
B) Stateful inspection firewall
C) Application layer (proxy) firewall
D) Next-generation firewall

<details><summary>Answer</summary>

**B) Stateful inspection firewall**

Stateful inspection firewalls maintain a state table tracking active connections and their state (established, related, new). They only allow packets that match a legitimate connection state, blocking unsolicited inbound packets. Packet filtering firewalls evaluate each packet independently (stateless). Proxy firewalls operate at the application layer. Next-generation firewalls include stateful inspection plus additional capabilities.

</details>

---

**Q10.** What does the term "converged network" refer to in modern enterprise environments?

A) A network where all devices use the same IP addressing scheme
B) A single network infrastructure carrying voice, video, and data traffic
C) A network that combines wired and wireless connections
D) A fully redundant network with no single points of failure

<details><summary>Answer</summary>

**B) A single network infrastructure carrying voice, video, and data traffic**

Converged networks carry multiple traffic types (voice, video, data) over a single IP infrastructure. This introduces security challenges: voice and video traffic has real-time requirements, making quality-of-service (QoS) critical; VoIP systems introduce new attack surfaces (toll fraud, eavesdropping); and network failures affect more services simultaneously.

</details>

---

**Q11.** An attacker sends a large number of SYN packets to a server without completing the three-way handshake, consuming server resources. Which attack is this?

A) Smurf attack
B) SYN flood attack
C) Fraggle attack
D) Ping of Death

<details><summary>Answer</summary>

**B) SYN flood attack**

A SYN flood sends many TCP SYN packets (connection initiation) without completing the handshake by not sending the final ACK. The server holds open half-open connections waiting for the ACK, exhausting connection table resources and preventing legitimate connections. Mitigations include SYN cookies, rate limiting, and firewall state tracking. Smurf and Fraggle attacks use ICMP/UDP amplification.

</details>

---

**Q12.** Which protocol is used to automatically assign IP addresses to network devices?

A) DNS
B) ARP
C) DHCP
D) ICMP

<details><summary>Answer</summary>

**C) DHCP**

DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses, subnet masks, default gateways, and DNS server addresses to network clients. DNS resolves domain names to IP addresses. ARP maps IP addresses to MAC addresses on a local network. ICMP is used for error messages and network diagnostics (ping). DHCP starvation and rogue DHCP server attacks are common security concerns.

</details>

---

**Q13.** A network uses 802.1X for port-based access control. What is the role of the RADIUS server in this architecture?

A) It assigns IP addresses to authenticated clients
B) It acts as the authentication server, validating client credentials
C) It encrypts traffic between the client and the access point
D) It monitors network traffic for anomalies

<details><summary>Answer</summary>

**B) It acts as the authentication server, validating client credentials**

In 802.1X, the RADIUS server is the authentication server (AS) that validates client credentials (using EAP methods like EAP-TLS or PEAP). The three components are: supplicant (client), authenticator (switch/AP), and authentication server (RADIUS). IP assignment is handled by DHCP. Encryption is handled by WPA2/WPA3. Traffic monitoring is performed by SIEM/IDS.

</details>

---

**Q14.** Which type of IDS/IPS detection method identifies attacks by comparing traffic to known attack signatures?

A) Anomaly-based detection
B) Behavior-based detection
C) Signature-based detection
D) Heuristic detection

<details><summary>Answer</summary>

**C) Signature-based detection**

Signature-based detection compares traffic or activity against a database of known attack patterns (signatures). It is effective against known threats but cannot detect new, unknown attacks (zero-days). Anomaly-based detection establishes a baseline and alerts on deviations — it can detect unknown attacks but has higher false positive rates. Heuristic and behavior-based detection analyze code or behavior patterns.

</details>

---

**Q15.** What is the security risk of using VLAN hopping in a network?

A) Attacker can change the VLAN configuration remotely
B) Attacker can gain access to traffic on a different VLAN, bypassing segmentation
C) Attacker can flood the VLAN with broadcast traffic
D) Attacker can disable trunking between switches

<details><summary>Answer</summary>

**B) Attacker can gain access to traffic on a different VLAN, bypassing segmentation**

VLAN hopping allows an attacker to send traffic to a VLAN they are not authorized to access, bypassing the segmentation that VLANs provide. Two techniques: switch spoofing (attacker's port negotiates as a trunk) and double tagging (attacker tags frames with two VLAN tags). Mitigations: disable dynamic trunking protocol (DTP), use dedicated native VLANs, and disable unused ports.

</details>

---

**Q16.** Which protocol provides connectionless, unreliable data transmission at Layer 4?

A) TCP
B) UDP
C) ICMP
D) SCTP

<details><summary>Answer</summary>

**B) UDP**

UDP (User Datagram Protocol) provides connectionless, unreliable (no guaranteed delivery) communication at Layer 4. It has less overhead than TCP, making it suitable for real-time applications like VoIP, video streaming, and DNS queries where speed matters more than reliability. TCP provides reliable, connection-oriented communication. ICMP is Layer 3. SCTP provides reliable, message-oriented communication.

</details>

---

**Q17.** A security analyst notices that an internal host is sending traffic to an external IP on port 443 at regular 60-second intervals, regardless of user activity. What is this MOST likely indicating?

A) A misconfigured web browser
B) Command-and-control (C2) beacon traffic from malware
C) Legitimate cloud application synchronization
D) Failed SSL certificate validation attempts

<details><summary>Answer</summary>

**B) Command-and-control (C2) beacon traffic from malware**

Regular, periodic outbound connections — especially beaconing at predictable intervals to the same external IP — is a classic indicator of malware communicating with a command-and-control server. The use of port 443 helps blend in with legitimate HTTPS traffic. Security analysts look for this pattern (known as "beaconing") using network monitoring and DNS analytics tools.

</details>

---

**Q18.** Which network security control monitors traffic for suspicious activity and can automatically block detected threats?

A) IDS (Intrusion Detection System)
B) IPS (Intrusion Prevention System)
C) SIEM (Security Information and Event Management)
D) WAF (Web Application Firewall)

<details><summary>Answer</summary>

**B) IPS (Intrusion Prevention System)**

An IPS is inline with network traffic and can both detect and automatically block suspicious activity in real time. An IDS only detects and alerts — it cannot block. A SIEM aggregates and correlates logs from multiple sources but doesn't directly block traffic. A WAF specifically protects web applications. The key differentiator: IDS = detect and alert; IPS = detect and prevent.

</details>

---

**Q19.** What is the purpose of a proxy server in a corporate network?

A) To route traffic between different network segments
B) To act as an intermediary, controlling outbound internet access and providing caching
C) To translate public IP addresses to private IP addresses
D) To encrypt all internal network communications

<details><summary>Answer</summary>

**B) To act as an intermediary, controlling outbound internet access and providing caching**

A forward proxy acts as an intermediary for internal clients accessing the internet. It provides URL filtering, content inspection, caching, and anonymization of internal IP addresses from external servers. Routing is performed by routers. NAT translates addresses. Encryption is performed by VPN and TLS.

</details>

---

**Q20.** Which attack exploits trust relationships between networked systems by forging the source IP address in network packets?

A) Session hijacking
B) IP spoofing
C) ARP poisoning
D) MAC cloning

<details><summary>Answer</summary>

**B) IP spoofing**

IP spoofing involves forging the source IP address in packet headers to impersonate a trusted host or bypass IP-based access controls. It is used in DDoS reflection/amplification attacks and session hijacking. Defenses include ingress filtering (RFC 2827) and BCP38. ARP poisoning forges Layer 2 addresses. MAC cloning forges hardware addresses. Session hijacking steals an active session token.

</details>

---

**Q21.** What technology allows multiple logical networks to be created over a single physical network infrastructure?

A) Subnetting
B) VLAN (Virtual Local Area Network)
C) NAT (Network Address Translation)
D) Tunneling

<details><summary>Answer</summary>

**B) VLAN (Virtual Local Area Network)**

VLANs segment a physical network into multiple logical networks at Layer 2. Devices in different VLANs cannot communicate without a router (Layer 3 device). Subnetting divides IP address space at Layer 3. NAT translates addresses. Tunneling encapsulates traffic from one protocol within another. VLANs are the primary Layer 2 segmentation mechanism.

</details>

---

**Q22.** During a network security review, a team identifies that a switch is configured with a management VLAN that is the same as the default VLAN (VLAN 1). What security risk does this create?

A) Performance degradation due to broadcast storms
B) All untagged traffic is on the management VLAN, exposing management interfaces to general traffic
C) VLAN 1 cannot support management protocols like SNMP
D) The switch cannot authenticate management sessions on VLAN 1

<details><summary>Answer</summary>

**B) All untagged traffic is on the management VLAN, exposing management interfaces to general traffic**

By default, all switch ports belong to VLAN 1. Using VLAN 1 as the management VLAN means untagged user traffic shares the management VLAN, exposing management interfaces to all network users. Best practice: use a dedicated, non-default VLAN for management traffic, and configure all unused ports to an isolated "dead" VLAN. This reduces the attack surface for management plane attacks.

</details>

---

**Q23.** Which secure protocol is used to remotely manage network devices through an encrypted command-line interface?

A) Telnet
B) SNMP v1
C) SSH
D) TFTP

<details><summary>Answer</summary>

**C) SSH**

SSH (Secure Shell) provides encrypted remote access to network devices and servers. Telnet transmits credentials and commands in plaintext. SNMPv1 and v2 use community strings in plaintext. TFTP (Trivial FTP) transfers files without authentication or encryption. SSH should replace Telnet for all remote management; SNMPv3 should replace SNMPv1/v2 for network monitoring.

</details>

---

**Q24.** A company deploys a unified threat management (UTM) appliance at its network perimeter. Which statement about UTM devices is MOST accurate?

A) UTM devices are the most secure option for all enterprise networks
B) UTM devices consolidate multiple security functions but introduce a single point of failure
C) UTM devices eliminate the need for endpoint security solutions
D) UTM devices are only appropriate for small networks

<details><summary>Answer</summary>

**B) UTM devices consolidate multiple security functions but introduce a single point of failure**

UTM devices combine multiple security functions (firewall, IPS, VPN, content filtering, antivirus) in a single appliance. This reduces complexity and cost but creates a single point of failure — if the UTM fails or is compromised, all security functions are affected. Defense in depth argues for layered, independent controls. UTMs are common in SMBs; large enterprises often prefer best-of-breed individual components.

</details>

---

**Q25.** Which protocol operates at the application layer and is designed specifically for secure transfer of files?

A) FTP
B) SFTP
C) TFTP
D) SCP

<details><summary>Answer</summary>

**B) SFTP**

SFTP (SSH File Transfer Protocol) is a secure file transfer protocol built on top of SSH, providing encryption and authentication. FTP transmits credentials and data in cleartext. TFTP is unauthenticated and unencrypted. SCP (Secure Copy) also uses SSH for encryption but has been largely superseded by SFTP. Both SFTP and SCP are acceptable secure alternatives to FTP.

</details>

---
