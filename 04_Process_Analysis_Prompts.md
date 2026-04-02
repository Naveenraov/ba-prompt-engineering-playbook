# 04 — Process Analysis Prompts

*Map the current mess. Design the better way. Show the gap.*

---

## Why Process Analysis Still Matters

Every system change starts with understanding what's broken today and defining what good looks like tomorrow. AI can accelerate this — but only if you give it specific, grounded context.

Vague process descriptions produce vague process outputs. Use these prompts with real numbers, real systems, and real pain points.

---

## Prompt 1 — As-Is Process Description

**Use when:** Documenting the current state before a redesign or system change.

```
CONTEXT: I need to document the current (As-Is) process for [process name] 
at a [org type — e.g. retail chain / telecom operator / logistics firm / 
enterprise IT department]. 
Key steps involve: [brief description]. 
Systems used: [list]. 
People involved: [roles]. 
Known pain points: [list 3-5 issues].

ROLE: Act as a BA specialising in business process documentation and analysis.

ACTION: Produce an As-Is process description covering:
1. Process narrative — step-by-step flow from trigger to completion
2. Roles involved at each step (RACI-lite: who does what)
3. Systems touched at each step
4. Pain points mapped to specific steps (not just listed separately)
5. Process metrics: average time per step, error rate, volume (where known)

FORMAT: 
- Process steps: numbered table — Step # | Step Name | Who | System | 
  Pain Point (if any) | Time Taken
- Summary pain points: table — Pain Point | Root Cause | Business Impact | Frequency

TONE: Analytical and factual. Workshop-ready — stakeholders will review this.
```

**Retail example — Goods Receiving process:**

> | Step | Name | Who | System | Pain Point | Time |
> |------|------|-----|--------|-----------|------|
> | 1 | PO receipt confirmation | Warehouse Operative | SAP | PO often not raised before goods arrive | 15 min |
> | 2 | Physical count vs. delivery note | Warehouse Operative | Manual (paper) | No digital scan — errors common | 30 min |
> | 3 | Discrepancy reporting | Supervisor | Email | No standard template — inconsistent data | 20 min |

---

## Prompt 2 — To-Be Process Design

**Use when:** Designing the improved future state process.

```
CONTEXT: We are redesigning the [process name] process at [org type]. 
Current As-Is issues: [list top 3-5 pain points from As-Is analysis]. 
New system / capability being introduced: [e.g. new WMS, AI tool, CRM, ERP module]. 
Constraints: [e.g. union agreement, GDPR, budget, timeline].
Success criteria: [what does "better" look like — faster, fewer errors, less manual work?]

ROLE: Act as a BA specialising in process redesign and business transformation.

ACTION: Design the To-Be process covering:
1. Redesigned process steps — what changes, what stays the same, what is removed
2. Technology enablers — which system supports each step
3. Expected improvement per step (time saved, error reduction, automation introduced)
4. Process KPIs: 3-5 measurable targets for the new process
5. Change impact summary — which roles are most affected and how

FORMAT:
- To-Be steps: table — Step # | Step Name | Who | System | Change from As-Is | 
  Expected Improvement
- KPI table: KPI | Current Baseline | Target | Measurement Method
- Change impact: table — Role | Impact Type | Action Required

TONE: Constructive and solution-focused. Design workshop output.
```

**Logistics example — KPI table for route optimisation:**

> | KPI | Current | Target | How Measured |
> |-----|---------|--------|-------------|
> | On-time delivery rate | 88% | 96% | Delivery system timestamp |
> | Avg. route planning time | 45 min/day | 5 min/day | Dispatcher time log |
> | Fuel cost per delivery | €4.20 | €3.50 | Fleet management system |
> | Failed delivery rate | 12% | 5% | Driver app completion data |

---

## Prompt 3 — Gap Analysis (As-Is vs To-Be)

**Use when:** Identifying what needs to change, build, or retire to move from current to future state.

```
CONTEXT: We are analysing the gap between our current [process/system] and 
the desired future state for [project name] at [org type].
As-Is summary: [brief description of current state].
To-Be summary: [brief description of target state].
Project scope: [what is changing — process only / system only / both].

ROLE: Act as a BA conducting a formal gap analysis.

ACTION: Produce a gap analysis covering [number] functional areas: [list areas].
For each area identify: current capability, target capability, the specific gap, 
recommended action to close the gap, effort estimate, and priority.

FORMAT: Table — Functional Area | As-Is Capability | To-Be Capability | 
Gap Description | Recommended Action | Effort (H/M/L) | Priority (H/M/L)

TONE: Analytical. Will be used in a solution design workshop.
```

**Telecom example — CRM Migration gap (one row):**

> | Functional Area | As-Is | To-Be | Gap | Action | Effort | Priority |
> |----------------|-------|-------|-----|--------|--------|---------|
> | Field Engineer Scheduling | Manual job assignment via phone/email in Siebel | Automated scheduling with skills matching in Salesforce Field Service | Skills-based routing not available in current system | Configure Salesforce Field Service skills matrix; migrate engineer profiles | High | High |

