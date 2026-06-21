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
