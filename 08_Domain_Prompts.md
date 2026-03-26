# 08 — Domain Prompts: Retail IT · Telecom · Logistics

*Prompt templates tailored to specific industry domains*

---

## Why Domain-Specific Prompts Matter

Generic prompts produce generic output. When you ground a prompt in specific domain language — retail replenishment cycles, telecom provisioning workflows, last-mile logistics — the AI output becomes immediately usable rather than requiring heavy rewriting.

This section provides ready-to-use domain prompts for the three industries where this playbook's author has hands-on experience.

---

## 🛒 Section A — Retail IT Prompts

---

### Retail Prompt 1 — Demand Forecasting System: BRD Executive Summary

```
CONTEXT: A retail chain with [number] stores and [number] SKUs is implementing 
an AI-driven demand forecasting system to replace manual Excel-based stock ordering. 
The system will integrate with an existing SAP ERP and POS system. 
Key business problem: stockouts averaging [X]% and overstock write-offs costing 
€[X] annually. Project budget: €[X]. Timeline: [X] months.

ROLE: Act as a senior Business Analyst with retail IT and AI project experience.

ACTION: Draft the Executive Summary section of a Business Requirements Document 
for this demand forecasting implementation. Cover: business problem, proposed solution, 
expected benefits (quantified where possible), key risks, and a recommendation to proceed.

FORMAT: 3 paragraphs, 150-200 words each. Formal prose. 
Include a summary benefits table: Benefit | Metric | Baseline | Target

TONE: Formal and persuasive. Written for a Board-level Project Sponsor.
```

---

### Retail Prompt 2 — E-Commerce Returns Process: As-Is Process Description

```
CONTEXT: A multichannel retailer sells online and in 80 physical stores. 
Currently, returns are processed differently across channels: 
online returns require a pre-paid label posted within 28 days; 
in-store returns can be processed immediately at any till. 
Returns data is not shared in real-time between channels, 
causing inventory reconciliation delays of 2-3 days.

ROLE: Act as a Business Analyst documenting the current state (As-Is) 
of a retail returns process.

ACTION: Produce an As-Is process narrative covering the end-to-end returns journey 
for both online and in-store channels. Identify 5 key pain points and inefficiencies.

FORMAT: 
- Process narrative: Step-by-step prose (numbered steps per channel)
- Pain points: Table — Pain Point | Cause | Business Impact | Frequency

TONE: Analytical and factual. Written as a process analysis document.
```

---

### Retail Prompt 3 — Loyalty Programme CRM: User Stories

```
CONTEXT: A grocery retailer is launching a digital loyalty programme. 
Customers earn points on purchases (in-store and online), 
can redeem points for discounts, and receive personalised offers via app and email. 
The system integrates with the POS, mobile app, and email marketing platform.

ROLE: Act as an Agile Business Analyst with retail CRM experience.

ACTION: Write 6 user stories for the loyalty programme covering: 
point earning (in-store), point earning (online), points balance view, 
redemption at checkout, personalised offer receipt, and account registration.

FORMAT: Standard user story format + 3 Given-When-Then ACs per story + MoSCoW label.

TONE: Concise. Suitable for a product backlog in Jira.
```

---

## 📡 Section B — Telecom Prompts

---

### Telecom Prompt 1 — CRM Migration: Gap Analysis

```
CONTEXT: A telecom operator is migrating from a legacy on-premise CRM (Siebel) 
to Salesforce Service Cloud. The current system manages 2M+ customer accounts, 
handles fault ticketing, field engineer scheduling, and billing enquiries. 
The new system must replicate all critical functionality within 9 months.
Key constraint: zero disruption to customer-facing service during cutover.

ROLE: Act as a Business Analyst specialising in CRM implementation and telecom domain.

ACTION: Produce a Gap Analysis covering 6 functional areas: 
Customer Account Management, Fault Ticket Management, Field Engineer Scheduling, 
Billing Enquiry Handling, Reporting & Analytics, and Third-Party Integrations.

FORMAT: Table — Functional Area | Current Capability (As-Is) | 
Target Capability (To-Be) | Gap Description | Recommended Action | 
Complexity (High/Medium/Low)

TONE: Analytical. Suitable for a Solution Design workshop with IT and Business stakeholders.
```

---

### Telecom Prompt 2 — AI Chatbot for Customer Service: Requirements

```
CONTEXT: A telecom provider is deploying an AI-powered chatbot to handle Tier 1 
customer service enquiries (billing questions, service status, plan upgrades). 
Currently, call centre handles 15,000 contacts/month. 
Target: deflect 40% to chatbot within 6 months. 
The chatbot integrates with the billing system, CRM, and service management platform. 
GDPR compliance required for all customer data handled.

ROLE: Act as a Business Analyst specialising in AI and customer service technology.

ACTION: Produce a requirements specification for the chatbot covering: 
10 functional requirements, 5 non-functional requirements (including GDPR), 
and a Conversation Design spec for 3 key user journeys 
(billing query, fault report, plan upgrade).

FORMAT: 
- Requirements: numbered with IDs (CB-FR-001 etc.)
- Conversation Design: flow table — User Input | Bot Response | 
  System Action | Escalation Trigger

TONE: Technical and precise. Suitable for a vendor briefing document.
```