---

## Prompt 4 — Root Cause Analysis

**Use when:** A business problem keeps recurring and you need to understand why before designing a solution.

```
CONTEXT: We have a recurring problem in [process/area] at [org type]: 
[describe the problem — what happens, how often, what impact it causes]. 
Known contributing factors: [list what you already suspect]. 
Data available: [what evidence exists — error logs, complaint data, audit findings].

ROLE: Act as a BA facilitating a root cause analysis.

ACTION: Conduct a structured root cause analysis using the 5 Whys approach. 
Then categorise root causes using an Ishikawa (fishbone) framework across: 
People, Process, Technology, Data, and Governance.
Conclude with: top 3 root causes ranked by impact, 
and a recommended corrective action for each.

FORMAT:
- 5 Whys: chain of Why → Because statements leading to root cause
- Fishbone summary: table — Category | Contributing Factor | Evidence | Root Cause? (Y/N)
- Recommendations: table — Root Cause | Corrective Action | Owner | Priority

TONE: Diagnostic and evidence-based. Workshop output for a problem-solving session.
```

**Enterprise IT example — repeated ERP data quality failures:**

> *Why are monthly finance reports incorrect?*  
> → Because journal entries contain errors  
> → Because data entry is manual with no validation  
> → Because the ERP form has no mandatory field checks  
> → Because the system was configured without input validation rules  
> → **Root cause: ERP implementation skipped data validation configuration due to time pressure**

---

## Prompt 5 — BPMN Process Description (for Diagramming)

**Use when:** You need to describe a process in structured text so it can be built into a BPMN diagram in Lucidchart, Draw.io, or Visio.

```
CONTEXT: I need to create a BPMN process diagram for [process name] 
at [org type]. The process involves these roles (swim lanes): [list roles]. 
It is triggered by: [trigger event]. It ends when: [end condition]. 
Key decision points: [list decision points — yes/no branches].

ROLE: Act as a BA with BPMN process modelling experience.

ACTION: Describe the process in structured BPMN notation text, covering:
1. Start event
2. Tasks per swim lane (labelled with role)
3. Decision gateways with Yes/No branches
4. Intermediate events (e.g. wait for approval, system notification)
5. End event(s) — including error/exception paths

FORMAT: Structured text with clear labels:
[ROLE] Task name → Gateway: condition? → Yes: next task / No: alternative path
Use consistent notation throughout.

TONE: Technical and precise. A developer or process modeller should be able to 
build the diagram directly from this description.
```

**Retail example — Returns authorisation process (abbreviated):**

> [CUSTOMER] Initiates return request online →  
> [SYSTEM] Validates order within return window → Gateway: Within 28 days?  
> → Yes: [SYSTEM] Generates return label, sends to customer  
> → No: [CUSTOMER SERVICE] Manual review → Gateway: Exception approved?  
> → Yes: [SYSTEM] Generates label → [CUSTOMER] Returns item  
> → No: [SYSTEM] Sends rejection notification → [END: Return Declined]

---

## Prompt 6 — Process Improvement Recommendations

**Use when:** Presenting process improvement options to stakeholders with a clear recommendation.

```
CONTEXT: We have completed an As-Is analysis of [process name] at [org type]. 
Key problems identified: [list 3-5]. 
Improvement options being considered: [list options — e.g. automate, outsource, 
redesign, new system, AI]. 
Constraints: [budget / timeline / headcount / technology stack].

ROLE: Act as a BA presenting process improvement options to business stakeholders.

ACTION: Produce an options appraisal covering [number] improvement options. 
For each option: description, benefits, risks, estimated effort, cost indicator, 
and fit with constraints. Conclude with a recommended option and rationale.

FORMAT:
- Options table: Option | Description | Benefits | Risks | Effort | Cost | Fits Constraints?
- Recommendation: one paragraph — state the option, why it wins, what conditions 
  must be met for it to succeed

TONE: Consultative. You're advising, not just presenting. Make a clear call.
```

---

## Quick Reference

| Task | Prompt | Key CRAFT Tip |
|------|--------|--------------|
| Document current state | #1 As-Is | Include real metrics — time, volume, error rate |
| Design future state | #2 To-Be | Name the new system/tool in Context |
| Find the gaps | #3 Gap Analysis | List functional areas explicitly in Action |
| Find the real problem | #4 Root Cause | Include known contributing factors in Context |
| Prep for diagramming | #5 BPMN | Name swim lanes and decision points upfront |
| Make a recommendation | #6 Options Appraisal | Include constraints — forces a real trade-off |

---

> *"A BA who can show what's broken, why it's broken, and what to do about it — that's the one who gets invited back."*

---

> *Next: [05 — Stakeholder Prompts](./05_Stakeholder_Prompts.md)*
