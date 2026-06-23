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
* Viruses requires a host to execute, while worms can replicate itself
* Virus spreads to impact and damage other resources on the system
* Spyware monitors our actions
* Botnet is a collection of zombie computers to collect personal information
* Trojan Horse appears to be legitmate but performs malicious activity 
* Logic bomb perfroms malicious activity at a specific time or after an event is triggered
* Logic bomb is also called an Asynchronous attack
* Rootkit allows adminitrator-level access, hides itself from detection
* Adware is when the browsers shows ads targeted to you based on your recent searches
* Anti-virus software are benefecial against worms and trojan horse
* Retro virus deletes key antivirus program files
* Stealth virus conceals its presence by intercepting system requests and altering service outputs
* Example of an Internal Threat (user accidentally deletes the desings)
* USB devices are the biggest threat to confidentiality
* Whaling is when the target is big, example CEO
* Spear Phishing is when an attacker gathers personal information about the target individual in an organization
* Dumpster diving is gathering information from trash
* Piggy backing is like following someone entering into a secure buiding
* Vishing is like phishing but through audio, via voicemail or call, also known as VoIP (Voice over IP)
* Masquerading is when an attacker convinces a person to grant access to sensitive ifnromation, pretend to be legitmate
* Spim is when an attacker send unwanted text messages to many people with the intent to sell products
* People are the weakest point in organization's infrastructure
* DDos attack uses zombie computers (botnets) ditributed deniel of service, multiple attacks, multiple machines at the same time
* Denial of service is when the attacker overlaods the system so it ddenies any further service
* Smurf attack is type of DDoS, it overwhelms target system by tricking multiple innocent devices.
Xmas tree attack obtains the infromation about open ports of the system
* Nmap is used to show the networks details and devices on 
* Null scan turns off all flags in a TCP header
* Ping flood is when the victim has less bandwidth (max amount of data a netwrok can handle at once) than the attacker
* Teardrop is another type of DDoS where the victim's system rebuild invalid UDP packets, causing system to crash