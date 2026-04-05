# AI Risk Identification: Standards, Taxonomies, and Treatment Options

> ISO 42001 requires you to assess AI risk. It does not tell you what AI risks look like. This document fills that gap.

Most practitioners doing AI risk assessments for the first time apply general risk management thinking to AI systems. That produces assessments that identify the risks they already know — data breach, reputational damage, regulatory non-compliance — and miss the risks that are specific to AI: model drift, prompt injection, automation bias, training data poisoning, distributional shift. These are not edge cases. They are the failure modes that have caused the most significant AI incidents in production to date.

This guide covers:
1. [Why AI risk identification is harder than it looks](#why-ai-risk-identification-is-harder-than-it-looks)
2. [The standards and frameworks that address it](#standards-and-frameworks-for-ai-risk-identification)
3. [A practitioner AI risk taxonomy](#ai-risk-taxonomy-for-practitioners)
4. [Treatment options mapped to risk type](#treatment-options)

---

## Why AI Risk Identification Is Harder Than It Looks

Standard risk management frameworks (ISO 31000, enterprise risk frameworks) are built on the assumption that systems behave deterministically — the same input produces the same output, and failure modes can be enumerated in advance. AI systems break this assumption in several important ways:

**AI systems are probabilistic.** The same input can produce different outputs. "Testing" an AI system does not produce a definitive answer about its behaviour — it produces a sample of behaviour from which you infer patterns.

**AI systems learn from data.** The risks are partially determined by the training data, which may contain biases, errors, or adversarially manipulated entries that are not visible in the final model.

**AI systems can fail in novel ways.** When a traditional system fails, it typically fails in a way that reflects a known category of failure (hardware fault, software bug, network issue). AI systems can fail in ways that are entirely new — a model that works correctly on all test cases encounters a distribution it has never seen and behaves unpredictably.

**AI systems are opaque.** For most production AI systems, it is not possible to explain with certainty why a specific output was produced. This makes root cause analysis of AI failures fundamentally different from root cause analysis of traditional system failures.

**Agentic AI adds a new dimension.** When AI systems take actions in the world — sending communications, making purchases, modifying systems — the consequence of a failure is no longer just a wrong output. It is a wrong action, potentially irreversible.

A risk assessor who does not understand these characteristics cannot identify the risks. They will produce a document that satisfies an audit but does not protect the organisation.

---

## Standards and Frameworks for AI Risk Identification

No single document covers everything. These are the most useful reference sources, organised by what they contribute.

---

### ISO/IEC 23894:2023 — Guidance on AI Risk Management

**What it is:** The official companion standard to ISO 42001 for AI risk management. Published February 2023 by ISO/IEC. Where ISO 42001 tells you that you must do risk assessment, ISO 23894 tells you how.

**Source:** [iso.org](https://www.iso.org/standard/77304.html)

**What it covers:**
- A risk management process for AI specifically, built on ISO 31000 (general risk management) principles
- Guidance on integrating AI risk management into the full AI lifecycle — from design through deployment to decommissioning
- AI-specific risk categories not present in conventional frameworks: algorithmic transparency, fairness and bias, robustness and reliability, human-AI interaction
- Guidance on the dynamic nature of AI risk — AI systems change over time as they encounter new data, and risk assessment must be continuous, not one-time
- Practical guidance on risk identification, analysis, and evaluation for AI contexts

**What it does not cover:**
- A fixed, enumerated list of AI risks — it provides a framework for identifying them, not a catalogue
- Security-specific adversarial threats (see MITRE ATLAS for those)
- Application-layer vulnerabilities in LLM deployments (see OWASP Top 10 LLM)

**How it relates to ISO 42001:**
ISO 42001 Clause 6 (Planning) and Annex A Category 8 (AI System Lifecycle) require risk assessment. ISO 23894 is the methodology standard that operationalises those requirements. They are designed to be used together. If you are implementing ISO 42001 and have not read ISO 23894, your risk assessment process has no methodological foundation specific to AI.

---

### MIT AI Risk Repository

**What it is:** A comprehensive, publicly accessible database of AI risks compiled by researchers at MIT. Updated regularly — as of December 2025, it contains 1,612 unique risk entries drawn from 65 frameworks, papers, and reports.

**Source:** [airisk.mit.edu](https://airisk.mit.edu)

**What it covers:**
The repository provides two complementary taxonomies:

**Domain Taxonomy — 7 domains, 25 subdomains:**

| Domain | Example Subdomains |
|--------|--------------------|
| **Discrimination and toxicity** | Bias and unfairness, hate speech, harmful content generation |
| **Privacy and security** | Personal data exposure, surveillance, data breach |
| **Misinformation** | Hallucinations, disinformation, deepfakes |
| **Malicious actors and misuse** | Cyberattacks enabled by AI, fraud, manipulation |
| **Human-computer interaction** | Over-reliance, automation bias, loss of human skill |
| **Socioeconomic and environmental** | Job displacement, environmental cost, concentration of power |
| **AI system safety, failures, and limitations** | Reward hacking, specification gaming, goal misalignment, distributional shift |

**Causal Taxonomy:** Each risk is classified by who or what causes it (human or AI), whether it is intentional or unintentional, and whether it occurs pre- or post-deployment.

**Why it is useful for practitioners:**
The repository is the best available catalogue of what can go wrong with AI. It is not a standard — it has no requirements language — but it is the most comprehensive reference for risk identification exercises. Using it as a checklist during a risk identification workshop will surface risks that standard risk management training simply does not include.

The December 2025 update added a new subdomain specifically for multi-agent and agentic AI risks, reflecting the rapidly evolving deployment of autonomous AI systems.

---

### MITRE ATLAS — Adversarial Threat Landscape for AI Systems

**What it is:** A knowledge base of adversary tactics, techniques, and procedures (TTPs) targeting AI and machine learning systems. Modelled after MITRE ATT&CK (the widely used cybersecurity threat framework), ATLAS is the equivalent for AI-specific attack paths.

**Source:** [atlas.mitre.org](https://atlas.mitre.org)

**Current version:** v5.3.0 (January 2026) — 16 tactics, 84 techniques, 32 mitigations, 42 case studies

**What it covers:**
ATLAS documents how adversaries attack AI systems — not just the systems that run AI, but the AI components themselves. Key tactic categories include:

- **Reconnaissance** — Gathering information about an AI system's architecture, training data, or model behaviour
- **Resource development** — Acquiring or building tools and infrastructure for AI attacks
- **Initial access** — Getting access to AI systems or their supply chain
- **ML attack staging** — Preparing attacks against ML systems specifically
- **ML model access** — Exploiting access to query AI models
- **Exfiltration via ML inference** — Extracting information from an AI model through its outputs
- **Impact** — Degrading or manipulating AI model behaviour

**Notable techniques for agentic AI (2025-2026 additions):**
- MCP server compromise and indirect prompt injection via MCP channels
- Malicious AI agent deployment
- Cross-agent prompt injection — where a compromised agent injects malicious instructions into another agent's context
- Tool call manipulation — where an adversary manipulates the tool calls an agent makes

**How it relates to ISO 42001:**
ATLAS techniques map to ISO 42001 Annex A Category 8 (AI system lifecycle controls) and directly inform the adversarial risk identification that ISO 23894 requires. An AI system impact assessment that does not consider ATLAS-documented attack techniques is incomplete for any system exposed to external inputs.

---

### OWASP Top 10 for LLM Applications (2025)

**What it is:** A community-developed ranked list of the 10 most critical security vulnerabilities in applications built on large language models. Published by the OWASP GenAI Security Project.

**Source:** [genai.owasp.org](https://genai.owasp.org/llm-top-10/)

**What it covers — the 2025 list:**

| # | Risk | What It Is |
|---|------|-----------|
| **LLM01** | Prompt Injection | Attackers manipulate LLM behaviour by embedding malicious instructions in inputs — either directly (jailbreaking) or indirectly (via content the LLM processes, such as documents, emails, or web pages) |
| **LLM02** | Sensitive Information Disclosure | LLMs inadvertently expose personal data, credentials, proprietary information, or training data through their outputs |
| **LLM03** | Supply Chain Vulnerabilities | Risks from third-party models, datasets, plugins, or fine-tuning sources that introduce vulnerabilities or biases |
| **LLM04** | Data and Model Poisoning | Manipulation of training data or fine-tuning inputs to alter model behaviour in ways that benefit an attacker |
| **LLM05** | Improper Output Handling | Failing to validate or sanitise LLM outputs before passing them to downstream systems — enabling prompt injection to cascade into code execution, SQL injection, or other attacks |
| **LLM06** | Excessive Agency | Giving an LLM agent too much authority, too many permissions, or too little human oversight — enabling it to take damaging actions when manipulated or behaving unexpectedly |
| **LLM07** | System Prompt Leakage | LLM reveals the contents of its system prompt, exposing business logic, security controls, or sensitive configuration |
| **LLM08** | Vector and Embedding Weaknesses | Vulnerabilities in how retrieval-augmented generation (RAG) systems store and retrieve content — enabling data poisoning or cross-user data leakage |
| **LLM09** | Misinformation | LLM generates confidently stated but factually incorrect outputs (hallucinations) — framed as a security risk, not just a quality issue, because misinformation in high-stakes decisions has direct harm potential |
| **LLM10** | Unbounded Consumption | Denial-of-service and "Denial of Wallet" attacks that exhaust compute resources or drive up costs through excessive inference requests or poorly designed reasoning loops |

**Why it is useful for practitioners:**
OWASP Top 10 LLM is the most practically actionable framework for teams deploying AI applications. Unlike ISO standards, it is specific about what the vulnerability is, how it is exploited, and what mitigations exist. It is the right starting point for application security risk identification on any system using LLMs or agentic AI.

**LLM06 (Excessive Agency) is particularly important** for agentic AI governance. It directly addresses the risk of AI agents with too much authority, too many permissions, or inadequate human oversight — and maps precisely to the financial governance pattern described in the ISO 42001 financial AI section of this repository.

---

### NIST AI RMF — MAP Function

**What it is:** The MAP function of the NIST AI Risk Management Framework focuses specifically on AI risk identification and categorisation.

**Source:** [nist.gov/artificial-intelligence](https://www.nist.gov/artificial-intelligence)

**What it covers:**
The MAP function provides structured practices for:
- Categorising AI systems by risk level (MAP 1 — context)
- Identifying affected communities and potential harms (MAP 2)
- Understanding AI system failure modes and their likelihood (MAP 3)
- Evaluating risks across the AI lifecycle (MAP 4)
- Reviewing and updating risk assessments as the system or context changes (MAP 5)

The accompanying NIST AI RMF Playbook provides more granular sub-practices for each MAP category, including specific questions to ask about bias, robustness, data quality, and human oversight.

**How it relates to ISO 42001:**
Where ISO 42001 requires risk assessment (Clause 6), the NIST AI RMF MAP function is the most detailed publicly available methodology for conducting one. Many organisations use NIST MAP practices as the operational content of their ISO 42001 risk assessment process.

---

### ENISA AI Threat Landscape

**What it is:** The European Union Agency for Cybersecurity's annual threat landscape analysis includes AI-specific threats — both threats TO AI systems and threats ENABLED BY AI.

**Source:** [enisa.europa.eu](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2025)

**What it covers (2025 report):**
- AI-enabled phishing and social engineering at scale (>80% of phishing emails in 2025 involved AI)
- Malicious AI tools (WormGPT, FraudGPT, Xanthorox AI) enabling adversaries without ML expertise
- Training data poisoning via compromised model hosting platforms
- "Rules File Backdoor" — injecting malicious instructions into AI coding assistants
- Deepfakes and synthetic media for identity fraud and disinformation

**Why it is useful:**
ENISA provides the European regulatory and threat intelligence context. For organisations subject to the EU AI Act, understanding the EU-specific threat landscape is directly relevant to risk assessment.

---

## AI Risk Taxonomy for Practitioners

What follows is a synthesised taxonomy drawing across the frameworks above, written for practitioners who need to identify and assess AI risks without specialist ML knowledge. For each category: what the risk is, why it is specific to AI, examples of failure, and what treatment options exist.

---

### 1. Model Performance Risks

**What it is:** The risk that an AI model fails to produce accurate, reliable, or appropriate outputs under real-world conditions.

**Why it is specific to AI:** Traditional software either works or does not. AI models work probabilistically — they can be accurate on average while failing systematically for specific inputs, populations, or scenarios.

**Specific risks:**
- **Accuracy degradation:** The model produces incorrect outputs at a rate that causes harm or poor decisions
- **Distributional shift / model drift:** The real-world data the model encounters changes over time, and the model's performance degrades because it was trained on data that no longer reflects current reality
- **Edge case failure:** The model works well on common inputs but fails on rare but important ones
- **Confidence miscalibration:** The model expresses high confidence in incorrect outputs — making it harder for humans to detect errors

**Examples:** A fraud detection model trained on pre-2024 fraud patterns fails to detect a new fraud technique. A credit scoring model degrades after a macroeconomic shift changes the relationship between input features and creditworthiness.

**Treatment options:**
- Establish acceptance criteria (accuracy, precision, recall thresholds) before deployment and test against them
- Implement production monitoring to detect performance degradation
- Set up drift detection that triggers re-evaluation when input distributions change
- Require human review for outputs in tail distributions or near decision boundaries
- Version and archive models so rollback is possible

---

### 2. Data Risks

**What it is:** Risks arising from the data used to train, validate, and operate AI systems.

**Why it is specific to AI:** AI systems inherit the characteristics of their training data. Garbage in, garbage out — but with AI, the garbage can be subtle and systematic rather than obvious.

**Specific risks:**
- **Training data bias:** Systematic errors or imbalances in training data that cause the model to produce biased outputs for certain groups, scenarios, or inputs
- **Data poisoning:** Deliberate manipulation of training data to cause a model to learn incorrect patterns or exhibit adversary-specified behaviour
- **Data provenance gaps:** Using training data whose origin, collection method, or licensing is unclear — creating legal, ethical, or quality risks
- **Personal data in training:** Using personal information to train models without appropriate lawful basis, creating Privacy Act / GDPR exposure
- **Data quality degradation:** The data feeding a live AI system degrades in quality over time, causing performance to deteriorate without an obvious trigger

**Examples:** A hiring AI trained on historical hiring decisions learns that certain universities predict success because the historical hires were demographically skewed, not because university matters. A model trained on scraped web data inherits the biases of internet content.

**Treatment options:**
- Maintain data provenance records covering origin, collection method, and processing history
- Conduct bias assessments on training data before model training
- Implement data quality monitoring in production data pipelines
- Establish data minimisation practices — do not include personal data in training unless necessary and lawful
- Red-team training data for poisoning vectors before fine-tuning on external datasets

---

### 3. Adversarial and Security Risks

**What it is:** Risks from deliberate attempts to manipulate, exploit, or attack AI systems.

**Why it is specific to AI:** Traditional application security assumes the application logic is fixed. AI systems can be manipulated through their inputs in ways that would not work on traditional software — because the AI interprets rather than processes inputs.

**Specific risks:**
- **Prompt injection (direct):** An attacker crafts inputs that override or circumvent the AI's intended behaviour — effectively hijacking the model's instructions
- **Prompt injection (indirect):** Content the AI processes (documents, emails, web pages) contains embedded instructions that redirect the AI's behaviour — a particular risk for agentic AI that reads and acts on external content
- **Model extraction:** An attacker queries an AI model systematically to reconstruct a copy of its weights or behaviour — stealing proprietary model capability
- **Membership inference:** An attacker determines whether specific data was used to train a model — relevant when training data includes personal or sensitive information
- **Adversarial inputs:** Inputs specifically crafted to cause the model to misclassify or produce incorrect outputs — particularly relevant for vision and classification models
- **Jailbreaking:** Techniques that cause a model to bypass its safety constraints and produce outputs it is designed to refuse

**Examples:** An AI agent processing customer emails is manipulated by a specially crafted email that instructs it to forward sensitive data to an attacker. A competitor systematically queries a proprietary model API to reconstruct the model's behaviour.

**Treatment options:**
- Implement input validation and content filtering before inputs reach the model
- Apply output validation and sanitisation before outputs are passed to downstream systems
- Separate the model's instruction context from user-controlled input context (system prompt isolation)
- Implement rate limiting and anomaly detection on inference endpoints (ISM December 2025 controls)
- Apply least-privilege access controls: AI agents should have access only to the tools and data they need for the current task
- Conduct red team exercises using MITRE ATLAS techniques relevant to your deployment

---

### 4. Human-AI Interaction Risks

**What it is:** Risks arising from how humans interact with, rely on, and respond to AI systems — including both over-reliance and under-reliance.

**Why it is specific to AI:** AI systems can appear more authoritative than they are — fluent, confident, comprehensive — which causes humans to defer to them in ways they would not defer to a spreadsheet or a junior colleague.

**Specific risks:**
- **Automation bias:** Humans systematically defer to AI recommendations even when they have relevant information that should override the AI's output
- **Over-reliance:** Users trust AI outputs without verification — causing errors to propagate into decisions without human correction
- **Under-reliance:** Users distrust AI outputs and do not benefit from AI capability — wasted investment and missed efficiency
- **Skill erosion:** Humans who rely on AI for tasks gradually lose the ability to perform those tasks independently — becoming unable to detect AI errors or operate without the AI
- **Inappropriate use:** Users apply an AI system to tasks it was not designed for, producing outputs that appear credible but are unreliable

**Examples:** A radiologist reviews AI-flagged scans more carefully than un-flagged scans, causing them to miss findings the AI did not flag. A lawyer relies on an LLM's legal citations without verification, submitting fabricated case references to court.

**Treatment options:**
- Design AI interfaces that communicate uncertainty, not just outputs
- Make human review steps explicit and mandatory for high-stakes decisions — do not make AI outputs the default "answer" that requires effort to override
- Train users on the limitations of the AI systems they use, not just how to use them
- Audit human override rates — if humans are not overriding AI outputs, investigate whether meaningful review is occurring or whether automation bias has set in
- Maintain human capability in critical areas by requiring regular manual operation

---

### 5. Fairness and Discrimination Risks

**What it is:** Risks that AI systems produce outputs that are systematically unfair to specific groups — based on protected attributes such as age, gender, race, or disability.

**Why it is specific to AI:** AI systems can learn and amplify discrimination from historical data without any discriminatory intent. The discrimination can be invisible to developers and users and can persist undetected through testing if testing does not specifically look for it.

**Specific risks:**
- **Disparate impact:** The AI produces materially worse outcomes for one group than another, even without using protected attributes as inputs — because the model has learned correlations between protected attributes and other features
- **Proxy discrimination:** The AI does not use a protected attribute directly but uses a proxy (postcode, purchasing behaviour, name) that correlates with the attribute
- **Intersectional discrimination:** The AI disadvantages people at the intersection of multiple characteristics in ways that are not visible when testing each characteristic independently

**Examples:** A loan approval AI denies applications from postcodes with high minority populations at higher rates, not because of race but because postcode correlates with race in the training data. A hiring AI rates CVs from women-only colleges lower because historical successful hires were predominantly from co-educational universities.

**Treatment options:**
- Conduct fairness testing across relevant protected characteristics before deployment — use both statistical parity and equal opportunity metrics
- Audit for proxy discrimination — test whether inputs correlated with protected attributes are driving disparate outcomes
- Establish a process for affected individuals to raise concerns and receive a human review of AI-influenced decisions
- Monitor fairness metrics in production, not just pre-deployment
- Document the fairness testing approach and results in the AI system record

---

### 6. Transparency and Explainability Risks

**What it is:** Risks arising from the inability to explain or understand why an AI system produced a specific output.

**Why it is specific to AI:** Traditional software decisions can be traced through code. AI decisions in complex models cannot be simply explained — which creates accountability gaps, impairs error correction, and may violate regulatory requirements.

**Specific risks:**
- **Unexplainable high-stakes decisions:** An AI-influenced decision (credit denial, insurance pricing, medical recommendation) cannot be explained to the affected individual or a regulator
- **Audit failure:** A post-incident investigation cannot determine why the AI system behaved as it did
- **Regulatory non-compliance:** Applicable law or regulation (consumer credit law, EU AI Act, sector-specific rules) requires explanation of automated decisions, and the AI system cannot provide one
- **Hidden complexity:** The full range of AI system behaviour is not visible to the organisation operating it — meaning risks and failure modes may be unidentified

**Examples:** A bank cannot explain to a customer or regulator why their loan application was declined by an AI system. A post-incident review of an autonomous agent's behaviour cannot reconstruct its decision chain.

**Treatment options:**
- Select model architectures appropriate to the explainability requirements of the use case — interpretable models where explanation is required
- Implement explainability tooling (SHAP, LIME, attention visualisation) where black-box models are used
- Log the full context of AI decisions — inputs, outputs, model version, timestamp — for audit purposes
- Design human approval workflows that require the approver to record their reasoning — creating an explanatory record even if the AI cannot provide one
- Document system cards for each AI system covering model type, training data, known limitations, and performance characteristics

---

### 7. Operational and Agentic Risks

**What it is:** Risks from how AI systems behave when deployed in production — particularly for AI agents that take actions autonomously.

**Why it is specific to AI:** AI systems can behave in unexpected ways under operational conditions. Agentic AI that takes real-world actions amplifies operational risk because errors are no longer just wrong outputs — they are wrong actions, some of which are irreversible.

**Specific risks:**
- **Scope creep:** An AI agent takes actions outside its intended scope, because its authority is defined in instructions rather than enforced at the infrastructure layer
- **Compounding errors:** Agentic AI chains multiple steps — an error early in the chain can cascade and amplify through subsequent actions
- **Irreversible actions:** An AI agent takes an action that cannot be undone — sending a communication, making a purchase, deleting data, committing to a contract
- **Blast radius:** A compromised or malfunctioning AI agent causes damage proportional to the access and authority it has been granted
- **Cumulative spend:** An AI agent with financial authority that operates within its per-transaction cap can exceed acceptable total spend through volume

**Examples:** An AI procurement agent, given access to a payment API, makes purchases its policy was designed to prevent because the policy was expressed in a system prompt rather than enforced by a rules engine. A coding agent with read-write access to a production database deletes data while attempting to perform a maintenance task.

**Treatment options:**
- Enforce scope at the infrastructure layer, not the prompt layer — spending caps, category controls, access permissions must be implemented as code
- Apply least-privilege access to all AI agents — agents should have the minimum access required for their current task, not broad access "just in case"
- Design for reversibility — prefer actions that can be reviewed before being committed, and flag irreversible actions for human approval
- Implement a financial control layer for agents with payment access — deterministic rules engine, human approval loop, immutable audit log
- Set cumulative spend trackers in addition to per-transaction caps — monthly or rolling spend limits enforced at the infrastructure layer

---

### 8. Supply Chain Risks

**What it is:** Risks arising from third-party AI components — foundation models, APIs, datasets, plugins, and services — that an organisation uses rather than builds.

**Why it is specific to AI:** Most organisations deploying AI are not building models from scratch — they are assembling AI capabilities from external sources. The governance of those external sources is not well-established, and the failure of a component is not always detectable until it manifests in a production failure.

**Specific risks:**
- **Model provider risk:** The third-party model you depend on changes its behaviour (through a model update), terminates access, or introduces undesirable capabilities
- **Training data provenance:** A third-party model was trained on data with legal, ethical, or quality problems you are now inheriting
- **Plugin and tool risk:** Plugins, tools, or APIs connected to an AI agent introduce vulnerabilities, change without notice, or behave maliciously
- **Embedding and RAG poisoning:** A retrieval-augmented generation system's knowledge base is poisoned — causing the AI to produce outputs based on adversarially modified content

**Examples:** A foundation model provider updates its model, changing its behaviour in ways that break downstream applications or introduce new outputs. A plugin connected to an LLM agent is compromised and begins exfiltrating data through the agent's tool calls.

**Treatment options:**
- Maintain an inventory of all AI components, including their provenance, version, and governance status (see AI System Inventory Template)
- Pin model versions in production — do not allow automatic model updates without testing
- Review third-party AI components against the same criteria you would apply to your own models: training data, bias testing, known limitations
- Include AI-specific requirements in supplier contracts: incident notification, change notification, audit rights (see DTA AI Procurement Guidance)
- Test third-party model updates before deploying them into production workflows

---

## Treatment Options — Quick Reference

The following summarises available treatment options by risk category. Treatment options are not mutually exclusive — effective risk treatment typically combines technical, process, and governance controls.

| Risk Category | Technical Controls | Process Controls | Governance Controls |
|--------------|-------------------|-----------------|-------------------|
| **Model Performance** | Monitoring, drift detection, rollback capability | Scheduled re-evaluation, human review triggers | Performance acceptance criteria, SLAs |
| **Data** | Data quality tooling, provenance tracking, de-identification | Data governance processes, bias audits | Data governance policy, lawful basis documentation |
| **Adversarial / Security** | Input validation, output filtering, rate limiting, scope enforcement | Red team exercises, penetration testing | Security requirements in design, MITRE ATLAS threat modelling |
| **Human-AI Interaction** | Uncertainty communication in UI, mandatory review workflows | User training, override rate monitoring | Automation bias awareness policy, responsible use guidelines |
| **Fairness** | Fairness testing tooling, bias metrics in monitoring | Pre-deployment fairness audit, ongoing disparity monitoring | Fairness policy, affected party redress process |
| **Transparency** | Explainability tooling, decision logging | Human reasoning capture in approval workflows | Explainability requirements by risk class, system cards |
| **Operational / Agentic** | Infrastructure-layer scope enforcement, least-privilege access, reversibility design | Human approval for irreversible actions, cumulative monitoring | Agent authority policy, blast radius assessment |
| **Supply Chain** | Version pinning, pre-deployment update testing | Supplier assessment process, change notification | AI supplier contracts, component inventory |

---

## Further Reading

| Resource | What It Contributes | Access |
|----------|---------------------|--------|
| ISO/IEC 23894:2023 | AI risk management methodology (the how) | [iso.org](https://www.iso.org/standard/77304.html) — paid |
| MIT AI Risk Repository | Comprehensive risk catalogue (the what) | [airisk.mit.edu](https://airisk.mit.edu) — free |
| MITRE ATLAS | Adversarial AI threat taxonomy (the who and how of attacks) | [atlas.mitre.org](https://atlas.mitre.org) — free |
| OWASP Top 10 LLM 2025 | Application-layer LLM security risks and mitigations | [genai.owasp.org](https://genai.owasp.org/llm-top-10/) — free |
| NIST AI RMF Playbook | Risk identification practices (MAP function) | [nist.gov](https://www.nist.gov/artificial-intelligence) — free |
| ENISA Threat Landscape 2025 | EU threat context including AI-specific threats | [enisa.europa.eu](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2025) — free |

---

*Last reviewed: April 2026*
