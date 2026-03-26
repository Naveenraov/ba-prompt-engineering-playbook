# 02 — The CRAFT Framework

*5 elements. Every prompt. Every time.*

---

## What is CRAFT?

It's the difference between a vague request and a stakeholder-ready output.

Most BAs prompt like this: *"Help me write user stories for a login screen."*  
Result: generic, fluffy, needs a full rewrite.

CRAFT prompts like this: *"I'm a BA on an Enterprise IT ERP rollout. Act as an Agile BA. Write 4 user stories for SSO login, covering employee, admin, and API user roles. Format as story + 3 Given-When-Then ACs + MoSCoW label. Concise, Jira-ready."*  
Result: paste straight into your backlog.

---

## The 5 Elements

| Element | Question It Answers | Weak Version | Strong Version |
|---------|-------------------|-------------|---------------|
| **C — Context** | What project, domain, constraints? | "A software project" | "ERP rollout for a 500-person logistics firm, integrating with SAP and legacy WMS, 6-month timeline" |
| **R — Role** | Who should AI be? | (nothing) | "Act as a senior BA with enterprise IT and ERP implementation experience" |
| **A — Action** | What exactly do I need? | "Write requirements" | "Write 6 functional requirements for the inventory module, covering stock lookup, transfer, write-off, and audit trail" |
| **F — Format** | How should it look? | (nothing) | "Numbered list with IDs (FR-001). Include priority column: High / Medium / Low" |
| **T — Tone** | Who's the audience? | (nothing) | "Formal. Suitable for technical review with a Solutions Architect" |

---

## The CRAFT Template — Copy This

```
CONTEXT: [Project type, organisation, domain, key systems, constraints, timeline]

ROLE: Act as [expert role, e.g. "senior BA with retail IT and Agile delivery experience"]

ACTION: [Precise deliverable — what, how many, what to cover]

FORMAT: [Table columns / numbered list / document sections / Jira-ready]

TONE: [Audience — formal / analytical / plain English / executive summary]
```

---

## 4 Full CRAFT Examples — Across All Domains

---

### 🖥️ Example 1 — Enterprise IT: ERP Requirements

**The task:** Writing functional requirements for a finance module in an ERP upgrade.

```
CONTEXT: A professional services firm (300 staff, Ireland) is upgrading from SAP ECC 
to SAP S/4HANA. Project phase: Finance module go-live in Q3. Key stakeholders: CFO, 
Finance Manager, IT Lead. Integration with existing payroll and procurement systems.

ROLE: Act as a senior Business Analyst specialising in ERP implementations and 
finance system requirements.

ACTION: Write 8 functional requirements for the Accounts Payable module covering: 
invoice capture, 3-way matching, payment run, supplier management, exception handling, 
audit trail, approval workflow, and reporting.

FORMAT: Numbered list with IDs (FR-001 to FR-008). Each requirement: one sentence, 
testable, no ambiguity. Include a Priority column: Must Have / Should Have / Could Have.

TONE: Precise and technical. Suitable for sign-off by a Solutions Architect.
```

**What you get:** 8 clean, testable requirements with IDs and priorities — ready for RTM.

---

### 🛒 Example 2 — Retail: User Stories for Returns Module

**The task:** Agile backlog for a new returns management feature.

```
CONTEXT: A multichannel retailer (80 stores + e-commerce) is building a unified 
returns module. Customers can return in-store or by post. The module integrates 
with SAP ERP and the existing CRM. Key pain point: refund processing takes 5-7 days.

ROLE: Act as an Agile BA with retail IT experience.

ACTION: Write 4 user stories for the returns module:
(1) in-store return initiation, (2) online return request, 
(3) refund processing trigger, (4) store manager override.
For each: standard user story format + 3 Given-When-Then ACs + MoSCoW label.

FORMAT: One block per story with clear headings. Concise ACs — 1-2 sentences each.

TONE: Punchy. Backlog-ready. No fluff.
```

**Sample output:**

> **US-002: Online Return Request**  
> *As an online customer, I want to request a return from my account, so I can send back an item without visiting a store.*  
> **AC1:** Given I'm logged in, when I select an order item and click "Return," then I see return options (post / drop-off) and reason codes  
> **AC2:** Given I select "post," when I confirm, then a prepaid label is emailed within 5 minutes  
> **AC3:** Given the return is registered, when it's submitted, then my account shows "Return Pending" and a case number  
> **Priority:** Must Have

---

### 📡 Example 3 — Telecom: Gap Analysis for CRM Migration

**The task:** Documenting gaps between legacy Siebel CRM and new Salesforce platform.

```
CONTEXT: A telecom operator migrating from Siebel CRM to Salesforce Service Cloud. 
2M+ customer records. Key functions: fault ticketing, field engineer scheduling, 
billing enquiries. Timeline: 9 months. Zero downtime required during cutover.

ROLE: Act as a BA specialising in CRM implementations and telecom domain.

ACTION: Produce a gap analysis for 5 functional areas: 
Customer Account Management, Fault Ticketing, Field Engineer Scheduling, 
Billing Enquiry Handling, Reporting & Analytics.

FORMAT: Table — Functional Area | As-Is | To-Be | Gap | Action | Complexity (H/M/L)

TONE: Analytical. Workshop-ready — will be walked through with IT and Business leads.
```

**What you get:** A 5-row table you can present the same day. Walk stakeholders through it. Assign owners. Done.

---

### 🚚 Example 4 — Logistics: AI Feasibility One-Pager

**The task:** Quick feasibility brief for an AI route optimisation pilot.

```
CONTEXT: A logistics company (80 vehicles, 1,200 daily deliveries, Dublin/Cork) 
is evaluating AI route optimisation. Current process: manual dispatcher using Google Maps. 
Issues: fuel costs up 18% YoY, late deliveries at 12%. 
Constraints: driver union agreement, GDPR (GPS data), 6-month window.

ROLE: Act as an AI BA specialising in logistics operations.

ACTION: Write a one-page feasibility brief covering: problem statement (3 lines), 
proposed solution (3 lines), data needed, top 3 benefits with KPIs, 
top 3 risks with mitigations, and a Go/No-Go recommendation.

FORMAT: Short sections with bold headers. Benefits and risks as mini-tables. 
Total length: under 500 words.

TONE: Direct. Written for a COO who has 5 minutes.
```

**What you get:** A crisp exec brief, not a 30-page document nobody reads.

---

## Anti-Patterns — What Kills a Prompt

| ❌ Anti-Pattern | Why It Fails | ✅ Fix |
|---------------|-------------|-------|
| No context | AI guesses the domain | Always name the industry + system |
| Vague action ("help me with X") | Output covers everything loosely | Define the deliverable + quantity |
| No format | Wall of prose, needs reformatting | Specify table, list, or doc structure |
| Missing role | Generic register | Match role to the task type |
| Wrong tone | Not stakeholder-ready | Name the actual audience |

---

## Iteration Checklist

After you get output, ask:

- [ ] Did it match my format spec?
- [ ] Is the domain context reflected?
- [ ] Is the tone right for my stakeholder?
- [ ] Did it cover everything in my Action?
- [ ] What one thing would I change in the prompt?

Your second prompt is always better than your first. That's the point.

---

> *Next: [03 — Requirements Prompts](./03_Requirements_Prompts.md)*
