# Agentic Trust Framework (ATF)

**An open specification for Zero Trust governance of autonomous AI agents**

[![Specification Version](https://img.shields.io/badge/spec-v0.1.0--draft-yellow.svg)](./SPECIFICATION.md)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![CSA](https://img.shields.io/badge/CSA-Research%20Publication-0072CE.svg)](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents)

## Overview

The Agentic Trust Framework (ATF) is an open specification that defines Zero Trust security standards for AI agents. Created by [MassiveScale.AI](https://massivescale.ai) and [introduced via the Cloud Security Alliance](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents), ATF provides a practical governance model for organizations deploying autonomous AI systems.

**Full specification and resources:** [agentictrustframework.ai](https://agentictrustframework.ai)

## The Five Core Elements

ATF implements five security elements, each addressing a fundamental question about agent governance:

| # | Element | Question | Function |
|---|---------|----------|----------|
| 1 | **Identity Management** | Who are you? | Unforgeable credentials for every agent |
| 2 | **Behavioral Monitoring** | What are you doing? | AI-driven anomaly detection and baselines |
| 3 | **Data Governance** | What are you eating? What are you serving? | Guard both inputs and outputs |
| 4 | **Segmentation** | Where can you go? | Enforce boundaries between agent systems |
| 5 | **Incident Response** | What if you go rogue? | Kill switches and recovery in minutes |

See the [full specification](./SPECIFICATION.md) for detailed requirements, compliance mappings, and implementation guidance.

## Agent Maturity Model

Agents earn autonomy through demonstrated trustworthiness — and can be demoted. Four levels aligned to the [AWS Agentic AI Security Scoping Matrix](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-security-scoping-matrix/overview.html):

| Level | Autonomy | Human Involvement | Example |
|-------|----------|-------------------|---------|
| **Intern** | Observe only | Continuous supervision | Reads dashboards, drafts reports for review |
| **Junior** | Recommend | Approves all actions | Proposes code changes, human merges |
| **Senior** | Act with guardrails | Notified after actions | Deploys to staging, alerts on anomalies |
| **Principal** | Autonomous in scope | Strategic oversight only | Manages incident response within defined playbooks |

Promotion requires passing five gates: performance, security validation, business value, clean incident record, and governance sign-off. See [MATURITY_MODEL.md](./MATURITY_MODEL.md) for full criteria.

## Ecosystem

ATF is an open specification — implementations are built independently by the community:

- [**Microsoft Agent Governance Toolkit**](https://github.com/microsoft/agent-governance-toolkit) — Policy enforcement, zero-trust identity, and execution sandboxing for AI agents. [CSA ATF alignment proposal](https://github.com/microsoft/agent-governance-toolkit/blob/main/docs/CSA-ATF-PROPOSAL.md).
- [**Berlin AI Labs**](https://berlinailabs.de) — 12-service reference implementation covering all 5 ATF elements with contract validation testing.

Building on ATF? Open an issue or PR — we'd love to list your implementation.

## Comparison to Other Frameworks

ATF is complementary to existing security and governance frameworks:

| Framework | Focus | Relationship to ATF |
|-----------|-------|---------------------|
| **MAESTRO** (CSA) | Threat modeling for agentic AI (7 layers) | ATF implements the security architecture that MAESTRO's threat model identifies |
| **OWASP Top 10 for Agentic Apps** | Risk identification (ASI-01 through ASI-10) | ATF's five elements provide controls that address all 10 risks |
| **NIST AI RMF / 800-207** | Broad AI risk + Zero Trust architecture | ATF operationalizes Zero Trust specifically for agent governance |
| **AWS Agentic AI Security Scoping** | Autonomy classification (Scopes 1-4) | ATF's maturity levels align directly to AWS scopes |
| **OWASP AEGIS** | AI governance and ethical guardrails | Complementary scope; ATF focuses on runtime enforcement |

## Getting Started

**Assess your current posture:**
- Review the [specification](./SPECIFICATION.md) and [maturity model](./MATURITY_MODEL.md)
- Run the [self-assessment questionnaire](https://agentictrustframework.ai/assessment) (30 questions, 10 minutes)
- Explore [implementation patterns](./IMPLEMENTATION_PATTERNS.md) for your stack

**Implement:**
- Start at the Intern level — full supervision, minimal risk
- Use the [Technical Component Catalog](https://agentictrustframework.ai/components) for recommended open-source tooling
- Promote agents through the maturity levels as they earn trust

## Specification Status

🚧 **v0.1.0-draft** — Accepting feedback via [Issues](https://github.com/massivescale-ai/agentic-trust-framework/issues) and PRs.

### Roadmap

- [x] Publish initial specification draft
- [x] CSA research publication ([Feb 2026](https://cloudsecurityalliance.org/blog/2026/02/02/the-agentic-trust-framework-zero-trust-governance-for-ai-agents))
- [ ] Community feedback and ecosystem growth (ongoing)
- [ ] Conformance criteria and testing guidance
- [ ] v1.0 specification release

## Contributing

We welcome contributions to the specification:

1. Read the [Specification](./SPECIFICATION.md) and [Contribution Guidelines](./CONTRIBUTIONS.md)
2. Open an Issue for discussion or a PR for proposed changes
3. Implementation feedback is especially valued — tell us what works and what doesn't

## Background

ATF grew out of research into applying Zero Trust architecture to autonomous AI systems. The theoretical foundations are detailed in [*Agentic AI + Zero Trust: A Guide for Business Leaders*](https://www.amazon.com/dp/B0FL2WJQVQ) (2025), with the specification developed through CSA working group collaboration.

## License

Specification: [Apache License 2.0](LICENSE). Build freely.

## Contact

- **Specification**: [agentictrustframework.ai](https://agentictrustframework.ai)
- **Author**: Josh Woodruff — CSA Research Fellow, IANS Faculty
- **Discussions**: [GitHub Issues](https://github.com/massivescale-ai/agentic-trust-framework/issues)
- **Business**: info@massivescale.ai
