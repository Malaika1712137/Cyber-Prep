# CIA Triad
1. Confidentiality > To prevent unauthorized acces to information.
2. Integrity > Messages can't be modified once sent.
3. Availablity > Systems and networks must be available and up when needed but only to authorized people.
- Redundancy- services that will alwasu be available.
- Fault Tolerance- system continue to run even adter a failure occurs
- Patching- stability

# Non-Reupdation
"Can't deny what have said aka sugnature"

# Authentication, Authorization, and Accounting Framework
1. Authentication: Prove that you are what you are (via passwords for example).
2. Authorization: What access you should have based on role.
3. Accounting: Keeping track, login time/log-out, data sent/received.

# Symmetric VS Asymmetric
1. Symmetric key encryption that is a single shared, you can encrypt and decrypt using the same key.
2. Asymmetric key encryption has 2 different keys, one to encrypt the message and other to decrypt. Public key to decrypt, and private key to encrypt.

# Hashing
Hashing is like a fingerprint, represents the data as short string of text.
- if data changes, the hash will also change but the file size will remain the same.

# PKI model (Public Key Infrastructure)
It is a foundational framekwork that allowes secure data encryption, communication, and digital authentication. It relies on three thing:
1. Public and Private Key Pairs > Asymmetric encryption for more secure systems.
2. Certificate Authority (CA) > ENtity that signs and issues digital certification aka digital passport issuer.
3. Digital Certifications > Documents that represents an identity, example a website domain

# Zero Trust and Defense in Depth
1. Zero Trust: NEVER TRUST, ALWAYS VERIFY
2. Defense in Depth: Multiple layers to protect the system.

## DOMAIN 1 Practice Quiz notes

# Control Types
* Controls - Tactics or strategies that proactively minimize risk in different ways
* Control plane - how data is managed, routed, and processed
* Technical security control - Hardware/software related controls
* Managerial security controls - risk management, government related strategies
* Operational security controls - implemented and excuted by people
* Phsical security controls - buildings security, physical locks
* Preventive control type - stop a threat agent from being successful
* Deterrent control type - discourage a threat agent from acting
* Detective control type - identify and report threat
* Corrective control type - Minimize the impact of a threat agent or modify 
* Compensating control type - alternative control when a primary control is impractical, too expensive
* Directive control type - actions taken to  cause an event to occur

# Fundamentals
* Three fundamental security - CIA (Confidentiality, Integrity, and Avalibility)
* Non-repudiation - making sure the validity and origin of data
* Framework of authentication (verify user), authorize (approve access), and accounting - AAA (Authentication, Authorization, Accounting)
* Zero Trust - requires all user to follow AAA before granted access
* Data plane - plane on a netowrking device(router/switch) that carries user traffic
* Access control versitbule - entry system with two gateways, only one of which is open at any one time
* Deception and disruption technology - Honeypot, honeynet, honeyfile, honeytoken