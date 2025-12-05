# OCPP-SBOM

This repository provides formal SBOM representations (CycloneDX and SPDX) of OCPP standard specification bundles, including all PDFs, appendices, and JSON schema files published by the [Open Charge Alliance](https://openchargealliance.org).
Although OCPP itself is not software, its specification bundle is a **critical dependency** for every CSMS software, charging station firmware, and conformance tool that implements the protocol.
Treating the OCPP specification as a versioned, hashable, machine-describable artifact provides strong benefits for implementors and auditors across the entire EV charging ecosystem.

### A CycloneDX 1.5 SBOM describing:

- the OCPP 2.1 Edition 2 release bundle as the top-level artifact
- every included PDF, ZIP, and JSON schema archive
- IEC 63584 as an alternative standard identifier
- precise file roles (introduction, architecture, certification profiles, test cases, schemas, etc.)
- SHA-256 hashes for verification

### A SPDX 2.3 SBOM with:

- document-level metadata and license declarations (CC-BY-ND-4.0)
- package definition for the full release ZIP
- per-file entries and CONTAINS relationships
- references to the official OCA publication and the IEC standard
- Both SBOMs follow the conventions normally used for software dependencies but applied consistently to a **standardized protocol specification**




## How implementors can use this

- **Build reproducibility**    
Link your CSMS/CP firmware build system to a specific OCPP-SBOM release to guarantee deterministic testing and version locking.

- **Documentation & compliance**    
Include this SBOM in your internal documentation or CRA/NIS2 audit packages to demonstrate dependency clarity.

- **Schema integrity**    
Automatically verify JSON schema inputs against the official hash before generating code, validators, or protocol bindings.

- **Vendor alignment**    
When debugging interoperability issues, simply asking “Which spec bundle SBOM are you on?” eliminates an entire class of subtle mismatches.




## Why an SBOM for a protocol specification?

OCPP is the structural and semantic backbone for nearly all EV charging infrastructures. While it is not executable code, the specification functions as a **normative dependency** that affects:

- **Interoperability**    
Implementors must ensure they reference exactly the same edition and the same JSON schema set. An SBOM gives you a machine-verifiable fingerprint of the spec bundle you built against.

- **Certification & Testing**    
Certification bodies (OCA, laboratories, vendors) can unambiguously confirm which edition and which file revisions were used to validate an implementation.

- **Supply-chain integrity**    
By treating the published OCPP ZIP/PDF/schema files as verifiable artifacts with SHA-256 hashes and structured metadata, organizations can detect:
  - corrupted downloads,
  - modified local copies,
  - unintentional drift between engineering teams, mismatches between vendors during integration testing.

- **Cybersecurity & CRA/NIS2 compliance**    
Regulatory frameworks increasingly require complete dependency transparency.
Even if OCPP is not “software”, it is:
  - a security-relevant input to implementations,
  - a normatively versioned dependency,
  - a source of JSON schemas, which are literally consumed by code generators, validators, test harnesses, and protocol stacks.

- **Long-term reproducibility**    
Implementations must remain traceable even 10–15 years later. A formal SBOM ensures that future engineers can reconstruct the exact edition of the standard that a system was originally built for.





## Get involved

This repository is under ***active development***, and your contributions are warmly welcomed.

If you want to verify, extend, or automate these SBOMs, please open an issue or submit a pull request.
OCPP evolves through collaboration, and the same applies to strengthening its supply-chain transparency.

If you are interested in the broader cybersecurity work around OCPP and the EV charging ecosystem, consider joining the **Open Charge Alliance Cyber Security Task Group**, where implementors, manufacturers, and researchers work together on practical security and compliance improvements.
