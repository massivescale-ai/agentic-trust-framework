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

The OWASP Top 10 for Agentic Applications identifies the most critical security risks facing autonomous AI agents (ASI-01 through ASI-10). ATF provides the governance controls to mitigate each of these risks. Every OWASP agentic risk maps to one or more ATF core elements, making the two frameworks naturally complementary.

*OWASP provides the risk catalog. ATF provides the governance response.*

| OWASP Risk | ATF Element | Alignment |
|------------|-------------|-----------|
| ASI-01: Agent Identity Spoofing | Identity | Cryptographic agent credentials, mutual authentication |
| ASI-02: Agent Authorization Failures | Identity + Segmentation | RBAC/ABAC enforcement, policy-as-code boundaries |
| ASI-03: Excessive Agent Autonomy | Behavior + Segmentation | Maturity-based autonomy levels, action boundaries |
| ASI-04: Improper Output Handling | Data Governance | Output validation, toxicity filtering, content classification |
| ASI-05: Insecure Agent Memory | Data Governance | Data classification, encryption at rest and in transit |
| ASI-06: Agent-to-Agent Trust Issues | Identity | Trust chains, session verification, delegation integrity |
| ASI-07: Insufficient Agent Logging | Behavior | Comprehensive structured logging, decision audit trails |
| ASI-08: Vulnerable Agent Supply Chain | Identity + Data Governance | Provenance verification, input validation, integrity checks |
| ASI-09: Agent Resource Exhaustion | Segmentation | Rate limiting, resource quotas, blast radius containment |
| ASI-10: Unreliable Agent Operations | Incident Response | Circuit breakers, graceful degradation, recovery playbooks |

### What ATF Adds Beyond OWASP

- Governance framework with progressive autonomy model, not just risk identification
- Maturity levels (Intern through Principal) that tie autonomy to demonstrated trustworthiness
- Continuous behavioral monitoring and anomaly detection beyond point-in-time risk assessment
- Incident response mechanics including kill switches, containment, and demotion triggers
- Operating model with roles, review cadence, and accountability structures

### What OWASP Provides Beyond ATF

- Prioritized risk ranking based on real-world prevalence and impact
- Detailed attack scenarios and exploitation techniques for each risk category
- Developer-focused remediation guidance with concrete implementation examples
- Community-driven threat intelligence updated as the agentic landscape evolves
- Broad industry recognition as a baseline security reference

Together, OWASP and ATF give security teams both the "what can go wrong" and the "how to prevent it."

---

## NIST 800-207 / AI RMF

NIST SP 800-207 defines the Zero Trust Architecture that underpins modern security, while the NIST AI Risk Management Framework (AI RMF) provides functions for governing AI system risk. ATF operationalizes both for autonomous AI agents, applying Zero Trust's "never trust, always verify" to non-deterministic systems that operate at machine speed.

*NIST provides the principles. ATF provides the agent-specific implementation.*

| NIST Principle / AI RMF Function | ATF Element | Alignment |
|----------------------------------|-------------|-----------|
| Never trust, always verify | All Elements | Continuous verification at every level, no implicit trust for agents |
| Least privilege access | Segmentation | Strict allowlists, maturity-based action boundaries |
| Assume breach | Incident Response | Kill switches, circuit breakers, blast radius containment |
| GOVERN function | Operating Model | Roles, review cadence, promotion criteria, governance policies |
| MAP function | Identity + Behavior | Agent characterization, behavioral baselines, capability inventory |
| MEASURE function | Behavior | Anomaly detection, performance metrics, drift monitoring |
| MANAGE function | All Elements | Controls enforcement, incident response, continuous improvement |

### What ATF Adds Beyond NIST

- Agent-specific maturity model that governs progressive autonomy (Intern through Principal)
- Concrete governance mechanics for non-human identities operating autonomously
- Behavioral monitoring tailored to non-deterministic AI agent outputs
- Demotion and containment triggers designed for machine-speed incident response
- Operating model with agent ownership, review cadence, and accountability structures

### What NIST Provides Beyond ATF

- Comprehensive Zero Trust reference architecture applicable to all system types
- Formal AI risk taxonomy with structured assessment methodology (AI RMF)
- Sector-specific guidance and implementation tiers for risk management
- Extensive federal compliance alignment and regulatory recognition
- Mature ecosystem of supporting publications (SP 800-53, CSF, privacy framework)

Organizations already implementing Zero Trust will find ATF a natural extension of their existing architecture into the agentic AI domain.

---

## ISO/IEC 42001:2023

ISO/IEC 42001:2023 is the world's first AI management system standard, with 39 controls across 10 domains covering AI governance, risk management, system lifecycle, and data management. ATF operationalizes the agent-specific subset of these controls, providing the implementation specification that ISO 42001 governance programs need for autonomous AI systems. Microsoft, AWS, Google Cloud, and Anthropic have all achieved ISO 42001 certification, making this crosswalk increasingly important for enterprise adoption.

