# 06 — Agile BA Prompts

*From backlog to retro. The prompts a BA needs for every sprint.*

---

## The BA's Role in Agile

In Agile, the BA is the bridge between what the business wants and what the team builds. You own the story quality. You facilitate the backlog. You make sure "done" actually means done.

These prompts cover the full Agile BA cycle — from sprint 0 through retrospective.

---

## Prompt 1 — Epic Definition

**Use when:** Breaking a large business capability into a structured epic before writing stories.

```
CONTEXT: We are building [capability/feature area] for [project] at [org type]. 
Business goal: [what outcome this delivers]. 
Users affected: [list user types]. 
Systems involved: [list]. 
Rough scope: [what's in, what's out].

ROLE: Act as an Agile BA defining epics for a product backlog.

ACTION: Define [number] epics for this capability area. For each epic:
- Epic title and one-line description
- Business value statement (why this epic matters)
- Acceptance criteria at epic level (3 conditions for "done")
- Suggested user stories to sit under it (titles only — 4-6 per epic)
- Dependencies on other epics or systems

FORMAT: One block per epic with consistent headings.

TONE: Concise. Product Owner and development team will use this in sprint planning.
```

**Enterprise IT example — ERP Finance Module:**

> **Epic: AP-001 — Invoice Processing Automation**  
> *Enable automated 3-way matching of invoices against POs and GRNs in SAP S/4HANA.*  
> **Business Value:** Reduce manual invoice processing time by 70% and eliminate payment errors  
> **Epic Done When:** 95% of standard invoices matched automatically; exceptions routed to approver; full audit trail captured  
> **Stories:** Capture supplier invoice | 3-way match logic | Exception flagging | Approval workflow | Payment run trigger | Audit log view

---

## Prompt 2 — Product Backlog Creation (Sprint 0)

**Use when:** Building the initial backlog at project kick-off.

```
CONTEXT: We are kicking off [project name] at [org type]. 
Core functionality to build: [list feature areas — 5-8 areas]. 
Users: [primary user types]. 
Systems: [integrations involved]. 
Timeline: [total project duration, number of sprints planned].

ROLE: Act as an Agile BA creating an initial product backlog for sprint planning.

ACTION: Produce a prioritised initial backlog with:
- 15-20 user stories across the feature areas listed
- Each story in standard format (As a / I want / So that)
- MoSCoW priority
- Story point estimate (Fibonacci)
- Epic it belongs to
- Any dependency flagged

FORMAT: Backlog table — Story ID | Epic | User Story | MoSCoW | 
Story Points | Dependency | Sprint Suggestion (1/2/3/later)

TONE: Practical. This is a working backlog — not a polished document.
```

**Logistics example — Delivery Tracking System (excerpt):**

> | ID | Epic | Story | MoSCoW | SP | Dependency | Sprint |
> |----|------|-------|--------|-----|-----------|--------|
> | US-001 | Driver App | As a driver, I want to see today's route on my app so I can start deliveries immediately | Must | 3 | None | 1 |
> | US-002 | Driver App | As a driver, I want to mark a delivery complete so the customer is notified automatically | Must | 5 | US-001 | 1 |
> | US-007 | Customer Portal | As a customer, I want to track my delivery in real time so I can plan for receipt | Must | 8 | US-002 | 2 |
> | US-012 | Reporting | As an ops manager, I want a daily delivery performance dashboard so I can spot issues early | Should | 5 | US-002 | 3 |

---

## Prompt 3 — Story Splitting

**Use when:** A user story is too large for a single sprint and needs to be broken down.

```
CONTEXT: We have the following user story that is too large for one sprint: 
[paste the story]. 
Story points estimated: [number]. 
Sprint capacity: [typical team velocity]. 
Technology involved: [any relevant system constraints].

ROLE: Act as an Agile BA or Scrum Master helping to split large stories.

ACTION: Split this story into [number] smaller, independently deliverable stories 
using the most appropriate splitting pattern from: 
workflow steps / business rule variations / happy path vs. edge cases / 
data variations / user types / interface channels.

For each new story:
- Standard user story format
- What slice of the original it covers
- Acceptance criteria (3 Given-When-Then)
- Story point estimate
- Suggested sprint

FORMAT: One block per story. Include a note on which splitting pattern was used and why.

TONE: Practical. Team will use these in sprint planning immediately.
```

**Telecom example — splitting "Manage Customer Account" story:**

> ❌ Too big: *"As a customer, I want to manage my account so I can update my details, change my plan, view my bill, and add services."* (13 points)  
>
> ✅ Split into:  
> US-A: Update personal details (3pts) — Sprint 1  
> US-B: View current plan and bill (3pts) — Sprint 1  
> US-C: Change plan (5pts) — Sprint 2  
> US-D: Add bolt-on services (5pts) — Sprint 2  
> *Splitting pattern used: Workflow steps — each is independently testable and deployable*

---

## Prompt 4 — Sprint Planning Support

**Use when:** Preparing for a sprint planning session — refining stories and confirming scope.

