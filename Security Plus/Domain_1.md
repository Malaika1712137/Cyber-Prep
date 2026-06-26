# Core security concepts
* Confidentiality - To prevent unauthorized acces to information
* Integrity - Ensures data is not changed without permission
* Availablity - Systems and networks must be available and up when needed but only to authorized people.
* Non-repudation - Proof that someone performed an action so they can't deny it later
* Redundancy- Services that will always be available, act as backups
* Fault Tolerance - System continue to run even adter a failure occurs
* Patching - Applying updates to fix vulnerabilites


# AAA Framework
* Authentication - Prove that you are what you are (via passwords for example).
* Authorization - What access you should have based on role.
* Accounting - Keeping track of the user, login time/log-out, data sent/received.

# Encryption and Hashing
* Symmetric key encryption that is a single shared, you can encrypt and decrypt using the same key.
* Asymmetric key encryption has 2 different keys, one to encrypt the message and other to decrypt. Public key to decrypt, and private key to encrypt.
* Hashing - A fingerprint, represents the data as short string of text.
* If data changes, the hash will also change but the file size will remain the same.

# PKI model (Public Key Infrastructure)
* A system for managing digital certificate and public key encryption
* Certificate Authority (CA) - Issues and signs digital certificates
* Digital Certifications - Documents that represents an identity, example a website domain
* Digital Signature - Prove authenticity, integrity, and non-repudation

# Zero Trust and Defense in Depth
* Zero Trust - NEVER TRUST, ALWAYS VERIFY
* Defense in Depth - Multiple layers to protect the system.

# Control Types by purpose
* Preventive - Stop a threat agent from being successful
* Deterrent - Discourage a threat agent from trying
* Detective - Identify and report threat
* Corrective - Minimize the impact of a threat agent or modify 
* Compensating - Alternative control when a primary control is impractical, too expensive
* Directive - Tells people what they must do

# Control types by category
* Technical - Hardware/software related controls
* Managerial - Risk management, government related strategies
* Operational - Implemented and excuted by people
* Phsical- Buildings security, physical locks

# Networking terms
* Data plane - Carries the actual user traffic on network device
* Control plane - Decides hwo traffic should be routed and processed
* Mantrap - Security entrance with two doors, used to control access one person at a time

# Deception technologies
* Honeypot - System designed to attract attacker, like a sunflower that attracts bees
* Honeynet - Multiple honeypots
* Honeyfile - Fake file planted
* Honeytoken - Fake data used to detect misuse

# Mini memory check
* CIA = Confidentiallity, Integrity, Availability
* AAA = Authentication, Autherization, Accounting
* PKI = Public Key Infrastructure, certificates, CA
* Preventive/Detective/Corrective controls = stop/find/fix
* Technical/Managerial/Operation/Phycial controls = tool/policy/people/place

