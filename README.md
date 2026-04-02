# Agentic Trust Framework (ATF)

**Zero Trust Governance for Autonomous AI Agents**

[![Specification Version](https://img.shields.io/badge/spec-v0.9.0-blue.svg)](./SPECIFICATION.md)
[![License: CC BY 4.0](https://img.shields.io/badge/spec_license-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![License: Apache 2.0](https://img.shields.io/badge/repo_license-Apache%202.0-blue.svg)](LICENSE)
[![CSA Published](https://img.shields.io/badge/CSA-Published-green.svg)](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents)

## Overview

The Agentic Trust Framework (ATF) is an open governance specification for autonomous AI agents, applying Zero Trust principles across five core security elements. Published through the Cloud Security Alliance and licensed under CC BY 4.0.

ATF answers the question every organization deploying AI agents must face: **How do we maintain control?**

**This is a specification, not a code library.** ATF defines governance principles and requirements. Implementations demonstrate them in practice.

## The Five Core Elements

Every AI agent must be governed across five dimensions:

| # | Element | Question | What It Governs |
|---|---------|----------|-----------------|
| 1 | **Identity** | "Who are you?" | Agent credentials, authentication, ownership |
| 2 | **Behavior** | "What are you doing?" | Monitoring, anomaly detection, intent alignment |
| 3 | **Data Governance** | "What are you eating? What are you serving?" | Input validation, PII protection, output filtering |
| 4 | **Segmentation** | "Where can you go?" | Access boundaries, least privilege, blast radius |
| 5 | **Incident Response** | "What if you go rogue?" | Kill switches, circuit breakers, containment |

## Agent Maturity Model

Agents earn autonomy through demonstrated trustworthiness. They do not receive it by default.

| Level | Name | Autonomy | Human Involvement | AWS Scope |
|-------|------|----------|-------------------|-----------|
| 1 | Intern | Observe + Report | Continuous oversight | Scope 1 |
| 2 | Junior | Recommend + Approve | Human approves all actions | Scope 2 |
| 3 | Senior | Act + Notify | Post-action notification | Scope 3 |
| 4 | Principal | Autonomous | Strategic oversight only | Scope 4 |

Agents can be **demoted** at any time if they fail to maintain standards. A critical incident triggers immediate demotion to Intern.

See [MATURITY_MODEL.md](MATURITY_MODEL.md) for promotion gates, demotion criteria, operating model, and deployment checklists.

## Status

**Specification**: v0.9.0 (Public Review Draft, April 2026)

The specification has been published through the Cloud Security Alliance, independently implemented by multiple organizations, and is approaching v1.0.

## Ecosystem Adoption

ATF has been independently implemented by organizations building against the specification without coordination:

- **Microsoft Agent Governance Toolkit**: MIT-licensed Python middleware implementing all five ATF elements, now in the official `microsoft/` GitHub organization with a formal [CSA-ATF proposal](https://github.com/microsoft/agent-governance-toolkit/blob/main/CSA-ATF-PROPOSAL.md)
- **Berlin AI Labs**: Reference implementation with 12 deployed services across all five core elements ([PR #1](https://github.com/massivescale-ai/agentic-trust-framework/pull/1))

### Community Engagement

- [Issue #4](https://github.com/massivescale-ai/agentic-trust-framework/issues/4): Temporal drift detection for behavioral monitoring
- [Issue #3](https://github.com/massivescale-ai/agentic-trust-framework/issues/3): Agent Passport System for cryptographic identity
- [Issue #2](https://github.com/massivescale-ai/agentic-trust-framework/issues/2): DID/VC-based agent identity (MolTrust)

## Framework Relationships

ATF is complementary, not competing. It is the governance operating model that other frameworks' threat models and risk assessments lead you to.

| Framework | Relationship | One-Liner |
|-----------|-------------|-----------|
| [CSA AICM](https://cloudsecurityalliance.org/artifacts/ai-controls-matrix) | Parent umbrella | AICM defines 243 controls for AI broadly. ATF operationalizes the agent-specific subset. |
| [MAESTRO](https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro) | Complementary | MAESTRO identifies what could go wrong. ATF defines how to maintain control. |
| [OWASP Agentic Top 10](https://owasp.org/www-project-top-10-for-agentic-applications/) | Complementary | OWASP tells you what the threats are. ATF provides the governance to mitigate them. |
| [NIST 800-207](https://csrc.nist.gov/publications/detail/sp/800-207/final) | Foundational | NIST provides the Zero Trust principles. ATF applies them to AI agents. |
| [AWS Scoping Matrix](https://aws.amazon.com/blogs/security/agentic-ai-security-scoping-matrix/) | Directly aligned | ATF maturity levels map 1:1 to AWS Scopes 1-4. |
| [ISO/IEC 42001](https://www.iso.org/standard/81230.html) | Directly aligned | ISO 42001 asks if you have an AI management system. ATF helps you build the agent governance component. |

See [CROSSWALKS.md](CROSSWALKS.md) for detailed framework alignment mappings.

## Specification Documents

| Document | Description |
|----------|-------------|
| [SPECIFICATION.md](SPECIFICATION.md) | Core specification with requirements (RFC 2119) |
| [MATURITY_MODEL.md](MATURITY_MODEL.md) | Four-level maturity model with promotion/demotion criteria |
| [CONFORMANCE.md](CONFORMANCE.md) | Conformance tiers, 25 core requirements, maturity level matrix |
| [IMPLEMENTATION_PATTERNS.md](IMPLEMENTATION_PATTERNS.md) | Technology-agnostic implementation patterns |
| [CROSSWALKS.md](CROSSWALKS.md) | Framework alignment mappings (AICM, OWASP, NIST, ISO) |
| [SECURITY.md](SECURITY.md) | Security principles and threat model |

## Getting Started

1. **Assess your readiness**: Take the free [ATF Self-Assessment](https://verifiedagents.ai/assess) (30 questions, 15 minutes, PDF report)
2. **Read the specification**: Start with [SPECIFICATION.md](SPECIFICATION.md) for requirements, then [MATURITY_MODEL.md](MATURITY_MODEL.md) for the operating model
3. **Understand the patterns**: Review [IMPLEMENTATION_PATTERNS.md](IMPLEMENTATION_PATTERNS.md) for technology-agnostic guidance
4. **Map to your compliance**: See [CROSSWALKS.md](CROSSWALKS.md) for alignment to AICM, ISO 42001, ISO 27001, NIST, and more

## Background

ATF builds on concepts from [Agentic AI + Zero Trust: A Guide for Business Leaders](https://www.amazon.com/dp/B0FL2WJQVQ) (September 2025), featuring a foreword by John Kindervag, creator of Zero Trust.

Published on the [Cloud Security Alliance blog](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents) in February 2026 via a joint Zero Trust Working Group and AI Safety Working Group collaboration.

## Contributing

ATF welcomes specification feedback, implementation experience reports, and crosswalk contributions. See [CONTRIBUTIONS.md](CONTRIBUTIONS.md) for details.

## License

- **Specification**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **Repository**: [Apache License 2.0](LICENSE)

## Links

- **Specification site**: [agentictrustframework.ai](https://agentictrustframework.ai)
- **Assessment tool**: [verifiedagents.ai/assess](https://verifiedagents.ai/assess)
- **CSA blog post**: [cloudsecurityalliance.org](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents)
- **Author**: Josh Woodruff, [MassiveScale.AI](https://massivescale.ai)
- **Book**: [Agentic AI + Zero Trust](https://www.amazon.com/dp/B0FL2WJQVQ) (Kindle) | [Paperback](https://www.amazon.com/dp/B0FQR3BFS3)
