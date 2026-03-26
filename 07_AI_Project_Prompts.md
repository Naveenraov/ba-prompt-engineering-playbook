# 07 — AI Project Prompts

*The section that separates AI BAs from regular BAs.*

---

## Why This Section Matters

Every BA will work on an AI project in 2026. Most won't know what to do with it.

Functional requirements for a CRM are familiar territory. But requirements for an AI model? Ethics checklists? Human-in-the-loop governance? UAT that tests for bias? That's new — and it's where the real opportunity is.

These 7 prompts cover the full AI project lifecycle from a BA's perspective.

> **Remember:** AI produces output. BAs decide whether that output is safe, accurate, explainable, and aligned to the business. Nobody else in the team owns that.

---

## Prompt 1 — AI Use Case Feasibility Assessment

**Use when:** Deciding whether AI is actually the right solution before the business commits.

```
CONTEXT: A [org type] is considering AI for [business problem]. 
Current process: [describe as-is — steps, tools, people involved]. 
Data available: [types, rough volume, quality level — clean / messy / incomplete]. 
Constraints: [budget / timeline / GDPR / technical stack]. 
Stakeholders: [names/roles and their main concerns].

ROLE: Act as an AI Business Analyst with feasibility assessment experience.

ACTION: Produce a structured feasibility assessment covering:
1. Problem-Solution Fit — is AI the right tool, or would a simpler solution work?
2. Data Readiness — is the data available, sufficient, and clean enough?
3. Technical Feasibility — integration complexity, infrastructure requirements
4. Business Case — expected benefits (quantified), effort estimate, rough ROI
5. Risk Assessment — 6 risks across: technical, operational, ethical, and regulatory
6. Go/No-Go Recommendation — one clear paragraph with rationale

FORMAT: Sections with bold headers. Risk assessment as a table: 
Risk | Category | Likelihood (H/M/L) | Impact (H/M/L) | Mitigation
End with a 3-sentence Executive Summary for a CTO briefing.

TONE: Direct and balanced. Don't oversell AI. Flag real risks clearly.
```

**When to use this in practice:**
> ✅ Retail: "Should we use AI for demand forecasting or is better ERP config enough?"  
> ✅ Telecom: "Is an AI chatbot the right answer, or do we need better IVR first?"  
> ✅ Logistics: "Route optimisation AI — or just hire one more dispatcher?"  
> ✅ Enterprise IT: "Automated invoice matching AI — or fix the master data first?"

---

## Prompt 2 — AI System Requirements Specification

**Use when:** Writing formal requirements for a system that includes AI/ML components.

```
CONTEXT: Specifying requirements for an AI-powered [system name] at [org type]. 
The AI will [describe function — predict / classify / recommend / automate]. 
Input data: [types]. Output: [what AI produces]. 
End users: [who uses the output]. Regulatory context: [GDPR / EU AI Act / sector].

ROLE: Act as an AI BA experienced in writing requirements for ML systems.

ACTION: Produce a requirements spec covering:
1. Functional Requirements for the AI component (8 requirements)
2. Model Performance Requirements — accuracy, precision, recall thresholds
3. Explainability Requirements — can users understand why the AI decided what it did?
4. Data Requirements — input specification, quality standards, refresh frequency
5. Human-in-the-Loop requirements — when must a human review or override AI output?
6. Non-Functional Requirements — fairness, security, auditability

FORMAT: Numbered requirements with IDs (AI-FR-001 etc.).
Include a HITL decision table: Scenario | AI Confidence Threshold | 
Human Action Required | Override Available?

TONE: Precise. Readable by both business stakeholders and the data science team.
```

**Enterprise IT example — AI invoice matching system:**

> **AI-FR-004:** The system shall flag any invoice where the AI confidence score falls below 85% for mandatory human review before payment approval.  
> **AI-NFR-002:** The AI model shall log the top 3 decision factors for every invoice match/rejection decision, accessible to the Finance Manager via audit trail.

---

## Prompt 3 — AI Risk & Ethics Checklist

**Use when:** Governance sign-off before any AI system goes live.

```
CONTEXT: Our org is implementing [AI system] for [use case]. 
It will [what it does + who is affected]. 
Regulatory context: [GDPR / EU AI Act risk tier / sector-specific].
Data used: [types — personal data, historical data, sensitive categories].

ROLE: Act as an AI Governance specialist and Business Analyst.

ACTION: Produce a risk and ethics checklist covering:
1. Data Bias & Fairness — is training data representative of all affected groups?
2. Privacy & GDPR — data minimisation, consent, right to explanation
3. EU AI Act Classification — what risk tier? What obligations follow?
4. Explainability — can decisions be explained to affected people in plain English?
5. Human Oversight — escalation paths, override mechanisms, who is accountable?
6. Security Risks — prompt injection, model poisoning, adversarial inputs
7. Operational Risks — model drift, retraining schedule, monitoring plan
8. Accountability — who owns AI decisions? What does the audit trail capture?

FORMAT: Checklist table — Risk Area | Specific Risk | 
Status (✅ Addressed / ⚠️ Partial / ❌ Not Addressed) | Owner | Notes

TONE: Rigorous. This is a compliance document, not a tick-box exercise.
```

---

## Prompt 4 — Human-in-the-Loop (HITL) Design

**Use when:** Designing when AI decides vs. when a human must be involved.

