# 03 — Requirements Prompts

*8 prompts. BRD to RTM. Elicitation to acceptance criteria.*

---

## How to Use This Section

Pick your task. Copy the template. Fill in the CRAFT elements for your project. Get a usable output in minutes, not hours.

> **Non-negotiable:** AI output is a first draft. You validate it against your domain knowledge before it goes anywhere near a stakeholder.

---

## Prompt 1 — Elicitation Interview Questions

**Use when:** Preparing for a stakeholder interview or requirements workshop.

```
CONTEXT: I'm a BA preparing to interview a [job title] at a [company type — 
e.g. mid-size retail chain / telecom operator / logistics firm]. 
Project: [name or type]. Business goal: [1-2 sentences].

ROLE: Act as an experienced BA specialising in [domain] requirements elicitation.

ACTION: Generate 12 open-ended interview questions to uncover:
(1) current pain points and workarounds
(2) desired future state
(3) data and system dependencies
(4) success criteria
(5) risks and constraints
Group by theme. Add a one-line note on why each question matters.

FORMAT: Numbered list under 5 theme headings. Note in italics under each question.

TONE: Conversational but professional. Questions a real BA would actually ask.
```

**Quick example — Retail (Demand Forecasting project):**

> *Theme: Current Pain Points*  
> **Q3:** "Walk me through how your team handles a stockout today — what's the manual workaround?"  
> *Why: Surfaces the hidden process steps that never make it into system documentation.*

---

## Prompt 2 — BRD Drafting

**Use when:** Starting a Business Requirements Document from scratch.

```
CONTEXT: I'm writing a BRD for [project name]. Organisation: [type + size]. 
Goal: [primary objective]. Key stakeholders: [list]. 
Integrates with: [existing systems]. Timeline: [duration].

ROLE: Act as a senior BA with BRD writing experience in [domain — 
e.g. Enterprise IT / Retail / Telecom / Logistics].

ACTION: Draft these BRD sections:
1. Executive Summary (120 words max)
2. Business Objectives — 5 SMART objectives
3. Scope — 5 In-Scope items, 5 Out-of-Scope items
4. Assumptions (5) and Constraints (5)
5. High-Level Requirements — 8 functional (FR-001–008), 4 non-functional (NFR-001–004)

FORMAT: Formal document sections. Requirements numbered with IDs. 
NFRs include a measurable threshold (e.g. "system shall respond within 2 seconds").

TONE: Formal. Ready for Project Sponsor sign-off.
```

**Enterprise IT example — NFR output:**

> **NFR-002 — Performance:** The system shall process 500 concurrent user sessions with a page load time not exceeding 3 seconds under normal operating conditions.

---

## Prompt 3 — User Stories

**Use when:** Building a product backlog for an Agile sprint.

```
CONTEXT: Building [system/feature] for [org type]. 
Primary users: [list]. Core function: [what it does]. 
Integrates with: [systems].

ROLE: Act as an Agile BA with [domain] experience.

ACTION: Write [number] user stories for [module]. 
Cover these scenarios: [list].
Each story needs:
- Standard format: As a [user], I want [goal], so that [benefit]
- 3 acceptance criteria in Given-When-Then format
- MoSCoW priority
- Story point estimate (Fibonacci scale)

FORMAT: One block per story. Consistent headings throughout.

TONE: Concise. Jira/Azure DevOps-ready. No padding.
```

**Logistics example — Delivery Tracking:**

> **US-004: Real-Time Delivery Status**  
> *As a B2B customer, I want to track my delivery in real time, so that I can plan my warehouse receiving staff accordingly.*  
> **AC1:** Given a shipment is out for delivery, when I enter the tracking number, then I see live location and ETA updated every 15 minutes  
> **AC2:** Given the ETA changes by more than 30 minutes, when the update occurs, then I receive an automatic SMS and email alert  
> **AC3:** Given delivery is completed, when the driver marks it done, then my portal shows "Delivered" with timestamp and proof of delivery photo  
> **Priority:** Must Have | **Story Points:** 5

---

## Prompt 4 — Acceptance Criteria (from Existing Stories)

**Use when:** You have user stories but need proper ACs added quickly.

```
CONTEXT: Project: [name]. Here are my existing user stories:
[paste stories]

ROLE: Act as a quality-focused BA or Product Owner.

ACTION: For each story, write 4 Given-When-Then acceptance criteria.
Make sure each AC is: testable, unambiguous, and covers at least one edge case 
or error scenario per story.

FORMAT: ACs listed under each story, labelled AC1–AC4.

TONE: Precise. Written from a QA perspective — someone will test these.
```

