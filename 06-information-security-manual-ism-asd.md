# Information Security Manual (ISM)

**Publisher:** Australian Signals Directorate (ASD) / Australian Cyber Security Centre (ACSC)
**Format:** Living document updated quarterly
**Current Version:** December 2025 (as of April 2026)
**Status:** Mandatory for government — reference standard for regulated industry
**Applies to:** Mandatory for Australian Government agencies and systems. Reference framework for critical infrastructure operators, regulated industries, and suppliers to government.
**Source:** [cyber.gov.au](https://www.cyber.gov.au/business-government/asds-cyber-security-frameworks/ism)

---

## What This Is

The Information Security Manual (ISM) is the Australian Signals Directorate's cyber security framework. It provides a set of controls that organisations can apply — using their risk management framework — to protect information technology and operational technology systems from cyber threats.

The ISM is not an AI governance document. However, it is directly relevant to organisations deploying AI systems for two reasons:

1. **AI systems are technology systems** — they must comply with ISM controls where government or regulated sector requirements apply
2. **The December 2025 release added 21 new AI-specific controls**, reflecting ASD's view that AI-enabled systems introduce distinct security risks not fully addressed by traditional application security guidance

The ISM is updated quarterly. Practitioners should track the quarterly changelog, not just the annual update cycle.

---

## Structure of the ISM

The ISM is organised into guidelines covering:

- Guidelines for Cyber Security Roles
- Guidelines for Cyber Security Incidents
- Guidelines for Outsourcing
- Guidelines for Security Documentation
- Guidelines for Physical Security
- Guidelines for Personnel Security
- Guidelines for Communications Infrastructure
- Guidelines for Network Management
- Guidelines for System Hardening
- Guidelines for System Management
- Guidelines for Software Development (includes the new AI section)
- Guidelines for Database Systems
- Guidelines for Email
- Guidelines for Networking
- Guidelines for Cryptography
- Guidelines for Gateways
- Guidelines for Data Transfers

Each guideline contains controls classified as **Essential**, **Should**, or **Could** — indicating the strength of the recommendation.

---

## The December 2025 AI Controls — What's New

The December 2025 release introduced **21 new AI security controls** within the Guidelines for Software Development. This is the most significant AI-specific addition to the ISM to date. Key control areas are:

### Unbounded Consumption (Denial of Service)
AI systems are vulnerable to denial-of-service attacks through unbounded inference requests — attackers or runaway processes can exhaust compute or incur significant cost through excessive queries.

Controls require:
- Rate limiting on inference endpoints
- Resource caps on AI model inference (CPU, memory, time)
- Monitoring of AI model performance metrics with anomaly alerting

### Scope Control
AI systems — particularly agents — risk taking actions beyond their intended scope, either through prompt injection, model misalignment, or misconfiguration.

Controls require:
- Fine-grained access control policies for AI applications (what data and systems can the AI access?)
- Role-based access controls to restrict access to sensitive data from AI components
- Documented and enforced boundaries on AI system authority

**Practitioner note:** For agentic AI with financial authority, this control area directly intersects with the financial governance layer. Scope control is not just a policy — it must be enforced at the infrastructure layer. An AI agent given unrestricted API access to a payment system fails this control regardless of what the system prompt says.

### Content Filtering
AI systems must implement content filtering to:
- Detect and block inadvertent exposure of sensitive or personal data in outputs
- Prevent improper output — including outputs that could facilitate harm or violate policy
- Catch prompt injection attempts where possible

### AI Usage Policy
A new control recommends that organisations develop, implement, and maintain a general-purpose AI usage policy. This covers:
- Approved AI tools and services
- Acceptable use for different data classifications
- Prohibition on inputting sensitive or classified information into unapproved AI systems
- Training and awareness requirements

---

## ISM and AI System Lifecycle

For government-facing AI systems, ISM controls apply to the full system — including AI components. Relevant areas from existing ISM guidelines that apply to AI systems:

| ISM Guideline Area | Relevance to AI |
|-------------------|-----------------|
| Software Development | Training data provenance, model testing, code review for AI components |
| System Hardening | Hardening inference infrastructure, API security |
| System Management | Patching, monitoring, and change management for AI systems |
| Outsourcing | Controls for third-party AI APIs and foundation model providers |
| Cryptography | Encryption of training data, model artefacts, and inference data in transit/at rest |
| Networking | Network segmentation for AI inference infrastructure |

---

## How It Maps to ISO 42001

The ISM and ISO 42001 are complementary. The ISM covers the security controls for AI systems as technology; ISO 42001 covers the governance of AI systems as a managed risk.

| ISM Control Area | ISO 42001 Mapping |
|-----------------|-------------------|
| AI scope control | Annex A 9.1–9.3 (Human Oversight), Annex A 8.5 (Deployment and Operation) |
| AI usage policy | Annex A 5.4 (Responsible Use), Clause 7.3 (Awareness) |
| Content filtering | Annex A 8.4 (AI System Operation), Annex A 8.2 (Data for AI) |
| Rate limiting / resource caps | Annex A 8.5 (Operational Controls), Clause 9.1 (Monitoring) |
| Third-party AI (outsourcing) | Annex A 11.1–11.5 (Suppliers) |

Organisations targeting ISO 27001 alongside ISO 42001 will find the ISM maps well to ISO 27001 Annex A controls. The ISM is best understood as the Australian implementation guidance for information security controls — it operationalises what ISO 27001 requires in the Australian government context.

---

## Practitioner Notes

**Track the quarterly releases.** The ISM December 2025 update was the most significant AI addition to date, but it will not be the last. ASD is actively developing its AI security guidance in response to the rapidly evolving threat landscape. Subscribe to the ASD advisory channel and check the quarterly changelog.

**The AI scope control area is the one to watch for agentic AI.** As organisations deploy AI agents with real-world authority — financial, communications, system access — the ISM's scope control requirements become directly relevant. ASD's view is that scope must be enforced deterministically, not through prompt instructions.

**For government suppliers:** If you are providing AI systems to government, your system must be demonstrably compliant with relevant ISM controls. The DTA AI Technical Standard references the ISM. Government buyers will increasingly ask whether AI systems have been assessed against ISM controls as part of procurement due diligence.

---

*Last reviewed: April 2026 | Source: [cyber.gov.au](https://www.cyber.gov.au/business-government/asds-cyber-security-frameworks/ism)*
