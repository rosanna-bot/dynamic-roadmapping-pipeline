# Customer Journey Map: Product Manager

> **Dynamic Roadmapping Product — Product Manager Journey**
> **Date**: February 2026

---

## Persona Overview

**Name**: Product Manager (PM)
**Role**: Product Manager / Senior Product Manager
**Goal**: Build and maintain an evidence-based roadmap that reflects customer needs, company strategy, and execution reality — while minimizing the manual overhead that currently consumes a disproportionate amount of PM time.

### Context

The PM owns a product area or feature domain. They are responsible for discovery (understanding customer needs), prioritization (deciding what to build), roadmap planning (when to build it), stakeholder communication (keeping everyone aligned), and delivery tracking (ensuring it ships). Today, each of these phases involves significant manual work and tool-switching, leaving little time for the strategic thinking that is the PM's highest-value contribution.

### Key Characteristics

- Works at the **initiative, epic, and feature** level
- Primary interactions are with **engineering leads, designers, customer-facing teams, and their product leader**
- Needs to **defend prioritization decisions** with concrete customer evidence
- Success measured by **customer outcomes, delivery predictability, and stakeholder satisfaction**
- Spends too much time on **status gathering, manual updates, and ad-hoc reporting** — wants to reclaim this time for strategic work

---

## Journey Map

### Phase 1: Discovery & Insights

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Collects customer feedback from multiple sources: Zendesk tickets, Salesforce notes, Gong call recordings, NPS surveys, app store reviews, support conversations. Reviews, tags, and synthesizes manually. |
| **Tools Used** | Spreadsheets, Gong, Zendesk, Salesforce, Notion, manual note-taking |
| **Key Pain** | Manually collects and reviews customer feedback from various sources. Synthesis is time-consuming and always incomplete — critical signals are missed or arrive too late. The PM spends hours on manual aggregation instead of strategic analysis. |
| **Emotional State** | Overwhelmed — feels like drinking from a firehose; always worried about missed signals |
| **Frequency** | Ongoing, with weekly dedicated review time |
| **Time Spent** | 4–6 hours per week on manual feedback review and synthesis |
| **Workarounds** | Creates personal spreadsheet trackers; relies on CS/Sales to surface "important" feedback; reviews only a sample of available data |

**Customer Quote**:
> "We have a general lack of data to support product decisions and want AI to speed up PRD generation, feature alignment, and prioritization."

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | Miro Insights auto-ingests feedback from all connected sources. AI clusters themes, identifies trends, and surfaces relevant signals without PM intervention. |
| **AI Role** | Proactive intelligence: "3 enterprise accounts flagged onboarding friction this week — here are the common themes, representative quotes, and affected accounts." Weekly Slack digests highlight emerging patterns. |
| **Key Benefit** | PM focuses on interpreting insights rather than gathering them. No critical signal is missed. Customer voice is always current and accessible. |
| **Impact** | Saves 3–5 hours per week; improves signal coverage from ~30% to ~90% of available feedback; surfaces issues weeks earlier |

---

### Phase 2: Prioritization

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Scores and ranks backlog items using prioritization frameworks (RICE, WSJF, impact/effort); defends priority decisions to stakeholders; balances customer requests, technical debt, and strategic initiatives |
| **Tools Used** | Spreadsheets with manual scoring, Productboard (some teams), Jira backlog, ad-hoc Miro boards |
| **Key Pain** | Struggles to trace decisions back to specific customer feedback. Prioritization lives in spreadsheets with manual scoring frameworks that quickly go stale. Decisions feel arbitrary and are difficult to defend without concrete customer evidence. |
| **Emotional State** | Insecure — knows prioritization should be data-driven but lacks the data infrastructure to make it so |
| **Frequency** | Weekly backlog grooming; quarterly roadmap planning |
| **Time Spent** | 3–4 hours per week on prioritization activities |
| **Workarounds** | Manually counts customer requests in spreadsheets; asks CS/Sales for anecdotal evidence; relies on gut feeling supplemented by incomplete data |

