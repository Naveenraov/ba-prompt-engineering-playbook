# 05 — Stakeholder Prompts

*Know your audience. Manage the politics. Keep everyone aligned.*

---

## Why Stakeholder Work Is Hard to Automate

Of all the BA disciplines, stakeholder management is the most human. AI can't read a room, sense tension between two departments, or know that the CFO says yes in meetings but blocks in private.

What AI *can* do: give you a solid structural starting point — the map, the plan, the communication templates — so you spend your time on the relationship, not the document.

Every output here needs your human layer on top. That's the rule.

---

## Prompt 1 — Stakeholder Identification & Analysis

**Use when:** Starting a new project and mapping who's involved, interested, or affected.

```
CONTEXT: I am a BA on [project name] at [org type — e.g. retail chain / 
telecom operator / logistics firm / enterprise IT department]. 
The project will [describe what it changes — system, process, or both]. 
Departments affected: [list]. Known stakeholders so far: [list names/roles].

ROLE: Act as a BA specialising in stakeholder analysis and engagement.

ACTION: Produce a stakeholder analysis covering all key groups. 
For each stakeholder: identify their role, interest in the project, 
level of influence, likely concerns or objections, and recommended engagement approach.
Also flag: any likely conflicts between stakeholder groups.

FORMAT: Table — Stakeholder | Role | Interest (H/M/L) | Influence (H/M/L) | 
Key Concerns | Engagement Approach | Conflict Risk

TONE: Analytical and politically aware. Internal BA working document.
```

**Enterprise IT example — ERP rollout stakeholder conflict:**

> | Stakeholder | Concern | Conflict Risk |
> |------------|---------|--------------|
> | Finance Manager | Loss of custom reports built in legacy system | High — will resist go-live if reports not replicated |
> | IT Lead | Tight timeline, resource constraints | Medium — may deprioritise finance requests |
> | CFO | ROI and timeline | Low — supportive if costs stay on track |

---

## Prompt 2 — Stakeholder Power/Interest Matrix

**Use when:** Prioritising who to spend your engagement time on.

```
CONTEXT: Project: [name]. Stakeholders identified: [paste your list].

ROLE: Act as a BA facilitating stakeholder prioritisation.

ACTION: Place each stakeholder into a Power/Interest matrix across 4 quadrants:
- Manage Closely (High Power, High Interest)
- Keep Satisfied (High Power, Low Interest)
- Keep Informed (Low Power, High Interest)
- Monitor (Low Power, Low Interest)
For each: suggest the ideal engagement frequency and channel.

FORMAT: 
- Matrix summary: table — Stakeholder | Quadrant | Engagement Frequency | Channel
- Top 3 "Manage Closely" stakeholders: one paragraph each on 
  why they matter and how to handle them

TONE: Strategic. This is your engagement prioritisation plan.
```

---

## Prompt 3 — RACI Matrix

**Use when:** Defining who is Responsible, Accountable, Consulted, and Informed for key project activities.

```
CONTEXT: Project: [name] at [org type]. 
Key activities to cover: [list 8-10 activities — e.g. requirements sign-off, 
UAT execution, go-live approval, data migration, training delivery].
Roles involved: [list all project roles].

ROLE: Act as a BA building a responsibility assignment matrix.

ACTION: Build a RACI matrix for the activities and roles listed.
Assign R/A/C/I for each combination. 
Flag any activities with: no Accountable owner (governance gap) or 
multiple Accountable owners (conflict risk).

FORMAT: RACI table — Activities as rows, Roles as columns, R/A/C/I in cells.
Flags listed below the table.

TONE: Structured and governance-focused. Will be reviewed at project kick-off.
```

**Logistics example — Delivery System implementation RACI (excerpt):**

> | Activity | Project Sponsor | BA | IT Lead | Operations Mgr | QA Lead |
> |----------|----------------|-----|---------|---------------|---------|
> | Requirements sign-off | A | R | C | C | I |
> | UAT execution | I | C | C | R | A |
> | Go-live approval | A | C | C | C | I |
> | Training delivery | I | R | I | A | I |

---

## Prompt 4 — Communication Plan

**Use when:** Planning how, when, and what to communicate to each stakeholder group throughout the project.

```
CONTEXT: Project: [name]. Duration: [timeline]. 
Key stakeholder groups: [list with brief description of their interest]. 
Project phases: [e.g. Discovery, Design, Build, UAT, Go-Live, Hypercare].
Communication tools available: [email / Teams / Confluence / SharePoint / town halls].

ROLE: Act as a BA creating a project communication plan.

ACTION: Build a communication plan covering all stakeholder groups across 
the project lifecycle. For each communication: audience, purpose, format, 
frequency, owner, and channel.
Include: a project status update template (5 fields) and 
an escalation communication template (for issues or delays).

FORMAT:
- Communication plan: table — Audience | Purpose | Format | Frequency | Owner | Channel
- Status update template: short fillable structure
- Escalation template: short fillable structure

TONE: Professional and practical. Used by the PM and BA to run project comms.
```

**Telecom example — Status update template:**

