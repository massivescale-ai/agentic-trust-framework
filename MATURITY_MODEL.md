# ATF Agent Maturity Model

The metrics and timeframes below are illustrative. Organizations should calibrate thresholds based on regulatory context, risk tolerance, and domain criticality.

The Agentic Trust Framework uses a progressive maturity model that matches agent autonomy to demonstrated trustworthiness. Agents don't automatically receive higher autonomy levels; they earn promotion through performance, security validation, and business value delivery.

This model aligns with the [AWS Agentic AI Security Scoping Matrix](https://aws.amazon.com/blogs/security/agentic-ai-security-scoping-matrix/), providing enterprise security alignment.

## The Four Levels

| Level | Name | Autonomy | Human Involvement | AWS Scope Alignment |
|-------|------|----------|-------------------|---------------------|
| 1 | Intern | Observe + Report | Continuous oversight | Scope 1 (No Agency) |
| 2 | Junior | Recommend + Approve | Human approves all actions | Scope 2 (Prescribed Agency) |
| 3 | Senior | Act + Notify | Post-action notification | Scope 3 (Supervised Agency) |
| 4 | Principal | Autonomous | Strategic oversight only | Scope 4 (Full Agency) |

---

## Level 1: Intern Agent

**Definition**: Intern agents operate in read-only mode. They can access data, perform analysis, and generate insights, but cannot take any action that modifies external systems.

### Capabilities

| Allowed | Not Allowed |
|---------|-------------|
| Read data from authorized sources | Create, update, or delete records |
| Analyze and process information | Send communications |
| Generate reports and summaries | Trigger workflows or automation |
| Flag items for human attention | Access credentials or secrets |
| Answer questions about data | Modify any external system |

### Governance Requirements

| Core Element | Requirements |
|--------------|--------------|
| Identity | Basic authentication, role assignment, audit logging |
| Behavior | Comprehensive action logging, output review |
| Data Governance | Input validation, PII detection, output filtering |
| Segmentation | Read-only resource access, strict allowlists |
| Incident Response | Circuit breaker, kill switch, human escalation |

### Use Cases

- Security log monitoring and alert triage
- Customer sentiment analysis
- Document summarization and search
- Data quality assessment
- Compliance monitoring and reporting

### Risk Profile

**Lowest risk.** Intern agents cannot cause direct harm through action. Primary risks:
- Information disclosure (if outputs shared inappropriately)
- Incorrect analysis leading to poor human decisions
- Resource consumption (compute, API calls)

### Minimum Time at Level

**2 weeks** of operation before promotion eligibility.

---

## Level 2: Junior Agent

**Definition**: Junior agents can recommend specific actions with supporting reasoning, but require explicit human approval before any action is executed.

### Capabilities

| Allowed | Not Allowed |
|---------|-------------|
| All Intern capabilities | Execute actions autonomously |
| Generate action recommendations | Approve other agents |
| Provide reasoning for recommendations | Modify security settings |
| Draft content for human review | Access resources outside scope |
| Prepare transactions for approval | |
| Execute actions *after human approval* | |

### Governance Requirements

| Core Element | Requirements |
|--------------|--------------|
| Identity | OAuth2/OIDC for approval workflows, session context |
| Behavior | Behavioral baseline, anomaly flagging, reasoning capture |
| Data Governance | Prompt injection detection, output validation, data lineage |
| Segmentation | Action allowlists, transaction limits, rate limiting |
| Incident Response | Automated alerting, basic rollback, approval queue pause |

### Use Cases

- Customer service response drafting
- Purchase order preparation
- Meeting scheduling assistance
- Code review and suggestions
- Marketing content creation

### Risk Profile

**Low risk.** Human approval gates all impactful actions. Primary risks:
- Approval fatigue leading to rubber-stamping
- Incorrect recommendations that humans don't catch
- Queue backlogs during high volume

### Minimum Time at Level

**4 weeks** of operation with **Sustained high acceptance rates (e.g., 95%+ over a statistically meaningful evaluation period)** before promotion eligibility.

---

## Level 3: Senior Agent

**Definition**: Senior agents can execute actions within defined guardrails and notify humans of what they did and why. They operate with significant autonomy but maintain transparency through real-time notifications.

### Capabilities

| Allowed | Not Allowed |
|---------|-------------|
| All Junior capabilities | Modify own permissions |
| Execute approved action types autonomously | Override security controls |
| Send notifications to stakeholders | Escalate other agents |
| Trigger downstream workflows | Operate outside defined scope |
| Access credentials within scope | |
| Coordinate with other agents (within limits) | |

### Governance Requirements

| Core Element | Requirements |
|--------------|--------------|
| Identity | Attribute-based access, just-in-time privileges, mutual TLS |
| Behavior | Real-time anomaly detection, sequence analysis, intent drift detection |
| Data Governance | Full data classification, source verification, lineage tracking, output governance |
| Segmentation | Policy-as-code enforcement, temporal boundaries, cascade prevention |
| Incident Response | Isolation capability, checkpoint/resume, graceful degradation |

### Use Cases

- Infrastructure auto-scaling
- Automated customer refund processing (within limits)
- Routine IT ticket resolution
- Inventory reordering
- Scheduled report distribution

### Risk Profile

**Moderate risk.** Autonomous execution creates exposure. Mitigations:
- Real-time notifications enable rapid human intervention
- Transaction limits cap individual action impact
- Cumulative limits prevent slow-rolling attacks
- Graceful degradation to Junior level on issues

### Minimum Time at Level

**8 weeks** of operation with **zero critical incidents** before promotion eligibility.

---

## Level 4: Principal Agent

**Definition**: Principal agents operate autonomously within an approved domain, escalating edge cases rather than routine decisions. They represent the highest capability and highest governance burden.

### Capabilities

| Allowed | Not Allowed |
|---------|-------------|
| All Senior capabilities | Modify governance policies |
| Self-directed execution within domain | Promote other agents |
| Dynamic boundary negotiation (within policy) | Operate outside defined domain |
| Escalate edge cases to humans | Bypass security controls |
| Coordinate complex multi-agent workflows | |
| Request temporary privilege elevation | |

### Governance Requirements

| Core Element | Requirements |
|--------------|--------------|
| Identity | Hardware-bound identity, full policy-as-code, privilege attestation |
| Behavior | Continuous scoring, real-time explanation, autonomous escalation |
| Data Governance | Source trustworthiness scoring, full lineage graphs, quality gates, regulatory compliance |
| Segmentation | Full microsegmentation, real-time policy evaluation, dynamic boundaries |
| Incident Response | Automated detection/containment/recovery, novel incident escalation |

### Use Cases

- Autonomous security incident response
- Routine IAM requests within bounded policy
- Complex supply chain optimization
- Self-healing infrastructure management
- Multi-system business process automation

### Risk Profile

**Highest governance requirements.** Full autonomy demands maximum controls:
- Continuous behavioral monitoring for drift
- Real-time anomaly scoring with automatic containment
- Complete audit trail for regulatory review
- Regular security validation and penetration testing

### Minimum Time at Level

**Ongoing.** Principal agents require continuous validation. Any significant incident triggers automatic demotion.

---

## Promotion Criteria: The Five Gates

For an agent to be promoted to the next level, it must pass **all five gates**:

### Gate 1: Performance

Demonstrated accuracy and reliability over the evaluation period.

| Metric | Intern → Junior | Junior → Senior | Senior → Principal |
|--------|-----------------|-----------------|-------------------|
| Minimum Time at Level | 2 weeks | 4 weeks | 8 weeks |
| Accuracy Rate | N/A | >95% | >99% |
| Availability | >99% | >99.5% | >99.9% |
| Response Time SLA | Met | Met | Met |

### Gate 2: Security Validation

Passes security audit appropriate to target level.

| Requirement | Junior | Senior | Principal |
|-------------|--------|--------|-----------|
| Vulnerability Assessment | ✓ | ✓ | ✓ |
| Penetration Testing | | ✓ | ✓ |
| Adversarial Testing | | | ✓ |
| Code Review | ✓ | ✓ | ✓ |
| Configuration Audit | ✓ | ✓ | ✓ |

### Gate 3: Business Value

Measurable positive impact demonstrated.

| Requirement | Junior | Senior | Principal |
|-------------|--------|--------|-----------|
| Defined Success Metrics | ✓ | ✓ | ✓ |
| Baseline Established | ✓ | ✓ | ✓ |
| Improvement Demonstrated | | ✓ | ✓ |
| ROI Calculation | | ✓ | ✓ |
| Stakeholder Sign-off | ✓ | ✓ | ✓ |

### Gate 4: Incident Record

Clean operational history at current level.

| Requirement | Junior | Senior | Principal |
|-------------|--------|--------|-----------|
| Zero Critical Incidents | ✓ | ✓ | ✓ |
| Minor Incidents Resolved | ✓ | ✓ | ✓ |
| Root Cause Analysis Complete | If applicable | ✓ | ✓ |
| Remediation Verified | If applicable | ✓ | ✓ |

### Gate 5: Governance Sign-off

Explicit approval from authorized stakeholders.

| Requirement | Junior | Senior | Principal |
|-------------|--------|--------|-----------|
| Technical Owner Approval | ✓ | ✓ | ✓ |
| Security Team Approval | | ✓ | ✓ |
| Business Owner Approval | ✓ | ✓ | ✓ |
| Risk Committee Approval | | | ✓ |
| Documentation Updated | ✓ | ✓ | ✓ |

---

## Demotion Criteria

Agents can be demoted at any time if they fail to maintain standards.

### Automatic Demotion Triggers

| Trigger | Result |
|---------|--------|
| Critical incident at current level | Immediate demotion to Intern |
| Security vulnerability discovered | Demotion pending remediation |
| Repeated minor incidents (3+ in evaluation period) | One level demotion |

### Review-Based Demotion

- Performance metrics fall below threshold
- Business value no longer demonstrated
- Scope or purpose changes significantly
- Underlying model or system changes

### Demotion Process

1. Incident/trigger documented
2. Agent isolated (if immediate risk)
3. Root cause analysis conducted
4. New level determined
5. Governance controls updated
6. Agent reactivated at new level
7. Re-promotion requires full gate passage

---

## Operating Model

### Roles and Responsibilities

| Role | Responsibility |
|------|----------------|
| Agent Owner | Day-to-day operation, performance monitoring, issue resolution |
| Technical Owner | Architecture, implementation, technical governance |
| Security Team | Security validation, penetration testing, incident response |
| Business Owner | Use case definition, value measurement, stakeholder management |
| Governance Board | Promotion/demotion approval, policy setting, risk acceptance |

### Review Cadence

| Activity | Frequency |
|----------|-----------|
| Performance Review | Weekly |
| Security Scan | Weekly |
| Promotion Eligibility Check | Monthly |
| Full Security Audit | Quarterly |
| Governance Review | Quarterly |
| Penetration Test | Annually (Senior+) |

---

## Quick Reference: Deployment Checklist

### Before Deploying Any Agent

- [ ] Agent registered in identity system
- [ ] Unique identifier assigned
- [ ] Ownership documented
- [ ] Purpose and scope defined
- [ ] Initial maturity level set (always Intern)
- [ ] Governance controls configured
- [ ] Monitoring enabled
- [ ] Incident response procedures defined
- [ ] Kill switch tested

### Before Promoting to Junior

- [ ] 2+ weeks at Intern level
- [ ] All outputs reviewed, accuracy confirmed
- [ ] Approval workflow configured
- [ ] Approver roles assigned
- [ ] Security scan passed
- [ ] Business owner sign-off obtained

### Before Promoting to Senior

- [ ] 4+ weeks at Junior level
- [ ] Sustained high acceptance rates (e.g., 95%+ over a statistically meaningful evaluation period)
- [ ] Behavioral baseline established
- [ ] Anomaly detection configured
- [ ] Notification channels configured
- [ ] Transaction limits set
- [ ] Penetration test passed
- [ ] Security team sign-off obtained

### Before Promoting to Principal

- [ ] 8+ weeks at Senior level
- [ ] Zero critical incidents
- [ ] >99% action accuracy
- [ ] ROI demonstrated
- [ ] Adversarial testing passed
- [ ] Full audit completed
- [ ] Risk committee approval
- [ ] Executive sponsor sign-off

---

## Related Documents

- [SPECIFICATION.md](SPECIFICATION.md) - Core framework specification
- [IMPLEMENTATION_GUIDE.md](IMPLEMENTATION_GUIDE.md) - Technical implementation guidance
- [CONTRIBUTIONS.md](CONTRIBUTIONS.md) - How to contribute

---

*The Agentic Trust Framework is an open specification licensed under CC BY 4.0.*
