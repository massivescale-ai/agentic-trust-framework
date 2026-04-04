# Changelog

All notable changes to the Agentic Trust Framework specification are documented here.

This project follows [Semantic Versioning](https://semver.org/).

## [0.9.1] - 2026-04-03

### Improved

- **SPECIFICATION.md**: Added cross-references to CONFORMANCE.md requirement IDs (I-1 through R-5) in each core element section, connecting the detailed implementation guidance to the 25 canonical requirements
- **SPECIFICATION.md**: Updated Section 3 (Conformance Requirements) to reference CONFORMANCE.md as the authoritative source for the 25 core requirements and maturity level applicability matrix
- **README.md**: Updated Microsoft Agent Governance Toolkit description to reflect the official open-source launch (April 2, 2026): seven packages, five language SDKs, MIT license

### Removed

- **SPECIFICATION.md**: Removed reference to non-existent "ATF compliance test suite" in Section 3 (conformance is assessed against CONFORMANCE.md requirements)

## [0.9.0] - 2026-04-01

### Status: Public Review Draft

This release reflects eight months of specification evolution, independent ecosystem adoption, and formal publication through the Cloud Security Alliance.

### Added

- **CROSSWALKS.md**: New document providing formal framework alignment mappings
  - CSA AI Controls Matrix (AICM): ATF's five core elements mapped to relevant AICM control domains across all 18 security domains (243 controls)
  - Stub sections for OWASP Top 10 for Agentic Applications, NIST 800-207 / AI RMF, and ISO/IEC 42001 crosswalks (forthcoming)
- **CHANGELOG.md**: This file, documenting the specification's evolution
- **CONFORMANCE.md**: Conformance specification with 25 core requirements (5 per element), two conformance tiers (ATF Compatible self-attestation, ATF Certified third-party audit), maturity level requirements matrix with RFC 2119 keywords, and conformance statement template
- **MATURITY_MODEL.md**: Comprehensive agent maturity model document with four levels (Intern, Junior, Senior, Principal), promotion/demotion criteria, five gates, operating model, review cadence, roles and responsibilities, and deployment checklists
- **IMPLEMENTATION_PATTERNS.md**: Detailed implementation patterns covering all five core elements with maturity indicators, anti-patterns, decision criteria, integration points, compliance alignment mappings, deployment path patterns, and self-assessment questions
- **SECURITY.md**: Security principles, cryptographic standards, threat model, and compliance considerations
- EU AI Act compliance mapping caveat noting the Act does not explicitly address agentic AI systems

### Changed

- Version bumped from 0.1.0-draft to 0.9.0 (Public Review Draft)
- README.md substantially updated to reflect current ecosystem state, adoption, and positioning
- CONTRIBUTIONS.md updated to reflect the current contribution model including specification discussions, implementation feedback, and crosswalk contributions
- SPECIFICATION.md header updated with new version, status, and date
- CONFORMANCE.md version updated to 0.9.0
- References section expanded with current framework links

### Ecosystem Adoption (since 0.1.0)

These milestones occurred between v0.1.0-draft and v0.9.0 and informed the specification's evolution:

- Published on the Cloud Security Alliance blog (February 2, 2026) via a joint Zero Trust Working Group and AI Safety Working Group collaboration
- Microsoft Agent Governance Toolkit independently implemented against ATF (now in the official microsoft/ GitHub organization with a formal CSA-ATF proposal document)
- Berlin AI Labs submitted a reference implementation PR documenting 12 deployed services across all five core elements
- Three community issues filed proposing extensions: temporal drift detection for behavioral monitoring, Agent Passport System for cryptographic identity, and DID/VC-based agent identity
- CSA webinar on ATF drew 150+ registrations and 60+ live attendees
- Presented at RSAC 2026 and multiple IANS Forums
- AWS Agentic AI Security Scoping Matrix alignment confirmed (1:1 mapping between ATF maturity levels and AWS Scopes 1-4)

## [0.1.0-draft] - 2025-08-09

### Status: Initial Draft

- Initial specification release with five core elements: Identity Management, Behavioral Monitoring, Data Governance, Segmentation, Incident Response
- Basic conformance requirements
- Security considerations
- Example implementation checklist
