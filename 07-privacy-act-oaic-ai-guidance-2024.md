# OAIC AI Privacy Guidance

**Publisher:** Office of the Australian Information Commissioner (OAIC)
**Published:** 21 October 2024 (two documents published simultaneously)
**Last Updated:** October 2024
**Status:** Current
**Applies to:** All APP entities — organisations and agencies with obligations under the Privacy Act 1988 that develop, use, or procure AI systems involving personal information
**Sources:**
- [Guidance on privacy and the use of commercially available AI products](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products)
- [Guidance on privacy and developing and training generative AI models](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-developing-and-training-generative-ai-models)

---

## What This Is

On 21 October 2024, the OAIC published two complementary pieces of guidance on AI and privacy — the first substantive guidance from Australia's privacy regulator on the intersection of AI and the Privacy Act 1988 (Cth).

The two documents address different organisational roles:

**Document 1 — Using commercially available AI products:** For organisations that purchase or use AI tools (chatbots, content generation tools, productivity assistants, classification engines) that involve personal information. This is the most broadly applicable document — it applies to any organisation using a commercial AI API or product with personal data.

**Document 2 — Developing and training generative AI models:** For organisations that are developing, training, or fine-tuning their own AI models using personal information as training data. Narrower in application but higher-stakes in obligation.

Both documents apply the existing Australian Privacy Principles (APPs) to AI contexts — they do not create new law. They clarify how existing obligations apply.

---

## Key Principle: Personal Information Is Broader Than You Think

The OAIC's guidance establishes that for the purposes of the Privacy Act, personal information in AI contexts includes:

- **Inputs to AI systems** that contain or reference personal information (queries, documents, audio, images)
- **Outputs from AI systems** that contain personal information about identified or reasonably identifiable individuals
- **Inferred information** — conclusions an AI draws about an individual, even if not explicitly provided
- **Hallucinated information** — false information an AI generates about a real, identifiable person is still "personal information" for the purposes of the Privacy Act if it relates to an identified individual

This last point has significant implications. If an AI system produces false statements about a real person, the organisation responsible for that system may have Privacy Act obligations in relation to those outputs.

---

## Document 1: Using Commercially Available AI Products

### Who This Applies To
Any APP entity (organisation or government agency) that uses a commercial AI product or API that processes personal information. This includes:
- Using ChatGPT, Claude, Gemini, Copilot, or similar tools in a business context with customer or employee data
- Using AI-powered SaaS products (HR platforms, CRM tools, document management systems with AI features)
- Connecting internal data to third-party AI APIs via integrations

### Core Obligations

**Before selecting an AI product:**
- Conduct a privacy impact assessment or due diligence on the AI product's data handling practices
- Understand how the vendor uses input data — does it use your data to train its models?
- Confirm the vendor's data storage, security, and deletion practices
- Assess whether the use of personal information is within the purpose for which it was collected (APP 6)

**When using the AI product:**
- Do not input more personal information than is necessary for the purpose (APP 3 — collection minimisation)
- Ensure users and affected individuals are aware that AI is processing their information — update privacy notices and collection statements
- Implement controls to prevent staff inputting sensitive categories of information (health, financial, identity documents) into AI tools without appropriate authorisation and safeguards

**Ongoing:**
- Monitor how the AI tool uses and stores data — vendor policies change
- Review privacy notices regularly to ensure they accurately describe AI data processing
- Have a process for handling access, correction, and complaints related to AI-processed personal information

### Key Risks Identified
- Bias and discrimination in AI outputs based on protected attributes
- Data breach risk from data shared with third-party AI vendors
- Loss of individual control over personal information
- Re-identification of de-identified data through AI inference
- Scope creep — AI tools learning from inputs in ways not anticipated at procurement

---

## Document 2: Developing and Training Generative AI Models

### Who This Applies To
Organisations that:
- Build or fine-tune their own AI models using personal information
- Scrape or aggregate personal data from public sources for training
- Use customer or employee data to train or improve AI systems

### Core Obligations

**Before training:**
- Confirm the legal basis for using personal information as training data — was it collected for this purpose? (APP 3 and APP 6)
- For data scraped from public sources: the fact that information is publicly available does not make it collected lawfully for AI training purposes
- Conduct a privacy impact assessment covering: what data, from whom, how it will be used, and what the risks are

**Data quality and minimisation:**
- Only use personal information that is necessary and proportionate for the training objective (APP 3)
- Ensure training data is accurate and up to date (APP 10)
- Implement data minimisation techniques — de-identification, synthetic data, differential privacy — where practicable

**Transparency:**
- Update privacy policies to disclose that personal information is used in AI training
- Where practicable, provide individuals with the ability to opt out of their information being used for AI training

**Ongoing:**
- Audit trained models for privacy risks — including the risk that the model memorises and can reproduce training data
- Have processes to respond to access and correction requests in relation to model training data
- Review and update training data practices as the model is updated or retrained

### The OAIC's Recommended Approach: Privacy by Design
The OAIC explicitly recommends a **privacy-by-design** approach to the AI lifecycle — meaning privacy considerations are built into the design of AI systems from the start, not added as a compliance check at the end. This aligns directly with ISO 42001's Annex A 8.2 (Data for AI Systems) and the broader risk-based lifecycle approach.

---

## How It Maps to ISO 42001

| OAIC Guidance Area | ISO 42001 Mapping |
|-------------------|-------------------|
| Privacy impact assessment / due diligence | Clause 8.2 (AI System Impact Assessment), Annex A 8.2 |
| Data minimisation and purpose limitation | Annex A 8.2 (Data for AI Systems) |
| Transparency and collection notices | Annex A 5.1, Clause 7.4 (Communication) |
| Supplier / vendor privacy due diligence | Annex A 11.1–11.4 (Suppliers) |
| Ongoing monitoring and audit | Clause 9.1–9.2 (Monitoring, Internal Audit) |
| Correction and access rights | Annex A 9.3 (Monitoring by affected parties) |

ISO 42001 does not replace Privacy Act compliance — they operate in parallel. ISO 42001 provides the management system that ensures privacy obligations are consistently identified, assessed, and controlled as part of AI governance. The OAIC guidance specifies what those obligations are.

---

## Practitioner Notes

**The hallucination point is significant for liability.** If your AI system produces false statements about a real person, the OAIC's view is that privacy obligations may apply. This has implications for customer-facing generative AI, AI-generated reports involving individuals, and any AI system producing content about identifiable people.

**"Publicly available" is not a free pass for training data.** If you are building or fine-tuning models using scraped web data, social media, or other public sources, the OAIC's guidance is clear that public availability does not establish a lawful basis for use as training data under Australian privacy law.

**Update your privacy notices.** Most privacy notices were written before AI was a meaningful operational tool. If your organisation uses AI products that process personal information, your collection notices and external privacy policies almost certainly need updating to accurately describe that processing.

**Watch for Privacy Act reform.** Privacy Act reforms were progressing through 2025–2026. The OAIC's AI guidance was issued under the current Act — reforms may strengthen some of these obligations, particularly around automated decision-making and the rights of individuals to seek human review of AI decisions.

---

*Last reviewed: April 2026*
*Sources: [OAIC — Using commercially available AI products](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products) | [OAIC — Developing and training generative AI models](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-developing-and-training-generative-ai-models)*