---

## Prompt 5 — Non-Functional Requirements

**Use when:** Defining system quality attributes beyond functional requirements.

```
CONTEXT: Specifying requirements for [system name] — a [type] system for [org]. 
Expected users: [number concurrent]. Data sensitivity: [personal / financial / low]. 
Deployment: [cloud / on-prem / hybrid]. Regulatory context: [GDPR / PCI-DSS / other].

ROLE: Act as a BA with enterprise system specification experience.

ACTION: Write an NFR register covering 6 quality attributes: 
Performance, Scalability, Security, Availability, Usability, Compliance.
2-3 measurable requirements per attribute.

FORMAT: Table — NFR-ID | Attribute | Requirement Statement | 
Measurement Criteria | Priority (H/M/L)

TONE: Technical and precise. Suitable for a Solutions Architect review.
```

**Telecom example — Security NFR:**

> **NFR-009 — Security:** All customer data transmissions between the CRM and billing platform shall be encrypted using TLS 1.3 or higher. Any data at rest containing personal data shall be encrypted using AES-256.

---

## Prompt 6 — Requirements Traceability Matrix (RTM)

**Use when:** Starting your RTM to link objectives → requirements → test cases.

```
CONTEXT: Project: [name]. Here are my business objectives and functional requirements:
[paste your objectives and requirements]

ROLE: Act as a BA responsible for requirements traceability and quality assurance.

ACTION: Build an RTM that maps each functional requirement to:
(1) the business objective it supports
(2) the user story it originated from
(3) a suggested test case title

FORMAT: Table — Req-ID | Requirement | Business Objective | User Story ID | 
Test Case Title | Status (Draft / Approved / Tested)

TONE: Formal. Governance document — will be reviewed at project checkpoints.
```

---

## Prompt 7 — Ambiguity Checker

**Use when:** Reviewing a requirements draft before stakeholder sign-off.

```
CONTEXT: I have drafted requirements for [project]. Here they are:
[paste requirements]

ROLE: Act as a senior BA or Requirements Quality Reviewer doing a peer review.

ACTION: Flag every requirement that contains:
(1) ambiguous terms (e.g. "fast," "easy," "appropriate," "user-friendly")
(2) untestable statements
(3) missing actors or conditions
(4) conflicts with other requirements
For each issue: quote the original, explain the problem, suggest a rewrite.

FORMAT: Table — Req-ID | Issue Type | Original Text | Rewritten Version

TONE: Direct and critical. Peer review, not a compliment.
```

**Example catch — Enterprise IT ERP project:**

> ❌ Original: *"The system should respond quickly."*  
> ✅ Rewritten: *"The system shall return search results within 2 seconds for up to 10,000 concurrent users under standard load conditions."*

---

## Prompt 8 — MoSCoW Prioritisation

**Use when:** Preparing a prioritisation session or running one with stakeholders.

```
CONTEXT: [Number] requirements to prioritise for [project]. 
Timeline: [duration]. Team size: [number]. 
Constraints: [list — e.g. budget cap, integration freeze dates, regulatory deadline].
Stakeholders: [list].

ROLE: Act as a BA facilitating a MoSCoW prioritisation workshop.

ACTION: Take the following requirements [paste list] and:
(1) suggest a MoSCoW label with a one-line rationale
(2) flag duplicates or requirements that should be merged
(3) identify dependencies (which requirement must come before which)

FORMAT: 
- Prioritisation table: Requirement | MoSCoW | Rationale
- Dependency map: Requirement | Depends On | Dependency Type

TONE: Facilitative. This is a pre-read for a stakeholder workshop — clear and scannable.
```

---

## Quick Reference

| Task | Prompt | Key CRAFT Tip |
|------|--------|--------------|
| Interview prep | #1 | Group questions by theme in Action |
| BRD draft | #2 | Always include system integrations in Context |
| User stories | #3 | Specify scenarios + Fibonacci in Action |
| Add ACs | #4 | Ask for edge case coverage explicitly |
| NFRs | #5 | Name the regulatory context in Context |
| RTM | #6 | Paste real reqs — specific input = specific output |
| Quality check | #7 | Tell it to be critical, not nice |
| Prioritisation | #8 | Include real constraints — deadlines, budget |

---

> *Next: [07 — AI Project Prompts](./07_AI_Project_Prompts.md)*