> **Project:** [Name] | **Date:** [Date] | **RAG Status:** 🟢 / 🟡 / 🔴  
> **This week:** [2-3 lines — what was completed]  
> **Next week:** [2-3 lines — what is planned]  
> **Risks/Issues:** [Any blockers or decisions needed]  
> **Action required from stakeholders:** [Yes/No — if yes, specify]

---

## Prompt 5 — Meeting Agenda & Facilitation Guide

**Use when:** Preparing for a requirements workshop, steering committee, or sprint review.

```
CONTEXT: I am facilitating a [meeting type — e.g. requirements workshop / 
steering committee / sprint review / stakeholder walkthrough] for [project name]. 
Duration: [time]. Attendees: [list roles]. 
Goals for this meeting: [list 2-3 outcomes you need to leave with]. 
Known tensions or difficult topics: [flag anything politically sensitive].

ROLE: Act as an experienced BA and meeting facilitator.

ACTION: Produce:
1. A structured agenda with time allocations
2. A facilitation guide — what to say to open each agenda item, 
   key questions to ask, and how to handle pushback or silence
3. Pre-meeting prep checklist — what to send attendees in advance
4. Parking lot template — for capturing out-of-scope items during the meeting

FORMAT:
- Agenda: table — Time | Item | Owner | Goal | Format (discussion/decision/info)
- Facilitation notes: bullet points under each agenda item
- Pre-meeting checklist: numbered list
- Parking lot: simple 3-column table

TONE: Practical. You're prepping for a real meeting, not writing a theory guide.
```

**Retail example — Requirements sign-off workshop agenda:**

> | Time | Item | Owner | Goal | Format |
> |------|------|-------|------|--------|
> | 09:00 | Welcome & objectives | BA | Align on purpose | Info |
> | 09:10 | As-Is recap — 3 key pain points | BA | Shared baseline | Discussion |
> | 09:30 | Requirements walkthrough — Priority 1 | BA + SME | Get approval or flag gaps | Decision |
> | 10:15 | Open issues & parking lot review | BA | Clear blockers | Discussion |
> | 10:30 | Next steps & owners | PM | Actions assigned | Decision |

---

## Prompt 6 — Stakeholder Interview Debrief

**Use when:** Synthesising notes from a stakeholder interview into structured BA outputs.

```
CONTEXT: I have just completed a stakeholder interview with [role/name] 
for [project name]. Here are my raw notes:
[paste your notes — bullet points, shorthand, whatever you captured]

ROLE: Act as a BA synthesising interview notes into structured requirements input.

ACTION: From these notes, extract and organise:
1. Business objectives mentioned (explicit and implied)
2. Pain points and current workarounds
3. Desired capabilities (what they want the new system/process to do)
4. Constraints mentioned (technical, budget, political, timeline)
5. Open questions — things that need follow-up clarification
6. Potential risks flagged (consciously or unconsciously)

FORMAT:
- Sections with bold headers, bullet points within each
- Open questions: numbered list with suggested follow-up action
- Flag any contradictions or ambiguities in the notes

TONE: Analytical. This becomes your working notes for requirements documentation.
```

---

## Prompt 7 — Stakeholder Objection Handling

**Use when:** Preparing for resistance — a stakeholder who is blocking, delaying, or pushing back.

```
CONTEXT: I am a BA on [project name]. A key stakeholder — [role] — is 
resisting the project because: [describe their objection or concern]. 
Their influence level: [High/Medium]. 
What the project needs from them: [sign-off / data access / participation in UAT / etc.].
What I know about their priorities: [what matters most to them].

ROLE: Act as a BA and change management advisor.

ACTION: Produce:
1. An analysis of the likely real reason behind the objection 
   (stated concern vs. underlying concern)
2. Three engagement approaches — from collaborative to escalation
3. Talking points for a one-to-one conversation
4. A suggested email to request a conversation (neutral, non-confrontational)

FORMAT:
- Analysis: 2 short paragraphs
- Approaches: table — Approach | When to Use | Risk | Expected Outcome
- Talking points: 5 bullet points
- Email: subject line + 3-paragraph body

TONE: Politically intelligent and empathetic. Not aggressive. Not a pushover either.
```

---

## Quick Reference

| Task | Prompt | Key CRAFT Tip |
|------|--------|--------------|
| Map all stakeholders | #1 Identification | Include known stakeholders — AI adds the gaps |
| Prioritise engagement | #2 Power/Interest | Paste your stakeholder list directly |
| Define responsibilities | #3 RACI | List all activities explicitly in Action |
| Plan communications | #4 Comms Plan | Include project phases in Context |
| Prep a workshop | #5 Meeting Agenda | Flag politically sensitive topics in Context |
| Process interview notes | #6 Debrief | Paste raw notes — messy is fine |
| Handle resistance | #7 Objection Handling | Be honest about the stakeholder's real concern |

---

> *"The BA who understands people as well as processes is the one who actually delivers change."*

---

> *Next: [06 — Agile BA Prompts](./06_Agile_BA_Prompts.md)*