**Customer Quote**:
> "We see strong potential in using Miro's connected AI capabilities — interview sets, prompt preparation, insights extraction, conversion into feature backlogs, and prototyping — all in one place."

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | Customer-enriched backlog where every item is automatically annotated with quantified customer evidence. Prioritization frameworks are pre-populated with real data. |
| **Enrichment per item** | # of customers requesting, customer list with segments, aggregated ARR impact, representative quotes, sentiment score, demand trend (growing/stable/declining) |
| **AI Role** | AI scores items by predicted impact based on customer evidence, strategic alignment, and market context. Suggests optimal priority ordering with explanations. |
| **Key Benefit** | Every prioritization decision is defensible with concrete evidence. Stakeholders can see exactly why something is prioritized — and what would change if priorities shifted. |
| **Impact** | Reduces prioritization prep time by 60%; increases stakeholder confidence in roadmap decisions; eliminates "loudest voice wins" dynamics |

---

### Phase 3: Roadmap Creation

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Creates the roadmap visualization; assigns initiatives to time horizons; communicates plan to stakeholders; iterates as priorities shift |
| **Tools Used** | Spreadsheets, Miro Timeline widget, PowerPoint, Aha!, or ad-hoc visual tools |
| **Key Pain** | Creates roadmap in spreadsheets or PM tools; manually updates as priorities shift. The roadmap is often out of date within days of creation. Maintaining it is a constant, low-value burden. |
| **Emotional State** | Resigned — accepts that the roadmap will always be somewhat wrong; dreads update cycles |
| **Frequency** | Quarterly creation; weekly-to-daily manual updates |
| **Time Spent** | 2–3 hours per week on roadmap maintenance |
| **Workarounds** | Uses "Now/Next/Later" format to avoid date commitments; maintains a "living" spreadsheet alongside a "presentation" version; manually syncs between Jira and roadmap tool |

**Specific Feedback**: 44% of users say they have no tool that allows them to create the visualization they need for team and stakeholders.

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | Timeline widget auto-populated from the enriched backlog. Drag-and-drop re-prioritization with immediate visual feedback. Roadmap stays current automatically through Jira sync. |
| **AI Role** | AI provides impact warnings during re-prioritization: "Moving Initiative X out of Q2 affects 5 enterprise accounts representing $1.2M ARR. Here's the customer list and their expectations." |
| **Key Benefit** | Roadmap creation is fast and maintenance is near-zero. The roadmap is a living artifact that reflects reality, not a snapshot that decays. |
| **Impact** | Reduces roadmap maintenance to near-zero; eliminates dual-maintenance burden; ensures roadmap always reflects current priorities and execution status |

---

### Phase 4: Scenario Planning

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Explores alternative prioritization and timing options; models "what-if" scenarios for resource allocation changes; prepares options for leadership review |
| **Tools Used** | Duplicate spreadsheets, copied Miro boards, mental models, informal whiteboarding |
| **Key Pain** | No way to play with different scenarios without affecting the source of truth. PMs resort to duplicating boards or creating ad-hoc spreadsheet models. Exploration is risky because changes made during "what-if" thinking accidentally become the real plan. |
| **Emotional State** | Cautious — avoids scenario planning because the tooling makes it dangerous |
| **Frequency** | Quarterly planning; ad-hoc when strategy questions arise |
| **Time Spent** | 4–8 hours per quarterly planning cycle |
| **Workarounds** | Duplicates entire boards/sheets before exploring; prefixes scenario items with "DRAFT" or "OPTION"; manually reconciles after scenario selection |

