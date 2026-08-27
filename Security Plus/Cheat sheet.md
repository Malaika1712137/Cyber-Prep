# Security+ Weak Points — Quick Review

## Control Categories × Types
**Categories** (what it does):
- Preventive – stops it before it happens
- Deterrent – discourages the attempt
- Detective – identifies during/after
- Corrective – fixes/restores after
- Compensating – alternative when primary control unavailable

**Types** (how it's enforced):
- Technical – systems/software (firewall, IDS, encryption)
- Administrative – policies/procedures/training
- Physical – tangible barriers (locks, mantraps, fences)
- Managerial – oversight/planning/risk decisions (audits, risk assessments, change management)

Examples: locked door = Preventive+Physical | "No Trespassing" sign = Deterrent | fire suppression = Corrective | security awareness training = Preventive+Administrative | WAF blocking SQLi = Preventive+Technical | risk assessment = Managerial | mantrap = Preventive+Physical

## Web Attack Family
- **SQL injection** – malicious SQL in input field, targets database
- **Stored XSS** – malicious script saved on server, hits every visitor
- **Reflected XSS** – script in the link itself, hits only that one click
- **CSRF** – forges a request using victim's *existing* session, no script injection

## Certificate Revocation
- **CRL** – full downloadable list, checked periodically
- **OCSP** – real-time single query to CA
- **OCSP stapling** – server pre-fetches OCSP response, attaches to handshake (more private)

## Access Control Models
- **MAC** – classification labels (Top Secret, Confidential)
- **RBAC** – job title/role (Nurse, HR Manager)
- **DAC** – owner sets permissions
- **ABAC** – attribute-based

## Personnel Controls
- **Separation of duties** – one process split between 2+ people, same time
- **Job rotation** – people moved between roles over time
- **Mandatory vacation** – forces time away to surface fraud
- **Least privilege** – minimum access needed for the job

## Redundancy vs Failover
- **Redundancy (cold spare)** – idle backup, manual activation
- **Failover/HA** – automatic, instant takeover, zero downtime

## Attack Lifecycle (order)
Initial access → Privilege escalation → Persistence → Pivoting/lateral movement → Beaconing/C2 → Exfiltration

## Password Attacks
- **Brute force** – every combo, one account
- **Dictionary attack** – wordlist, one account
- **Credential stuffing** – real leaked pairs, many sites
- **Password spraying** – one password, many accounts (avoids lockout)

## Risk Response
- **Avoidance** – eliminate the activity
- **Mitigation** – reduce via controls
- **Acceptance** – document and own it
- **Transference** – shift to third party (insurance)

## Agreements
- **SLA** – service level agreement, guaranteed performance/uptime metrics
- **MOU** – memorandum of understanding, informal intent to collaborate, not binding
- **NDA** – non-diclosure agreement, confidentiality
- **SOW** – statement of work, specific project scope/deliverables/timeline
- **BPA** – business partnership agreement, formal partnership terms

## Wireless/Bluetooth Attacks
- **Evil twin** – rogue AP with same SSID as legit network
- **Bluesnarfing** – stealing data via Bluetooth
- **Bluejacking** – sending unsolicited messages via Bluetooth
- **War driving** – mapping vulnerable Wi-Fi networks while mobile

## SIEM vs SOAR
- **SIEM** – aggregates/correlates logs, detects & alerts
- **SOAR** – automates the response (auto-isolate, auto-block)

## Authentication Protocols
- **Kerberos** – tickets/KDC, internal Windows AD authentication, timestamp-protected against replay
- **RADIUS/TACACS+** – centralized AAA for network devices (VPN, switches, Wi-Fi APs)
- **LDAP** – directory query/lookup protocol (not itself AAA)
- **SAML** – XML-based federated SSO between identity provider and service provider (org-to-org)
- **FIDO2/WebAuthn** – passwordless, hardware security key-based auth
- **SSO** – one login across systems within the SAME organization
- **Federation** – trust extended ACROSS different organizations

## Devices — know WHAT each does
| Device | Function |
|---|---|
| Packet-filtering firewall | Filters by IP/port only (Layer 3/4) |
| NGFW | App-aware filtering, deep inspection (Layer 7) |
| UTM | ALL-in-one box: firewall+IPS+VPN+AV+content filter |
| IDS | Detects & alerts only, NOT inline |
| IPS | Detects & BLOCKS, sits inline |
| Forward proxy | Represents/protects internal CLIENTS going out |
| Reverse proxy | Represents/protects internal SERVERS, faces external users |
| NAT | Translates private IP → public IP |
| VPN concentrator | Terminates many remote VPN tunnel connections |
| Load balancer | Distributes traffic (round robin / least connection / sticky sessions) |

## Network Segmentation
- **VLAN** – logical separation on SAME physical switch (802.1Q tagging)
- **Subnetting** – dividing IP address space into smaller ranges
- **DMZ / screened subnet** – buffer zone for public-facing servers between internet & internal network
- **Air gap** – ZERO connection, fully physically isolated
- **NAC** – checks device compliance BEFORE granting network access

## VPN — two separate questions, don't confuse them
1. **WHO connects?** Site-to-site (network↔network, always-on) vs Client-to-site (one user↔network)
2. **HOW MUCH traffic routes through it?** Full tunnel (ALL traffic) vs Split tunnel (only internal-bound traffic)

## Modern Architecture
- **SASE** – umbrella: cloud-delivered networking + security (includes ZTNA, CASB, SD-WAN, FW)
- **ZTNA** – app-specific access based on identity (VPN replacement, least privilege)
- **CASB** – monitors/controls CLOUD service usage (Shadow IT, DLP in cloud)
- **SD-WAN** – optimizes WAN connections (not security-specific)

## WEB SECURITY

- **SQL injection** – malicious SQL in input, targets database
- **Stored XSS** – script saved on server, hits every visitor
- **Reflected XSS** – script in the link itself, hits only that click
- **CSRF** – forges request using victim's EXISTING session, no script injected
- **Open redirect** – trusted domain blindly redirects to attacker's external URL (used in phishing)
- **XXE** – malicious XML input exploits how parser handles external entities
- **Directory traversal** – `../../` manipulation to access files outside intended folder

### Security Headers
| Header | Protects against |
|---|---|
| X-Frame-Options | Clickjacking (iframe embedding) |
| Content-Security-Policy | XSS (restricts allowed script sources) |
| HSTS (Strict-Transport-Security) | Downgrade/SSL-stripping (forces HTTPS) |
| X-Content-Type-Options | MIME-type sniffing |
| Cookie: Secure flag | Cookie sent ONLY over HTTPS |
| Cookie: HttpOnly flag | Blocks JS access to cookie (XSS theft) |

## WIRELESS SECURITY

- **WPA3** – uses **SAE** (replaces vulnerable WPA2 4-way handshake), resists offline dictionary attacks
- **WPA2/WPA3-Personal** – shared PSK, same password for all users
- **WPA2/WPA3-Enterprise** – individual credentials, RADIUS + 802.1X backend

## IOT SECURITY
- IoT devices often ship with **default credentials never changed** — #1 real-world risk
- Typically **lack regular patching/updates** — vendor support often short-lived
- Mitigation: **network segmentation** (separate VLAN for IoT), disable unused services, change defaults, firmware updates where possible
- IoT often has **limited compute power** — can't run traditional AV/heavy security agents

## Symmetric vs Asymmetric
- **Symmetric** – SAME key both ways (AES, DES, 3DES) — fast, key distribution is the challenge
- **Asymmetric** – key PAIR, public + private (RSA, ECC) — slower, solves distribution problem

## The Encrypt vs Sign Key Rule (memorize this pair)
- **Encrypt for CONFIDENTIALITY** → use **recipient's PUBLIC key** (only their private key opens it)
- **Sign for AUTHENTICITY/non-repudiation** → use **YOUR OWN private key** (anyone verifies with your public key)

## Key Concepts
- **Perfect Forward Secrecy (PFS)** – unique session key each time; stealing today's key doesn't expose past sessions
- **Key stretching** – deliberately SLOW hashing (bcrypt/PBKDF2/Argon2) to resist brute force — for PASSWORDS
- **Salting** – random data added before hashing, defeats rainbow tables
- **Key escrow** – trusted third party holds a backup copy of keys for recovery
- **Tokenization** – random surrogate value, no math relationship, mapped in secure vault
- **Homomorphic encryption** – compute ON encrypted data, never decrypt at all
- **Confidential computing** – decrypts briefly inside a protected hardware enclave (TEE)

### Hashing
- MD5 = weak/deprecated (collisions)
- SHA-1 = deprecated
- SHA-256 / SHA-3 = secure, current standard
- bcrypt/PBKDF2/Argon2 = specifically for PASSWORDS (slow on purpose)

### Hardware
- **TPM** – trusted platform module, soldered to motherboard, tied to ONE device
- **HSM** – hardware security module, removable/network-attached, enterprise-scale key management (e.g., for a CA)