```
CONTEXT: We are deploying an AI system that can [describe autonomous actions — 
e.g. approve supplier invoices, generate customer communications, flag delivery anomalies]. 
Domain: [Retail / Telecom / Logistics / Enterprise IT]. 
Risk tolerance: [low — regulated environment / medium — operational decisions].

ROLE: Act as an AI BA specialising in human-AI collaboration design.

ACTION: Design a HITL framework covering:
1. Decision Classification Matrix — fully automated vs. requires human review vs. 
   requires human approval before action
2. Escalation Triggers — specific conditions that force human intervention
3. Override Protocol — how a human overrides an AI decision + what gets logged
4. Audit Trail Requirements — every field that must be captured per AI action
5. Performance Monitoring — KPIs to detect model underperformance before it causes harm

FORMAT:
- Decision Matrix: Decision Type | AI Confidence Threshold | Human Action | Timeframe
- Escalation Triggers: numbered list with one-line rationale each
- Audit Fields: table of fields, data type, retention period

TONE: Structured. This goes to the risk committee or compliance team.
```

**Logistics example — Route Optimisation AI:**

> | Decision | Confidence Threshold | Human Action | Timeframe |
> |----------|---------------------|-------------|-----------|
> | Standard route assignment | ≥ 90% | None — auto-assigned | Immediate |
> | Route with restricted access | ≥ 75% | Dispatcher review | Within 30 min |
> | New customer delivery | Any | Dispatcher confirms | Before despatch |
> | Weather disruption reroute | < 70% | Supervisor approval | Within 15 min |

---

## Prompt 5 — UAT Planning for AI Systems

**Use when:** Planning user acceptance testing where the system includes an AI component.

```
CONTEXT: Planning UAT for [AI system name]. Function: [what it does]. 
Key user groups: [list]. Known risks: [e.g. bias, low confidence scores, edge cases]. 
Integration points: [other systems].

ROLE: Act as a BA with UAT planning experience for AI-driven systems.

ACTION: Produce a UAT plan addressing AI-specific testing challenges:
1. Test scope — what is in/out of UAT for the AI component
2. 10 test scenarios — include: normal use, edge cases, adversarial inputs, 
   model failure scenarios, and at least 2 bias detection scenarios
3. AI acceptance criteria — how do we define "good enough" model performance?
4. User feedback protocol — how UAT participants flag concerns about AI behaviour
5. Entry and exit criteria for UAT sign-off

FORMAT: Formal UAT plan. Scenarios as a table: 
Scenario ID | Description | Input | Expected Output | 
Actual Output (blank) | Pass/Fail | Notes

TONE: Rigorous. QA Lead or Project Manager will sign this off.
```

---

## Prompt 6 — AI Tool Evaluation Matrix

**Use when:** Helping the business choose between AI tools or platforms.

```
CONTEXT: Our [org type] is evaluating [number] AI tools for [use case — 
e.g. internal productivity / customer service automation / data analysis]. 
Tools: [list them]. Key concerns: [data privacy / GDPR / existing stack integration / 
cost / ease of use for non-technical staff / EU AI Act compliance].

ROLE: Act as an AI BA conducting a vendor evaluation.

ACTION: Build an evaluation framework with 8 criteria + scoring guidance, 
then apply it to the tools listed. Criteria must include: 
GDPR & Data Privacy, EU AI Act Compliance, Integration Capability, 
Ease of Use, Cost Model, Performance on Use Case, Explainability, Vendor Support & SLA.

FORMAT:
- Criteria table: Criterion | Description | Weight (%) | Scoring Guide (1–5)
- Scoring matrix: Tools as columns, Criteria as rows, 
  weighted scores, total, recommendation

TONE: Objective and analytical. Goes to a technology steering committee.
```

**Use case across domains:**
> - Enterprise IT: Microsoft Copilot vs Google Gemini for internal BA productivity  
> - Retail: AI demand forecasting vendors (e.g. Blue Yonder vs Relex vs o9)  
> - Telecom: AI chatbot platforms (e.g. Salesforce Einstein vs AWS Lex vs Google CCAI)  
> - Logistics: Route optimisation tools (e.g. OptimoRoute vs Circuit vs proprietary AI)

---

## Prompt 7 — AI Project Lessons Learned

**Use when:** Post-implementation review of any AI project.

```
CONTEXT: We completed [AI project name] — [description] — over [duration]. 
Result: [achieved / partially achieved / missed objectives]. 
Key challenges: [list]. Key wins: [list].

ROLE: Act as a BA facilitating a post-implementation review for an AI project.

ACTION: Structure a lessons learned document covering:
1. Planned vs. actual (requirements accuracy, timeline, budget)
2. AI-specific lessons — data quality issues, model performance vs. expectations, 
   stakeholder acceptance of AI output
3. BA process lessons — what worked in requirements, what didn't
4. Governance lessons — what HITL and ethics review processes worked in practice
5. Top 5 recommendations for future AI projects (specific and actionable)

FORMAT: Document with bold section headers. 
Recommendations as a table: Recommendation | Rationale | Owner | Priority

TONE: Honest and constructive. Internal knowledge base article — not a PR document.
```

---

## AI Prompt Quick Reference

| # | Prompt | Use It When |
|---|--------|------------|
| 1 | Feasibility Assessment | Evaluating whether to build an AI solution |
| 2 | AI Requirements Spec | Writing reqs for ML/AI components |
| 3 | Risk & Ethics Checklist | Governance sign-off before go-live |
| 4 | HITL Design | Deciding when AI decides vs. human decides |
| 5 | AI UAT Plan | Planning testing for AI-driven systems |
| 6 | Tool Evaluation Matrix | Comparing AI platforms or vendors |
| 7 | Lessons Learned | Post-implementation AI retrospective |

---

> *"In 2026, every BA will work on at least one AI project. The ones who stand out are those who can govern it — not just document it."*

---

> *Next: [08 — Domain Prompts](./08_Domain_Prompts.md)*