**Specific Feedback**: "If I want to remove stuff from the roadmap when I'm talking to the CEO, I don't want to remove it in Jira too."

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | "Snapshot mode" — create multiple roadmap scenarios as parallel branches without affecting the source of truth. Side-by-side comparison of scenarios with quantified trade-offs. |
| **AI Role** | AI compares scenarios against customer signals, strategic alignment, and execution capacity: "Scenario A covers 80% of top customer requests but stretches Team X beyond capacity. Scenario B covers 65% of requests but is achievable within current resources." |
| **Key Benefit** | Scenario planning becomes safe, fast, and data-enriched. PMs can freely explore options and present evidence-based alternatives to leadership. |
| **Impact** | Reduces scenario planning effort by 70%; eliminates risk of accidental changes; improves quality of options presented to leadership |

---

### Phase 5: Stakeholder Communication

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Creates roadmap presentations for different audiences; responds to ad-hoc questions from sales, executives, CS, and engineering; publishes customer-facing roadmap updates |
| **Tools Used** | PowerPoint/Google Slides, Slack, email, manually curated Miro boards, Confluence pages |
| **Key Pain** | Creates separate presentations for different audiences. Responds to frequent ad-hoc questions about roadmap status from sales, executives, and customer success teams. Communication overhead consumes a disproportionate amount of PM time. |
| **Emotional State** | Drained — feels like a "roadmap answering machine" instead of a strategic thinker |
| **Frequency** | Daily ad-hoc questions; weekly team updates; monthly executive reviews; quarterly planning presentations |
| **Time Spent** | 5–8 hours per week on roadmap communication |
| **Workarounds** | Creates FAQ documents that quickly go stale; sends "roadmap office hours" calendar invites; maintains separate Slack channels for different audiences |

**Core Pain**: PM responds to frequent ad-hoc questions about roadmap status and creates separate reports for each audience/segment manually.

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | Tailored views auto-generated from a single source of truth. Each audience sees the right level of detail without PM intervention. Views are embedded in Confluence/Slack for self-serve access. |
| **View Types** | **Engineering**: detailed epics, sprint assignments, dependencies. **Executives**: strategic themes, goal alignment, milestones. **Customer-facing**: public roadmap with idea status. **Sales/CS**: customer-specific views showing their requested features. |
| **AI Role** | AI-generated summaries answer common questions before they're asked. Auto-generates weekly Slack updates and monthly executive digests. |
| **Key Benefit** | Stakeholders get self-serve access to always-current roadmap information. PM recovers hours of communication time per week. |
| **Impact** | Reduces communication overhead by 60–70%; eliminates version drift; improves stakeholder satisfaction with roadmap transparency |

---

### Phase 6: Delivery Tracking

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Tracks sprint progress; monitors epic completion; identifies and escalates blockers; updates stakeholders on delivery status |
| **Tools Used** | Jira dashboards, Slack check-ins, team standups, manual spreadsheet trackers |
| **Key Pain** | Attends multiple standups; manually updates tracking spreadsheets; follows up on blockers through Slack and meetings. Status gathering feels like a full-time job on top of the actual PM role. Delays in information propagation lead to missed deadlines and surprised stakeholders. |
| **Emotional State** | Exhausted — the mechanics of tracking crowd out the thinking time PMs need |
| **Frequency** | Daily standup attendance; bi-weekly sprint reviews; weekly status updates |
| **Time Spent** | 5–7 hours per week on status gathering and tracking |
| **Workarounds** | Joins multiple team standups (often 3–5 per week); sends end-of-day Slack summary messages; creates personal Jira dashboards to avoid attending every meeting |

**Core Pain**: PM attends multiple team standups to gather status updates manually.

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | Jira/Azure sync shows real-time delivery status directly on the roadmap timeline. No manual updates needed — the roadmap reflects execution reality automatically. |
| **AI Role** | AI flags delivery risks proactively: "Epic X is 2 sprints behind — 3 dependent features affected. Here's the impact on Q2 commitments and the 5 customer accounts expecting this feature." Suggests mitigation options. |
| **Key Benefit** | PM spends zero time on manual status gathering. Risks are surfaced before they become crises. Stakeholders see live execution status without asking the PM. |
| **Impact** | Saves 4–6 hours per week; eliminates delivery surprises; improves on-time delivery through proactive risk detection |