```
CONTEXT: We are planning Sprint [number] for [project]. 
Team velocity: [story points per sprint]. 
Sprint goal: [what we aim to deliver this sprint]. 
Candidate stories for this sprint: [paste story list with point estimates].

ROLE: Act as an Agile BA preparing for sprint planning.

ACTION: 
1. Check if the candidate stories fit within velocity — flag if over/under
2. For any story missing acceptance criteria, write 3 Given-When-Then ACs
3. Flag any stories with unclear scope, missing dependencies, or 
   technical assumptions that need clarification before the sprint starts
4. Suggest a sprint goal statement (one sentence)

FORMAT:
- Velocity check: simple maths + recommendation
- ACs: added under each story that needed them
- Flags: table — Story ID | Issue | Question to Resolve | Who to Ask
- Sprint goal: one sentence

TONE: Direct. This is prep work — flag the problems before the meeting, not during it.
```

---

## Prompt 5 — Definition of Done (DoD)

**Use when:** Establishing or refreshing the team's Definition of Done.

```
CONTEXT: We are establishing a Definition of Done for [project name]. 
Team: [size, mix — developers, QA, BA, UX]. 
Technology stack: [brief]. 
Regulatory or compliance requirements: [e.g. GDPR, accessibility, audit trail]. 
Delivery method: [CI/CD / manual releases / sprint-based releases].

ROLE: Act as an Agile BA or Scrum Master defining quality standards for delivery.

ACTION: Produce a Definition of Done covering 3 levels:
1. Story level — what must be true for a single story to be "done"
2. Sprint level — what must be true at the end of every sprint
3. Release level — what must be true before anything goes to production

FORMAT: Three numbered checklists, one per level. 
10-12 items per level. 
Mark any item that is [MANDATORY] vs [RECOMMENDED].

TONE: Clear and enforceable. The team will reference this every sprint.
```

**Retail example — Story-level DoD (excerpt):**

> ✅ Code reviewed and approved by at least one peer [MANDATORY]  
> ✅ Unit tests written and passing (min. 80% coverage) [MANDATORY]  
> ✅ Acceptance criteria tested and confirmed by BA [MANDATORY]  
> ✅ No critical or high bugs open against this story [MANDATORY]  
> ✅ UI matches approved wireframe or design spec [RECOMMENDED]  
> ✅ Performance tested for expected load [RECOMMENDED]

---

## Prompt 6 — Backlog Grooming / Refinement Session

**Use when:** Preparing for or facilitating a backlog refinement session.

```
CONTEXT: We are running a backlog refinement session for Sprint [next sprint number] 
on [project]. Team velocity: [points]. 
Stories up for refinement: [paste list]. 
Items known to be complex or unclear: [flag any known issues].

ROLE: Act as an Agile BA facilitating backlog refinement.

ACTION: For each story in the list:
1. Assess clarity — is the story well-defined or does it need rewriting?
2. Check for missing ACs — add if absent
3. Identify dependencies or blockers
4. Flag stories that need technical spikes before estimating
5. Suggest a relative size (XS/S/M/L/XL) as a pre-estimation guide

FORMAT: Table — Story ID | Story Title | Clarity (✅ / ⚠️ Needs work) | 
ACs Present (Y/N) | Dependency | Spike Needed (Y/N) | Size

TONE: Efficient. Refinement has a timebox — keep it moving.
```

---

## Prompt 7 — Sprint Retrospective Facilitation

**Use when:** Preparing for or documenting a sprint retrospective.

```
CONTEXT: Sprint [number] for [project] has just completed. 
Sprint goal: [what we aimed to deliver]. 
Achieved: [what was delivered]. 
Not completed: [what was carried over and why]. 
Team size: [number]. Known issues this sprint: [list any friction points].

ROLE: Act as an Agile BA or Scrum Master facilitating a sprint retrospective.

ACTION: Produce a retrospective structure covering:
1. What went well (prompt 5 discussion starters)
2. What didn't go well (prompt 5 discussion starters)
3. What to try next sprint (3 specific, actionable improvement suggestions 
   based on the issues described)
4. A team health check — 5 questions to gauge morale and collaboration
5. Action items template — for capturing commitments made in the retro

FORMAT:
- Discussion starters: bullet points per section
- Improvement suggestions: table — Suggestion | Why | Owner | How We Measure Success
- Health check: 5 questions with a 1-5 scale
- Action items: table — Action | Owner | Due Date | Status

TONE: Open and constructive. Blame-free. Forward-focused.
```

**Enterprise IT retro — improvement suggestion example:**

> | Suggestion | Why | Owner | How We Measure |
> |-----------|-----|-------|---------------|
> | BA signs off ACs before stories enter sprint | 2 stories returned mid-sprint due to unclear ACs | BA + PO | Zero AC rejections mid-sprint in Sprint 5 |
> | Daily standup capped at 15 min | Standups averaging 35 min, blocking morning work | Scrum Master | Time-logged for 2 sprints |

---

## Quick Reference

| Task | Prompt | Key CRAFT Tip |
|------|--------|--------------|
| Define large features | #1 Epics | List stories under each epic in Action |
| Build the backlog | #2 Backlog Creation | List all feature areas in Context |
| Break big stories | #3 Story Splitting | Paste the full story + point estimate |
| Prep sprint planning | #4 Sprint Planning | Include team velocity in Context |
| Set quality standards | #5 DoD | Include compliance requirements in Context |
| Run refinement | #6 Backlog Grooming | Flag known complex stories upfront |
| Run the retro | #7 Retrospective | Be honest about what didn't go well |

---

> *"Good Agile BA work is invisible when it's done well — the team just always knows what to build next."*

---

> *Back to: [README](./README.md)*
