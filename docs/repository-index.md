# CROWN-STANDARD REPOSITORY INDEX
SOVERAIN Verification Bundle — Version 1.0

This index provides a complete, structured overview of all files and directories
contained in the SOVERAIN Verification Bundle. It defines the purpose, function,
and expected location of each component for verification crawlers, ENS resolvers,
QR systems, and auditors.

---

## 1. Root Level

### README.md
Primary public declaration of the verification bundle.
Contains:
- sovereign address
- ENS identity hierarchy
- repository structure
- purpose statement

---

## 2. identity/

### identity/sovereign-identity.json
Defines the sovereign identity for verification systems.
Contains:
- address
- ENS name
- parent domains
- resolver version
- repository reference
- bundle version

---

## 3. verification/

### verification/manifest.json
Declares the bundle contents and their canonical locations.
Used by verification crawlers to understand the structure.

### verification/checksums.json
Holds SHA-256 integrity hashes for core identity files.
Used to confirm authenticity and detect tampering.

### verification/pointer.json
Defines the ENS → GitHub pointer.
Used by QR systems and ENS text-record resolvers.

---

## 4. qr/

### qr/qr-metadata.json
Metadata describing the QR identity.
Contains:
- ENS name
- address
- repository reference
- pointer reference
- issuance date

---

## 5. docs/

### docs/ens-linkage.md
Explains ENS → GitHub linkage and resolver behavior.

### docs/integrity-proof.txt
Describes the integrity verification process and covered files.

### docs/crown-standard-protocol.md
Defines the Crown-Standard Protocol for structure, placement, and verification.

### docs/repository-index.md
(This document.)
Provides a complete map of all files and their purposes.

---

## 6. assets/

### assets/
Optional folder for visual assets such as:
- crest
- seal
- banner

These files are not required for verification but may support presentation.

---

## 7. Summary of Verification Flow

1. ENS text records point to the repository root.
2. Verification crawlers load verification/manifest.json.
3. Crawlers load verification/checksums.json.
4. Crawlers compute SHA-256 hashes for all listed files.
5. If all hashes match, the bundle is verified.
6. QR systems use qr/qr-metadata.json to resolve identity.

---