---

### Telecom Prompt 3 — Network Upgrade: Stakeholder Analysis

```
CONTEXT: A telecom operator is upgrading its core network infrastructure 
from 4G to 5G across [region]. The project will affect: 
consumer customers (service interruptions), business customers (SLA implications), 
field engineers (new tools and processes), IT (system integrations), 
regulatory body (licence conditions), and local authorities (planning permissions).

ROLE: Act as a Business Analyst conducting a stakeholder analysis.

ACTION: Produce a stakeholder analysis covering all groups listed. 
For each stakeholder: identify their interest in the project, 
their level of influence, their likely concerns, and the recommended engagement approach.

FORMAT: Table — Stakeholder Group | Interest | Influence (H/M/L) | 
Key Concerns | Engagement Strategy | Communication Frequency

TONE: Analytical and strategic. Suitable for a Project Initiation Document (PID).
```

---

## 🚚 Section C — Logistics Prompts

---

### Logistics Prompt 1 — Route Optimisation AI: Feasibility Brief

```
CONTEXT: A logistics company is evaluating AI-powered route optimisation for 
last-mile delivery in [city/region]. Current process: dispatchers manually assign 
routes each morning using Google Maps. Fleet size: [number] vehicles. 
Average daily deliveries: [number]. Key issues: fuel costs rising, 
late deliveries at [X]%, customer complaints increasing.
Constraints: driver union agreement, GDPR (GPS tracking), 6-month delivery window.

ROLE: Act as an AI Business Analyst specialising in logistics and operations.

ACTION: Produce a feasibility brief covering: 
problem statement, solution description, data requirements 
(what data the AI needs to function), expected benefits (quantified), 
top 5 risks with mitigations, and a clear recommendation.

FORMAT: Document with headings. Benefits as a table: 
Benefit | Current State | Target State | Measurement KPI. 
Risks as a table: Risk | Likelihood | Impact | Mitigation.

TONE: Concise and evidence-based. Suitable for a COO decision briefing.
```

---

### Logistics Prompt 2 — Warehouse Management System: Process Improvement

```
CONTEXT: A logistics company operates a warehouse processing [number] 
inbound and outbound orders daily. Current system is a legacy WMS with 
limited scanning capability. Issues: pick errors at [X]%, 
average pick time [X] minutes per order, no real-time inventory visibility.
A new WMS with RF scanning, real-time inventory, and automated putaway is being evaluated.

ROLE: Act as a Business Analyst specialising in warehouse operations and WMS implementations.

ACTION: Produce a To-Be process design for the following warehouse processes: 
(1) Goods Inbound & Receiving, (2) Putaway, (3) Order Picking, (4) Despatch & Shipping. 
For each process: describe the improved workflow, list the technology enablers, 
and state the expected improvement metric.

FORMAT: One section per process. Each section: 
- To-Be Process (numbered steps)
- Technology Enablers (bullet list)
- KPI Improvement: Current → Target

TONE: Operational and practical. Suitable for a process design workshop.
```

---

### Logistics Prompt 3 — Customer Delivery Notification: User Stories

```
CONTEXT: A logistics provider is improving its customer communication system. 
Currently customers receive only one SMS at point of despatch. 
The new system should provide real-time delivery status updates 
via SMS, email, and app push notifications. 
Customers should be able to reschedule or redirect deliveries 
up to 2 hours before estimated delivery.

ROLE: Act as an Agile Business Analyst with logistics and customer experience focus.

ACTION: Write 5 user stories for the delivery notification system covering: 
despatch notification, out-for-delivery update, ETA notification, 
delivery confirmation, and failed delivery notification with rescheduling option.

FORMAT: Standard user story + 3 Given-When-Then ACs + MoSCoW label + Story Points.

TONE: Concise. Backlog-ready.
```

---

## Domain Prompt Quick Reference

| Domain | Prompt | Best Used For |
|--------|--------|--------------|
| Retail | Demand Forecasting BRD | AI project initiation |
| Retail | Returns Process As-Is | Process analysis workshop |
| Retail | Loyalty CRM Stories | Agile backlog sprint 0 |
| Telecom | CRM Migration Gap Analysis | Solution design phase |
| Telecom | AI Chatbot Requirements | Vendor briefing |
| Telecom | Network Upgrade Stakeholders | Project initiation |
| Logistics | Route Optimisation Feasibility | AI investment decision |
| Logistics | WMS Process Improvement | To-Be design workshop |
| Logistics | Delivery Notification Stories | Customer experience sprint |

---

> *Next: [09 — Lessons Learned](./09_Lessons_Learned.md)*
