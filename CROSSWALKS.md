# ATF Framework Crosswalks

**Version**: 0.9.0
**Last Updated**: April 2026

This document maps ATF's five core elements to other governance and security frameworks. These crosswalks enable organizations to understand how ATF implementation supports compliance with existing standards and integrates with complementary frameworks.

Crosswalk mappings are illustrative. Applicability depends on system classification, organizational role, and regulatory context.

---

## CSA AI Controls Matrix (AICM)

The AI Controls Matrix is CSA's vendor-agnostic controls framework for AI systems, containing 243 control objectives across 18 security domains. ATF operationalizes the agent-specific subset of AICM's controls, adding a maturity model for progressive autonomy that AICM does not provide.

AICM is the broad AI controls umbrella. ATF is the agent-specific operating model underneath it.

| AICM Domain | ATF Element | Alignment |
|-------------|-------------|-----------|
| Identity & Access Management (IAM) | Identity | Agent credentials, mutual authentication, non-human identity lifecycle |
| Data Security & Privacy Lifecycle Management (DSP) | Data Governance | Input validation, PII/PHI classification, data lineage, output filtering |
| Log and Monitoring (LOG) | Behavior | Real-time behavioral monitoring, structured decision logging, anomaly detection |
| Infrastructure & Virtualization Security (IVS) | Segmentation | Network isolation, resource boundaries, blast radius containment |
| Security Incident Management (SEF) | Incident Response | Kill switches, circuit breakers, containment, recovery playbooks |
| Model Security (MDS) | Identity + Data Governance | Model provenance, supply chain verification, integrity validation |
| Application & Interface Security (AIS) | Segmentation + Behavior | API governance, action boundaries, rate limiting |
| Governance, Risk & Compliance (GRC) | Operating Model | Governance policies, promotion criteria, review cadence, compliance evidence |
| Supply Chain Management & Transparency (STA) | Identity + Data Governance | Agent provenance, tool verification, delegation chain integrity |
| Audit & Assurance (A&A) | Maturity Model | Governance sign-off gates, assessment scoring, certification readiness |
| Change Control & Configuration Management (CCC) | Behavior + Operating Model | Configuration drift detection, change approval workflows |
| Threat & Vulnerability Management (TVM) | Behavior + Incident Response | Threat detection for agent-specific attack vectors |
| Human Resources Security (HRS) | Operating Model | Agent ownership accountability, role definitions, training requirements |
| Encryption & Key Management (CEK) | Identity + Data Governance | Credential encryption, key rotation, cryptographic standards |
| Business Continuity & Operational Resilience (BCR) | Incident Response | Recovery procedures, graceful degradation, operational continuity |
| Universal Endpoint Management (UEM) | Segmentation | Agent runtime environment controls, endpoint security |

### What ATF Adds Beyond AICM

- Agent-specific maturity model (Intern, Junior, Senior, Principal) with promotion and demotion gates
- Progressive autonomy governance: agents earn trust, they do not receive it by default
- Zero Trust first principles applied to individual agent identity and behavior
- Operational governance mechanics including review cadence, roles, and accountability
- Free scored self-assessment tool at [verifiedagents.ai](https://verifiedagents.ai/assess)

### What AICM Provides Beyond ATF

- 243 granular control objectives covering the full AI system lifecycle
- Role-based implementation and auditing guidelines (Model Provider, Orchestrated Service Provider, Application Provider)
- Foundation for the STAR for AI certification program
- Formal mappings to ISO 42001, ISO 27001, NIST AI RMF 1.0, and BSI AIC4

Both ATF and AICM are published through the Cloud Security Alliance and are freely available.

---

## OWASP Top 10 for Agentic Applications

*Formal crosswalk forthcoming. See [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) for the current mapping.*

OWASP identifies the top risks for agentic applications (ASI-01 through ASI-10). ATF provides governance controls to mitigate each risk. Every OWASP agentic risk maps to one or more ATF core elements.

---

## NIST 800-207 / AI RMF

*Formal crosswalk forthcoming. See [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) for the current mapping.*

ATF operationalizes NIST Zero Trust principles for AI agents. NIST 800-207 defines the architecture. ATF applies it to the specific challenges of autonomous, non-deterministic systems.

---

## ISO/IEC 42001:2023

*Formal crosswalk forthcoming. See [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) for the current mapping.*

ISO/IEC 42001 is the AI management system standard. ATF operationalizes the agent-specific subset of 42001's controls (Annex A.2 through A.10), providing the implementation specification that 42001 governance programs need for autonomous AI systems.

---

## ISO/IEC 27001:2022

*Formal crosswalk forthcoming. See [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) for the current mapping.*

ISO/IEC 27001 is the global standard for information security management systems. ATF extends ISO 27001's security controls to address the unique challenges of autonomous AI agents: non-deterministic behavior, machine-speed decision-making, and dynamic trust relationships.

---

## Related Documents

- [SPECIFICATION.md](SPECIFICATION.md) - Core framework specification
- [CONFORMANCE.md](CONFORMANCE.md) - Conformance tiers and 25 core requirements
- [IMPLEMENTATION_PATTERNS.md](IMPLEMENTATION_PATTERNS.md) - Implementation patterns including compliance alignment section
- [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) - Interactive framework comparison with full mapping tables

---

*The Agentic Trust Framework is an open specification licensed under CC BY 4.0.*
