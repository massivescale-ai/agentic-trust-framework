# ATF Conformance Specification

**Version:** 0.9.0
**Status:** Public Review Draft
**License:** CC BY 4.0
**Last Updated:** April 2026

## Purpose

This document defines what it means to conform to the Agentic Trust Framework (ATF). It provides two tiers of recognition:

- **ATF Compatible:** Self-assessed alignment with ATF requirements. No external audit needed.
- **ATF Certified:** Independent third-party validation against all ATF requirements plus additional operational rigor.

This is a living document. Community feedback is welcome via [GitHub Issues](https://github.com/massivescale-ai/agentic-trust-framework/issues) or the [CSA Zero Trust Working Group](https://cloudsecurityalliance.org/research/working-groups/zero-trust).

## Relationship to the ATF Specification

This document builds on the [ATF Specification](SPECIFICATION.md) and the [CSA blog post](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents) that introduced the framework. The 25 core requirements below come directly from those sources. Conformance is assessed against these requirements, not against specific implementation choices.

ATF is deliberately technology-agnostic. Implementations can use any stack, language, or platform as long as the requirements are met.

---

## ATF Compatible (Self-Attestation)

An implementation qualifies as **ATF Compatible** when the organization:

1. Documents how it addresses each of the 25 core requirements below
2. Publishes a conformance statement identifying which requirements are fully met, partially met, or not yet addressed
3. Identifies the target agent maturity level (Intern, Junior, Senior, Principal)
4. Makes the conformance statement available to stakeholders on request

No external audit is required. The organization is responsible for the accuracy of its self-assessment.

### The 25 Core Requirements

#### Element 1: Identity ("Who are you?")

| # | Requirement | Description |
|---|-------------|-------------|
| I-1 | Unique Identifier | Globally unique, immutable identifier for each agent instance |
| I-2 | Credential Binding | Agent identity bound to cryptographic credentials |
| I-3 | Ownership Chain | Clear documentation of ownership and operational responsibility |
| I-4 | Purpose Declaration | Documented intended use and operational scope |
| I-5 | Capability Manifest | Machine-readable list of claimed agent capabilities |

#### Element 2: Behavioral Monitoring ("What are you doing?")

| # | Requirement | Description |
|---|-------------|-------------|
| B-1 | Structured Logging | All agent actions logged in machine-parseable format |
| B-2 | Action Attribution | Every action tied to agent identity and session context |
| B-3 | Behavioral Baseline | Established patterns of normal operation for anomaly detection |
| B-4 | Anomaly Detection | Identification of deviations from expected behavior |
| B-5 | Explainability | Ability to retrieve rationale for agent decisions |

#### Element 3: Data Governance ("What are you eating? What are you serving?")

| # | Requirement | Description |
|---|-------------|-------------|
| D-1 | Schema Validation | Inputs conform to expected structure and types |
| D-2 | Injection Prevention | Detection of prompt injection and adversarial inputs |
| D-3 | PII/PHI Protection | Automated detection and masking of sensitive data |
| D-4 | Output Validation | Outputs conform to expected structure and content policies |
| D-5 | Data Lineage | Tracking of data provenance through the agent pipeline |

#### Element 4: Segmentation ("Where can you go?")

| # | Requirement | Description |
|---|-------------|-------------|
| S-1 | Resource Allowlist | Explicit enumeration of permitted resources |
| S-2 | Action Boundaries | Explicit enumeration of permitted actions |
| S-3 | Rate Limiting | Maximum operations per time period |
| S-4 | Transaction Limits | Maximum impact per individual action |
| S-5 | Blast Radius Containment | Limits on cumulative impact and cascade effects |

#### Element 5: Incident Response ("What if you go rogue?")

| # | Requirement | Description |
|---|-------------|-------------|
| R-1 | Circuit Breaker | Automatic halt on repeated failures |
| R-2 | Kill Switch | Immediate manual termination capability (<1 second) |
| R-3 | Session Revocation | Ability to invalidate all agent sessions |
| R-4 | State Rollback | Ability to undo agent actions where possible |
| R-5 | Graceful Degradation | Fallback to lower autonomy level on issues |

### Conformance Statement Template

Organizations claiming ATF Compatible status should publish a statement in the following format:

```
Organization: [Name]
Implementation: [Product/System Name]
ATF Version: 0.9.0
Target Maturity Level: [Intern | Junior | Senior | Principal]
Assessment Date: [Date]

Element 1 - Identity:       [X/5 requirements met]
Element 2 - Behavior:       [X/5 requirements met]
Element 3 - Data Governance: [X/5 requirements met]
Element 4 - Segmentation:   [X/5 requirements met]
Element 5 - Incident Response: [X/5 requirements met]

Notes: [Any partial implementations, planned work, or scope limitations]
```

For each requirement marked as met, the organization should maintain internal documentation describing how it is implemented.

---

## ATF Certified (Third-Party Audit)

ATF Certified is a higher bar. It requires everything in ATF Compatible, plus independent validation and additional operational controls.

### Prerequisites

- All 25 core requirements must be fully met (not partial)
- ATF Compatible self-assessment completed first
- Minimum 90 days of production operation at the declared maturity level

### Additional Requirements

#### Independent Verification
- Annual third-party security audit covering all five ATF elements
- Source code or configuration review for security-critical paths
- Validation that the conformance statement matches the actual implementation

#### Operational Maturity
- Formal security governance program with defined roles and responsibilities
- Regular training for staff involved in agent operations
- Documented change management process for agent configurations and policies

#### Testing
- Penetration testing covering agent-specific attack vectors (prompt injection, privilege escalation, data exfiltration)
- Automated compliance testing integrated into deployment pipeline
- Periodic simulation of incident response procedures

#### Continuity
- Business continuity plan that addresses agent governance failures
- Defined procedures for agent demotion (reducing autonomy level) when incidents occur
- Crisis communication plan for agent-related incidents

### Certification Process

1. Complete ATF Compatible self-assessment
2. Engage an approved third-party auditor
3. Auditor validates all 25 core requirements plus additional Certified requirements
4. Submit audit report for review
5. Certification valid for 12 months from audit completion

The list of approved auditors and detailed audit procedures will be published as this specification matures. Organizations interested in early certification should contact the ATF maintainers.

---

## Maturity Level Requirements

Not all 25 requirements apply equally at every maturity level. The table below shows the minimum conformance expectation by level:

| Requirement | Intern | Junior | Senior | Principal |
|-------------|--------|--------|--------|-----------|
| I-1 Unique Identifier | MUST | MUST | MUST | MUST |
| I-2 Credential Binding | SHOULD | MUST | MUST | MUST |
| I-3 Ownership Chain | MUST | MUST | MUST | MUST |
| I-4 Purpose Declaration | MUST | MUST | MUST | MUST |
| I-5 Capability Manifest | SHOULD | SHOULD | MUST | MUST |
| B-1 Structured Logging | MUST | MUST | MUST | MUST |
| B-2 Action Attribution | MUST | MUST | MUST | MUST |
| B-3 Behavioral Baseline | SHOULD | MUST | MUST | MUST |
| B-4 Anomaly Detection | SHOULD | SHOULD | MUST | MUST |
| B-5 Explainability | MAY | SHOULD | MUST | MUST |
| D-1 Schema Validation | SHOULD | MUST | MUST | MUST |
| D-2 Injection Prevention | SHOULD | MUST | MUST | MUST |
| D-3 PII/PHI Protection | MUST | MUST | MUST | MUST |
| D-4 Output Validation | MAY | SHOULD | MUST | MUST |
| D-5 Data Lineage | MAY | SHOULD | SHOULD | MUST |
| S-1 Resource Allowlist | MUST | MUST | MUST | MUST |
| S-2 Action Boundaries | MUST | MUST | MUST | MUST |
| S-3 Rate Limiting | SHOULD | MUST | MUST | MUST |
| S-4 Transaction Limits | MAY | SHOULD | MUST | MUST |
| S-5 Blast Radius Containment | MAY | SHOULD | MUST | MUST |
| R-1 Circuit Breaker | SHOULD | MUST | MUST | MUST |
| R-2 Kill Switch | MUST | MUST | MUST | MUST |
| R-3 Session Revocation | MAY | SHOULD | MUST | MUST |
| R-4 State Rollback | MAY | MAY | SHOULD | MUST |
| R-5 Graceful Degradation | MAY | SHOULD | MUST | MUST |

MUST, SHOULD, and MAY follow [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt) definitions.

---

## Revision History

| Version | Date | Changes |
|---------|------|---------|
| 0.1-draft | 2026-03-18 | Initial community review release |

---

## Contributing

This specification is maintained at [github.com/massivescale-ai/agentic-trust-framework](https://github.com/massivescale-ai/agentic-trust-framework). File issues or submit pull requests to propose changes.

For questions about ATF conformance, contact josh@massivescale.ai or join the [CSA Zero Trust Working Group](https://cloudsecurityalliance.org/research/working-groups/zero-trust).
