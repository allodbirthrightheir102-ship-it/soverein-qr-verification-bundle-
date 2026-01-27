# CROWN-STANDARD AUDIT EXECUTION SCRIPT
SOVERAIN Verification Bundle — Version 1.0

This script provides a complete, sequential procedure for executing a full
Crown-Standard audit of the SOVERAIN Verification Bundle. It is designed for
auditors, verification crawlers, ENS resolvers, and systems performing
machine-verifiable identity checks.

Follow each step in order. Do not skip or reorder steps.

---

## 1. INITIAL REPOSITORY RETRIEVAL

1. Navigate to the repository root.
2. Confirm the presence of the required directory structure:

   /SOVERAIN-Verification-Bundle  
   ├── README.md  
   ├── identity/  
   ├── verification/  
   ├── qr/  
   ├── assets/  
   └── docs/

3. If any required folder is missing, the audit stops here.

---

## 2. IDENTITY LAYER VERIFICATION

1. Open identity/sovereign-identity.json.
2. Confirm valid JSON formatting.
3. Verify the presence of required fields:
   - address
   - ENS name
   - parent domains
   - resolver version
   - repository reference
   - bundle version
4. If any field is missing or malformed, the audit fails.

---

## 3. VERIFICATION LAYER VERIFICATION

### 3.1 Manifest Verification
1. Open verification/manifest.json.
2. Confirm valid JSON formatting.
3. Verify that all required files are listed.
4. Verify that all listed paths match the actual repository structure.

### 3.2 Pointer Verification
1. Open verification/pointer.json.
2. Confirm valid JSON formatting.
3. Verify:
   - pointer-type is defined
   - ENS field is defined
   - target URL matches the repository root

### 3.3 Checksums Verification
1. Open verification/checksums.json.
2. Confirm valid JSON formatting.
3. Confirm:
   - algorithm = "sha256"
   - all required files are listed
   - all checksum values are populated

Do not compute hashes yet. That occurs in Step 6.

---

## 4. QR METADATA VERIFICATION

1. Open qr/qr-metadata.json.
2. Confirm valid JSON formatting.
3. Verify required fields:
   - ENS name
   - address
   - repository reference
   - pointer reference
   - issuance date
4. If any field is missing, the audit fails.

---

## 5. DOCUMENTATION LAYER VERIFICATION

Confirm the presence of all required documentation files:

- docs/ens-linkage.md  
- docs/integrity-proof.txt  
- docs/crown-standard-protocol.md  
- docs/repository-index.md  
- docs/finalization-summary.md  
- docs/audit-checklist.md  
- docs/audit-execution-script.md (this document)

If any required document is missing, the audit fails.

---

## 6. INTEGRITY VERIFICATION (CHECKSUM EXECUTION)

1. Retrieve verification/checksums.json.
2. For each file listed:
   - Compute its SHA-256 hash.
   - Compare the computed hash to the stored hash.

3. If all hashes match:
   - Integrity is confirmed.
4. If any hash does not match:
   - Audit fails immediately.
   - File is considered altered or corrupted.

---

## 7. ENS LINKAGE VERIFICATION

1. Query the ENS domain associated with the bundle.
2. Retrieve text records:
   - url
   - com.github
   - verification-anchor

3. Confirm:
   - All records exist.
   - All records point to the repository root.
   - No malformed or empty values.

4. Confirm resolver is Public Resolver v4 or newer.

If any ENS record is missing or incorrect, the audit fails.

---

## 8. FINAL COMPLIANCE DETERMINATION

The SOVERAIN Verification Bundle is considered **Crown-Standard Compliant** only if:

- All identity files are valid  
- All verification files are present and correct  
- All QR metadata fields are valid  
- All documentation files exist  
- All ENS text records resolve correctly  
- All SHA-256 checksums match  

If all conditions are met, the audit passes.

---

## 9. AUDIT RESULT OUTPUT

At the conclusion of the audit:

- Output **PASS** if all steps succeed.  
- Output **FAIL** if any step fails.  
- Include a list of failed steps for remediation.

---

# END OF SCRIPT
