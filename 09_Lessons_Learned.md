# 09 — Lessons Learned

*What worked. What didn't. What I'd do differently.*

---

## Why Include This?

Most playbooks skip the honest part. This section doesn't.

These are real observations from building and using this playbook across Enterprise IT, Retail, Telecom, and Logistics projects. If you're building your own prompt library, these will save you time.

---

## What Worked

**1. CRAFT eliminates the blank page.**  
Before CRAFT, I'd open an AI tool, type something vague, and spend an hour fixing the output. Filling in the five elements forced me to think before I typed. Several times, the act of completing CRAFT made me realise I hadn't clearly defined the deliverable myself.

**2. Domain context is the biggest lever.**  
The single biggest jump in output quality came from adding specific context. "A logistics company with 80 vehicles, 1,200 daily deliveries, and a GDPR constraint on GPS data" produces dramatically better output than "a transport company." Real domain knowledge — the kind you build on actual projects — translates directly into prompt quality.

**3. Format specification kills rework.**  
Every hour spent defining the output format saves two hours of reformatting. "A table with columns: Risk | Category | Likelihood | Impact | Mitigation" is ready to paste into Confluence. "Write me some risks" is not.

**4. Role assignment shifts the register.**  
"Act as a senior BA with 10 years of retail IT experience" produces practitioner-level language. Without a role, you get textbook-style output that sounds like it was written by someone who has read about BA work but never done it.

---

## What Didn't Work (And the Fix)

**Over-long Actions lose focus.**  
Early prompts had 8 sub-tasks in the Action element. AI addressed some well and skipped others. Fix: break complex tasks into a sequence. Get the framework first, then drill into each section with a follow-up prompt.

**AI doesn't know your stakeholders.**  
Stakeholder analysis prompts produce structurally solid outputs, but miss the human layer — the sponsor who agrees in meetings then blocks in private, the technical lead who gold-plates every solution. Always add the political layer yourself.

**Acceptance criteria need domain sense-checking.**  
AI-generated ACs are often technically naive. One example: a Given-When-Then criterion for an AI system that assumed 100% model accuracy. Always review ACs with a "could a tester actually verify this?" mindset.

**"Formal" is too vague a tone.**  
"Formal" means different things to a startup CTO vs. a GDPR Data Protection Officer. Fix: specify the actual audience in the Tone element. "Formal — suitable for a regulatory compliance review" gets a much more targeted output.

---

## The Surprises

**AI is better at structure than content.**  
It excels at logical flow, consistent headings, and document scaffolding. The content within the structure still needs significant BA judgment — especially for domain-specific nuance and stakeholder-aware framing.

**Prompting improves your own thinking.**  
Writing a CRAFT prompt forces you to articulate exactly what you need. That discipline improved my requirements thinking independent of the AI output.

**The AI BA gap is real — and wide.**  
After working through these prompts across real project contexts, I'm more convinced than ever: the value BAs add in AI projects isn't tool proficiency. It's knowing what questions to ask, what risks to flag, and how to govern decisions that affect real people. This playbook is a bridge to that — not a shortcut around it.

---

## Top 5 Recommendations for Building Your Own Prompt Library

| # | Recommendation | Why |
|---|---------------|-----|
| 1 | Use CRAFT for every prompt — no exceptions | Consistency = reusability |
| 2 | Include specific domain context every time | Generic context = generic output |
| 3 | Specify the output format before you write the Action | Saves reformatting time |
| 4 | Keep a prompt log — save every prompt that worked well | Your library compounds in value |
| 5 | Validate every output against your domain knowledge | AI is a first draft. You're the gate. |

---

## What's Coming Next in This Playbook

- `04_Process_Analysis_Prompts.md` — As-Is/To-Be, root cause, gap analysis
- `05_Stakeholder_Prompts.md` — RACI, stakeholder maps, meeting prep, comms plans
- `06_Agile_BA_Prompts.md` — backlog grooming, sprint planning, retrospectives
- Case study: applying this playbook on a live logistics project

---

> *"The best BAs in 2026 aren't the ones who use AI the most. They're the ones who use it most deliberately."*

---

**Author:** Naveen Rao V | AI-Focused Business Analyst  
**LinkedIn:** [linkedin.com/in/naveen-rao-v-01593a169](https://linkedin.com/in/naveen-rao-v-01593a169)  
**Last updated:** March 2026
