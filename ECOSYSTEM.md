# ATF Ecosystem

Organizations building against the Agentic Trust Framework specification. Each entry describes how the project relates to ATF's five core elements (Identity, Behavior, Data Governance, Segmentation, Incident Response) and four-level maturity model.

To add your project, submit a pull request following the entry format below. Entries are limited to 10 lines each. Link to your own repository for full architectural detail.

---

## Microsoft Agent Governance Toolkit

**Organization**: Microsoft | **Relationship**: Independent convergence
**Repository**: [microsoft/agent-governance-toolkit](https://github.com/microsoft/agent-governance-toolkit)

Seven-package MIT-licensed open-source project (Python, TypeScript, Rust, Go, .NET) officially launched April 2, 2026. The toolkit's architecture independently validates all five ATF core elements. Microsoft's Principal Group Engineering Manager filed a formal conformance proposal ([CSA-ATF-PROPOSAL.md](https://github.com/microsoft/agent-governance-toolkit/blob/main/docs/proposals/CSA-ATF-PROPOSAL.md)) with detailed feedback in [Discussion #301](https://github.com/microsoft/agent-governance-toolkit/discussions/301), mapping the toolkit against ATF and proposing spec refinements. Three spec changes from that collaboration are committed for the next ATF point release.

| ATF Element | Toolkit Coverage |
|---|---|
| Identity | Workload identity, credential management |
| Behavior | Runtime monitoring, behavioral baselines |
| Data Governance | Input/output validation, PII protection |
| Segmentation | Policy enforcement, least-privilege boundaries |
| Incident Response | Circuit breakers, kill switches, containment |

## Berlin AI Labs — VERA

**Organization**: Berlin AI Labs | **Relationship**: ATF Reference Implementation
**Repository**: [berlinailabs/vera-reference-implementation](https://github.com/berlinailabs/vera-reference-implementation)

A cryptographic enforcement architecture integrating the Agentic Trust Framework. The repository maps 12 independently deployable, MIT-licensed microservices against all 25 ATF core requirements and 5 promotion gates. VERA utilizes an AWS Nitro Enclave (Rust) and SemaProof middleware to cryptographically sign agent intents and generate verifiable Certificate of Execution Records (CERs).

| ATF Element | Implementation Coverage |
|---|---|
| Identity | Decentralized agent trust scoring, DID:web credential verification |
| Behavior | Immutable Ed25519 Proof of Execution (PoE) & blockchain anchoring |
| Data Governance | Sub-20ms ONNX firewall with dynamic semantic boundary constraints |
| Segmentation | Policy-as-code A2A segmentation and strict SLA enforcement |
| Incident Response | Automated 41-vector adversarial containment and network kill switches |