*ISO 42001 provides the management system. ATF provides the agent-specific operating model within it.*

| ISO 42001 Control | ATF Element | Alignment |
|--------------------|-------------|-----------|
| A.2 AI Policy | Operating Model | Governance policies, promotion criteria, review cadence |
| A.3 Internal Organization | Operating Model | Roles, responsibilities, and reporting for agent governance |
| A.4 Resources for AI Systems | Identity | Agent inventory, credential management, resource documentation |
| A.5 AI System Lifecycle | Maturity Model | Intern to Principal progression, promotion gates, demotion triggers |
| A.6 Data for AI Systems | Data Governance | Input validation, data provenance, PII/PHI protection, output filtering |
| A.7 System Information for Interested Parties | Behavior | Transparency, decision logging, explainability, audit trails |
| A.8 Use of AI Systems | Segmentation + Behavior | Action boundaries, rate limiting, behavioral monitoring |
| A.9 Third-Party and Customer Relationships | Identity + Segmentation | Agent-to-agent trust, supply chain verification, delegation chains |
| A.10 Continual Improvement | All Elements | Maturity progression, incident-driven demotion, continuous verification |

### What ATF Adds Beyond ISO 42001

- Progressive autonomy model with concrete promotion and demotion mechanics
- Zero Trust identity verification applied to every agent interaction
- Real-time behavioral monitoring and anomaly detection for autonomous systems
- Machine-speed incident response with kill switches and circuit breakers
- Scored self-assessment tool for implementation readiness at [verifiedagents.ai](https://verifiedagents.ai/assess)

### What ISO 42001 Provides Beyond ATF

- Comprehensive AI management system covering all AI system types, not just agents
- Formal certification pathway with accredited third-party auditing
- Broad organizational controls including HR, training, and management review
- International recognition and regulatory alignment across jurisdictions
- Structured risk assessment methodology for AI-specific risks

Organizations pursuing ISO 42001 certification will find that ATF implementation generates much of the evidence and documentation the standard requires for autonomous AI systems.

---

## ISO/IEC 27001:2022

ISO/IEC 27001 is the global standard for information security management systems, providing 93 controls across organizational, people, physical, and technological domains. ATF extends ISO 27001's security controls to address the unique challenges of autonomous AI agents, including non-deterministic behavior, machine-speed decision-making, and dynamic trust relationships. Organizations with existing ISO 27001 certification will find ATF builds naturally on their existing ISMS.

*ISO 27001 provides the information security foundation. ATF extends it for autonomous AI agents.*

| ISO 27001 Control Group | ATF Element | Alignment |
|--------------------------|-------------|-----------|
| A.5 Organizational Controls (policies, roles) | Operating Model | Agent governance policies, ownership, review cadence |
| A.5.15-A.5.18 Access Control | Identity + Segmentation | Agent credentials, least privilege, action boundaries |
| A.8.1-A.8.10 Technology Controls (endpoint, logging) | Behavior | Continuous monitoring, structured logging, anomaly detection |
| A.8.11-A.8.12 Network Security | Segmentation | Network isolation, resource allowlists, blast radius containment |
| A.8.15-A.8.16 Logging and Monitoring | Behavior | Real-time behavioral analysis, decision audit trails |
| A.5.24-A.5.28 Incident Management | Incident Response | Circuit breakers, kill switches, containment, recovery playbooks |
| A.5.31-A.5.36 Compliance | Maturity Model | Governance sign-off gates, compliance evidence generation |
| A.8.25-A.8.31 Secure Development | Data Governance | Input validation, output filtering, data lineage |

### What ATF Adds Beyond ISO 27001

- Governance model for non-deterministic, autonomous systems that ISO 27001 was not designed to cover
- Progressive autonomy with maturity levels that tie trust to demonstrated agent behavior
- Machine-speed incident response mechanics including automated kill switches and demotion
- Agent-specific identity management for non-human entities operating independently
- Behavioral baselines and drift detection for systems whose outputs vary by design

### What ISO 27001 Provides Beyond ATF

- Comprehensive information security management system covering all organizational assets
- Mature certification ecosystem with global regulatory recognition
- People, physical, and organizational controls beyond the scope of agent governance
- Structured risk assessment and treatment methodology applicable to all information assets
- Decades of implementation guidance, auditor training, and industry best practices

The key addition ATF makes is addressing non-deterministic agent behavior, progressive autonomy, and machine-speed incident response, none of which ISO 27001 was designed to cover.

---

## Related Documents

- [SPECIFICATION.md](SPECIFICATION.md) - Core framework specification
- [CONFORMANCE.md](CONFORMANCE.md) - Conformance tiers and 25 core requirements
- [IMPLEMENTATION_PATTERNS.md](IMPLEMENTATION_PATTERNS.md) - Implementation patterns including compliance alignment section
- [agentictrustframework.ai/compare](https://agentictrustframework.ai/compare) - Interactive framework comparison with full mapping tables

---

*The Agentic Trust Framework is an open specification licensed under CC BY 4.0.*