---

### Phase 7: Iteration & Learning

#### Current State (Pain)

| Aspect | Details |
|---|---|
| **Activities** | Reviews delivery outcomes against original goals; updates roadmap based on what was learned; incorporates new customer feedback into future plans |
| **Tools Used** | Retrospective meetings, ad-hoc analysis, manual roadmap updates |
| **Key Pain** | Struggles to keep roadmap updated as conditions change. The feedback loop from delivery back to strategy is broken. Insights from one cycle don't flow into the next — the same mistakes repeat. Learning doesn't compound. |
| **Emotional State** | Frustrated — knows the learning loop should be continuous but lacks the tooling to make it work |
| **Frequency** | Sprint retrospectives (bi-weekly); quarterly roadmap reviews |
| **Time Spent** | 1–2 hours per cycle, often skipped due to time pressure |
| **Workarounds** | Keeps personal notes on lessons learned; occasionally reviews old roadmaps to identify patterns; relies on memory rather than systematic tracking |

#### Future State (Dynamic Roadmap Vision)

| Aspect | Details |
|---|---|
| **Experience** | AI continuously enriches roadmap items with new customer signals. Outcomes from delivered features feed back into the insights system, creating a closed learning loop. |
| **AI Role** | Proactive suggestions: "New competitor launched Feature Y — 12 customers mentioned this in the last 30 days. Consider adding to Q3 evaluation." Also: "Feature Z shipped 4 weeks ago — adoption is at 15%, below the 30% target. Here's what early feedback says about why." |
| **Key Benefit** | Learning becomes automatic and continuous. Every delivery cycle feeds intelligence back into the system, making future prioritization smarter. |
| **Impact** | Creates compounding intelligence advantage; surfaces market changes in real-time; closes the discovery-delivery-learning loop |

---

## Summary: Pain-to-Vision Transformation

| Phase | Top Pain | Vision Outcome | Time Saved |
|---|---|---|---|
| Discovery & Insights | Manual feedback collection; missed signals | Auto-ingested, AI-clustered insights | 3–5 hrs/week |
| Prioritization | Can't trace decisions to customer evidence | Customer-enriched backlog with ARR, quotes, sentiment | 60% reduction in prep |
| Roadmap Creation | Roadmap stale within days; constant manual updates | Auto-populated, living timeline from enriched backlog | Near-zero maintenance |
| Scenario Planning | Can't explore without risking source of truth | Snapshot mode with AI-compared trade-offs | 70% effort reduction |
| Stakeholder Communication | Separate reports for every audience; constant questions | Auto-generated views per audience; self-serve access | 60–70% reduction |
| Delivery Tracking | Manual standup attendance and status gathering | Real-time Jira sync with proactive risk alerts | 4–6 hrs/week |
| Iteration & Learning | Feedback loop is broken; learning doesn't compound | AI continuously enriches roadmap; closed learning loop | Continuous improvement |

**Total estimated PM time recovered**: 15–20 hours per week — equivalent to reclaiming 2–2.5 full workdays for strategic thinking, customer engagement, and creative problem-solving.

---

## Core PM Pains (Cross-Phase Summary)

From the PM Persona Research (Insights Use Case Library):

1. **Decision traceability** — PM struggles to trace decisions back to specific customer feedback
2. **Roadmap currency** — PM struggles to keep roadmap updated as changes occur
3. **Real-time visibility** — PM struggles to maintain accurate real-time visibility into delivery status
4. **Segment freshness** — PM struggles to keep segment analysis updated as new feedback arrives
5. **Idea validation** — PM struggles to validate ideas against actual customer needs
6. **Ad-hoc reporting** — PM responds to frequent ad-hoc questions about roadmap status
7. **Manual reporting** — PM creates separate reports for each audience/segment manually
8. **Status gathering** — PM attends multiple team standups to gather status updates manually
