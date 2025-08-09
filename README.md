# Agentic Trust Framework (ATF)

**A specification for implementing Zero Trust security for AI agents**

[![Specification Version](https://img.shields.io/badge/spec-v0.1.0--draft-yellow.svg)](./SPECIFICATION.md)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Overview

The Agentic Trust Framework (ATF) is an open specification that defines security standards for AI agents. It provides a blueprint for implementing Zero Trust principles in agentic AI systems, based on the book ["Agentic AI + Zero Trust: A Guide for Business Leaders"](https://www.amazon.com/dp/B0FL2WJQVQ).

**This is a specification and reference architecture.** We define the security principles; implementations demonstrate them in practice.

## Why This Matters

AI agents with access to your systems need security boundaries. This framework implements the five core elements of Zero Trust for AI introduced in the book:

## The Five Core Elements

1. **Identity Management** → "Who are you?"
   Every AI agent gets unforgeable credentials.

2. **Behavioral Monitoring** → "What are you doing?"
   AI watches AI for abnormal patterns.

3. **Data Governance** → "What are you eating? What are you serving?"
   Guard both inputs and outputs.

4. **Segmentation** → "Where can you go?"
   Build walls between AI systems.

5. **Incident Response** → "What if you go rogue?"
   Kill switches and recovery in minutes.

See the [full specification](./SPECIFICATION.md) for detailed requirements.

## Status

🚧 **Specification**: v0.1.0-draft (accepting feedback)  
🔨 **Reference Implementation**: In development for our platforms

The ATF specification is open for feedback and discussion. The reference implementation is being built for:
- 🚀 [Your First Agent](https://yourfirstagent.ai) - See ATF principles in action
- ☁️ [ZeroTrustAgents](https://zerotrustagents.ai) - Production ATF implementation

## Quick Example

This example shows what ATF-compliant code looks like:

```python
# This is aspirational - implementations will vary
class MyAgent:
    """An AI agent that follows ATF specification"""
    
    def __init__(self):
        self.identity = IdentityProvider.issue_credentials()  # Element 1
        self.monitor = BehaviorMonitor.for_agent(self)       # Element 2
        self.data_guard = DataGovernance()                   # Element 3
        self.access_control = Segmentation()                  # Element 4
        self.incident_handler = IncidentResponse()            # Element 5
```

## For Users

If you're looking to **use** secure AI agents:
- Read the [book](https://www.amazon.com/dp/B0FL2WJQVQ) for the theory
- Try [Your First Agent](https://yourfirstagent.ai) for hands-on experience
- Host on [ZeroTrustAgents](https://zerotrustagents.ai) for production

## For Implementers

Want to implement ATF in your own systems?
1. Read the [Specification](./SPECIFICATION.md)
2. Review our [Security Principles](./SECURITY.md)
3. Build according to your needs
4. Share your learnings with the community

## Comparison to Other Frameworks

| Framework | Focus | Approach |
|-----------|-------|----------|
| ATF | Security-first for AI agents | Zero Trust principles |
| LangChain | Agent building | Development tools |
| Guardrails | Output validation | Rule-based checking |

ATF is complementary to existing frameworks, adding the security layer they lack.

## Background

This specification implements the security principles from "Agentic AI + Zero Trust: A Guide for Business Leaders" by Josh Woodruff. The book provides the theory; this specification provides the blueprint for practice.

## Roadmap

- [x] Publish initial specification draft
- [ ] Gather community feedback (ongoing)
- [ ] Build reference implementation in ZeroTrustAgents
- [ ] Share implementation learnings
- [ ] Evolve specification based on real-world usage

## License

The specification is licensed under [Apache License 2.0](LICENSE). Build freely!

## Contact

- **Author**: Josh Woodruff ([@jlwoodruff](https://twitter.com/jlwoodruff))
- **Discussions**: Use GitHub Issues for specification questions
- **Business**: contact@massivescale.ai

---

*Building secure AI agents? Star this repo to follow our progress!*