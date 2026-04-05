# ISO 42001 Resource Hub — AI Management Systems

> A practitioner-focused reference for understanding and implementing ISO/IEC 42001:2023 — the international standard for AI Management Systems.

Written for solution architects, technology managers, governance leads, and consultants working with AI systems in regulated or enterprise environments. Not a summary. Not a sales pitch. A working reference that will grow over time.

---

## Contents

1. [What is ISO/IEC 42001?](#what-is-isoiec-42001)
2. [What It Is and Is Not](#what-it-is-and-is-not)
3. [Who This Standard Is For](#who-this-standard-is-for)
4. [The Standard at a Glance](#the-standard-at-a-glance)
5. [Key Concepts](#key-concepts)
6. [ISO 42001 in Practice: Financial AI Governance](#iso-42001-in-practice-financial-ai-governance)
7. [ISO 42001 vs NIST AI RMF](#iso-42001-vs-nist-ai-rmf)
8. [2026 Regulatory Context](#2026-regulatory-context)
9. [Free Resources](#free-resources)
10. [Contributing](#contributing)

---

## What is ISO/IEC 42001?

ISO/IEC 42001:2023 is the first internationally recognised management system standard for artificial intelligence. Published in December 2023 by the International Organisation for Standardisation (ISO) and the International Electrotechnical Commission (IEC), it provides a framework for organisations to manage AI responsibly, consistently, and with demonstrable accountability.

Like ISO 27001 for information security or ISO 9001 for quality management, ISO 42001 follows the **High-Level Structure (HLS)** — the common clause framework that makes it structurally compatible with other management system standards and easier to integrate into existing governance programs. Organisations already certified to ISO 27001 will find the structure familiar and the integration relatively straightforward.

---

## What It Is and Is Not

**ISO 42001 is:**

- A **certifiable** management system standard — third-party audit and certification by accredited bodies is possible and increasingly expected in regulated markets
- A **requirements** standard — it uses "shall" throughout. These are obligations, not suggestions
- A **risk-based** framework covering the entire AI lifecycle, from design and procurement through deployment, monitoring, and decommissioning
- **Compatible with and complementary to** ISO 27001, ISO 31000, and the NIST AI RMF — it is designed to integrate, not replace

**ISO 42001 is not:**

- A technical standard for how to build AI models — it governs how organisations manage AI, not the engineering of models themselves
- A point-in-time checklist — it is a management system, which means ongoing operation, monitoring, and improvement
- A substitute for the EU AI Act, NIST AI RMF, or sector-specific regulations — it is a foundation layer that those requirements build on
- A guarantee of ethical AI — certification demonstrates a governance framework exists and operates; it does not guarantee outcomes. The distinction matters.

---

## Who This Standard Is For

ISO 42001 applies to **any organisation that develops, provides, or uses AI systems**. The standard deliberately does not prescribe a minimum size, sector, or geography. What matters is whether AI is part of your operations and whether the risks from that AI are being managed.

Practically, the organisations with the most pressing need are those where:

- AI systems make or influence decisions with material consequences — credit decisions, clinical recommendations, hiring, financial transactions, public services
- Regulatory exposure is growing — EU AI Act obligations, sector-specific rules, government procurement requirements
- Customers, partners, or investors are requesting evidence of responsible AI governance — this is becoming a procurement and due diligence standard
- **Agentic AI systems are being deployed** — autonomous agents that act, transact, communicate, or commit on behalf of operators without per-action human approval

That last point warrants particular attention in 2026. The deployment of agentic AI has moved from experiment to production in many organisations, and the governance gap it creates is exactly what ISO 42001 is designed to address.

---

## The Standard at a Glance

ISO 42001 is structured in 10 clauses. Clauses 1–3 cover scope, definitions, and normative references. The operative requirements are in Clauses 4–10, with normative Annex A (controls) and informative Annex B (implementation guidance).

### Clauses 4–10

| Clause | Title | What It Requires |
|--------|-------|-----------------|
| **4** | Context of the Organisation | Understand your organisation, relevant internal and external context, stakeholder expectations, the scope of your AI Management System (AIMS), and which AI systems are in scope |
| **5** | Leadership | Senior management accountability for the AIMS, an AI policy that is communicated and enforced, defined roles and responsibilities for AI governance |
| **6** | Planning | Risk and opportunity assessment, AI-specific risk identification across the lifecycle, setting measurable objectives and plans to achieve them |
| **7** | Support | Resources, competence requirements (training and awareness), internal and external communication, documented information controls |
| **8** | Operation | Operational planning and control, AI system impact assessment before deployment, supply chain and third-party AI governance, lifecycle operational controls |
| **9** | Performance Evaluation | Monitoring and measurement, internal audit program, management review of AIMS performance |
| **10** | Improvement | Nonconformity identification, corrective action, continual improvement of the AIMS |

### Annex A Controls

Annex A contains 38 controls across 8 control categories. Unlike a checklist, organisations are expected to assess which controls are applicable given their context and document a Statement of Applicability (similar to ISO 27001 practice).

| Category | Controls | Focus Area |
|----------|---------|-----------|
| **5** | 5.1–5.7 | Policies for AI — responsible use, data governance, AI objectives |
| **6** | 6.1–6.2 | Internal organisation — roles, AI responsibilities in organisational structure |
| **7** | 7.1–7.5 | Resources for AI — computational, data, human expertise |
| **8** | 8.1–8.6 | AI system lifecycle — specification, design, testing, deployment, operation, decommissioning |
| **9** | 9.1–9.3 | Human oversight — mechanisms for human review, intervention, and control of AI systems |
| **10** | 10.1 | Documentation of AI systems — system cards, data provenance, model documentation |
| **11** | 11.1–11.5 | Suppliers and third parties — governance of AI components, APIs, and services sourced externally |

> **Note on Annex A applicability:** Not every control applies to every organisation. A company that only uses pre-built AI APIs (rather than training models) will apply Annex A differently to one that develops foundation models. Scoping and the Statement of Applicability are where that judgement is exercised and documented.

---

## Key Concepts

### AI Management System (AIMS)

An AIMS is the set of policies, processes, roles, responsibilities, and controls an organisation establishes to govern its AI activities. It is not software — it is a governance structure. The standard requires organisations to define the scope of their AIMS, document how the system operates, and demonstrate through evidence that it is functioning as intended. The management system framing means it is a living system, not a one-time project.

### Risk-Based Approach

ISO 42001 requires organisations to assess the risks their AI systems present and calibrate controls accordingly. A content recommendation algorithm has a different risk profile to an autonomous agent making financial commitments on behalf of its operator. The standard does not apply a single fixed level of control to all AI — it requires proportionality, which means the risk assessment is the foundation everything else rests on.

### AI System Impact Assessment

Clause 8 requires organisations to conduct an impact assessment before deploying an AI system. This is conceptually similar to a Data Protection Impact Assessment (DPIA) under GDPR but scoped to AI-specific risks: What could go wrong? Who could be harmed? How likely is it? What controls are in place? The assessment must be documented and reviewed.

### Responsible AI Principles

The standard references responsible AI principles that an organisation's policies should operationalise. These typically include:

- **Transparency** — AI systems and their decision logic should be explainable to those affected
- **Accountability** — There is a clear human responsible for each AI system's governance
- **Fairness and non-discrimination** — AI outputs are assessed for bias and disparate impact
- **Privacy and security** — AI systems handle data in accordance with privacy obligations and are designed to resist adversarial manipulation
- **Safety and reliability** — AI systems behave as intended, including under edge cases and novel inputs
- **Human oversight** — Humans retain meaningful ability to review, correct, and override AI system outputs

These are not values statements. The standard requires them to be reflected in documented policies and operational controls.

### Agentic AI and Autonomous Systems

ISO 42001 was published at a point when agentic AI — AI that takes actions in the world without per-step human approval — was emerging from research into production. The standard's requirements around human oversight (Annex A 9.x), AI system impact assessment, and operational controls are the primary levers for governing this class of system.

In 2026, this is the fastest-moving area of ISO 42001 application. Organisations deploying agents into production are discovering that existing controls — system prompts, rate limits, spend caps embedded in application code — are not auditable in the way regulators and enterprise risk functions are beginning to require.

---

## ISO 42001 in Practice: Financial AI Governance

One of the clearest current test cases for ISO 42001's requirements is the governance of AI agents that can spend money.

Autonomous AI agents — systems that can book, purchase, subscribe, or commit contractually on behalf of their operators — represent a category of operational risk that existing financial controls were not designed to handle. An employee using a company card has human intent behind each transaction and leaves a traceable approval chain. An AI agent has neither, unless governance is explicitly architected in.

ISO 42001 Clause 8 and Annex A Category 9 (human oversight) are directly relevant here. They require organisations to:

- Define the scope of authority their AI systems operate within — and enforce it, not just describe it in a policy document
- Document what triggers human review and how that review is conducted before action is taken
- Maintain an audit trail that is sufficient for post-incident investigation and regulatory inquiry
- Assess the impact of the AI system before deployment — including what happens in failure modes

For AI agents with financial authority, these requirements translate to concrete design questions:

**Scope enforcement:** Is the agent's spending authority defined in policy, or enforced at the infrastructure layer? Policy-only controls are vulnerable to prompt injection, model hallucination, and misconfiguration. Infrastructure-layer controls — rules that apply regardless of what the model generates — are what ISO 42001's deterministic control requirements are pointing toward.

**Audit trail:** A Slack notification and an email approval constitute a human-in-the-loop. They do not constitute an auditable record of the reasoning behind a transaction, the identity of the approving human, the time taken, or the policy basis for the decision. Regulators, particularly under the EU AI Act, are beginning to distinguish between these.

**Impact assessment:** Before deploying an agent with financial authority, what is the worst-case financial exposure if the agent behaves unexpectedly? What is the blast radius of a compromised agent key? Has that been documented and accepted by a named accountable person?

**Monitoring:** Are agent transactions being monitored for anomalous patterns? Who is alerted, at what threshold, and how quickly?

Organisations getting this right in 2026 are implementing a dedicated financial control layer — something that sits between the agent and the payment infrastructure and enforces rules deterministically. The governance pattern involves identity verification at the transaction layer, a rules engine for spending caps and category controls, a human approval loop that produces attributable and timestamped records, and an immutable audit log that exists independently of the agent framework.

This is ISO 42001 Annex A operationalised in a financial context. Not theory — production governance for organisations deploying agentic AI where the stakes include real money and regulatory liability.

---

## ISO 42001 vs NIST AI RMF

These two frameworks are frequently discussed together and sometimes confused. They are complementary, serving different purposes and different contexts.

| Dimension | ISO/IEC 42001:2023 | NIST AI RMF (2023) |
|-----------|-------------------|-------------------|
| **Type** | Management system standard | Risk management framework |
| **Certifiable** | Yes — accredited third-party certification | No — voluntary framework, no certification |
| **Language** | "Shall" — requirements | "Should" — guidance |
| **Structure** | 10 clauses + Annex A controls | 4 functions: GOVERN, MAP, MEASURE, MANAGE |
| **Geographic origin** | International (ISO/IEC) | United States (NIST) |
| **Primary driver** | Formal certification, regulatory alignment, international markets | US federal agencies, structured risk guidance |
| **Prescriptiveness** | Higher — specifies what must be in place | Lower — specifies what to think about |
| **Compatibility** | References NIST AI RMF; designed to integrate | Maps well to ISO 42001 clause structure |

**In practice:**

ISO 42001 is the right primary framework for organisations that need certification, operate in international markets, are responding to EU or APAC regulatory requirements, or want a formal management system with clear audit criteria.

NIST AI RMF is a valuable complement — its playbooks and practice guides provide more granular operational guidance than ISO 42001 alone. Many organisations implement NIST AI RMF practices as the operational layer within an ISO 42001 management system. The two are not in competition.

The most common pattern in 2026: implement ISO 42001 as the governance framework and certification target, use NIST AI RMF playbooks to inform the specific risk practices inside it.

---

## 2026 Regulatory Context

ISO 42001 exists within a rapidly evolving regulatory landscape. Understanding the relationship between the standard and relevant regulations is important for positioning your implementation.

### EU AI Act

The EU AI Act reached full applicability for high-risk AI systems in August 2026. It does not mandate ISO 42001 certification, but its requirements — documented risk management systems, technical documentation, accuracy and robustness requirements, human oversight mechanisms — map closely to ISO 42001 controls. Harmonised standards under the EU AI Act are still being finalised; ISO 42001 is positioned as a likely reference standard.

For financial services specifically, the EU AI Act creates direct liability for payment service providers that cannot explain or audit AI-initiated transactions. This is materially changing how enterprise legal and compliance teams are evaluating AI agent deployments.

### Australia

Australia's AI governance framework has been developing through 2025–2026, building on the Voluntary AI Safety Standard and the APS AI Policy for government agencies. ISO 42001 provides a structured, internationally recognised baseline that aligns with the direction of Australian regulatory thinking, particularly for regulated sectors (financial services, healthcare, critical infrastructure) and government procurement, where governance requirements are tightening.

The Privacy Act reforms and the evolving framework from the OAIC also intersect with ISO 42001's data governance controls.

### Sector-Specific Overlays

ISO 42001 provides the management system foundation. Sector-specific requirements layer on top:

- **Financial services:** APRA guidance on model risk, ASIC expectations on AI in financial advice, EU AI Act financial services provisions
- **Healthcare:** TGA considerations for AI as a medical device, clinical governance requirements
- **Government:** APS AI Policy, sector-specific security requirements, procurement rules

ISO 42001 does not replace these. It provides the governance architecture into which sector-specific controls are integrated.

---

## Free Resources

The following resources are available as free downloads from [AIrchitect](https://airchitect.com.au). They are working documents — designed to be used, not filed.

| Resource | Format | What It Is |
|----------|--------|-----------|
| [ISO 42001 Gap Assessment Checklist](#) | XLSX | Assess your current state against each clause and Annex A control. Status tracking, evidence fields, and a summary dashboard. |
| [ISO 42001 vs NIST AI RMF Comparison Sheet](#) | XLSX | Control-level mapping of both frameworks side by side. Useful for organisations managing both or making an adoption decision. |
| [AI System Inventory Template](#) | XLSX | A structured register for cataloguing AI systems, their risk classifications, deployment status, and governance owners. |

Premium implementation templates — including Statement of Applicability templates, AI System Impact Assessment frameworks, and audit preparation kits — are available at [AIrchitect](https://airchitect.com.au).

---

## Contributing

This repository is a working reference, not a polished product. Corrections, additions, and contributions are welcome.

**Found an error?** Open an issue with the specific clause, claim, or reference that needs correcting, and the source you're using.

**Want to add content?** Open an issue describing what you'd like to add before submitting a pull request. This keeps the scope manageable.

**Scope:** This repository covers ISO/IEC 42001 and its direct relationships with NIST AI RMF and relevant regulations. Adjacent frameworks (ISO 27001 integration, sector-specific overlays) will be added over time.

---

## About

Maintained by [Dani Storey](https://www.linkedin.com/in/danielle-storey/) — AI governance practitioner and founder of [Valkurai](https://valkurai.com) and [AIrchitect](https://airchitect.com.au).

This is a free educational resource. The examples used throughout reflect real governance patterns observed in enterprise AI deployments. Where specific products or approaches are referenced, they are illustrative, not endorsements.

*Last updated: April 2026*
