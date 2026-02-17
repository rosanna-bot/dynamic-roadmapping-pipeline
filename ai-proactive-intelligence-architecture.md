# AI Proactive Intelligence Architecture

> **Dynamic Roadmapping Product — Technical Architecture Document**
> **Date**: February 2026

---

## 1. Overview

The core differentiator of Miro's dynamic roadmapping system is **proactive AI** — intelligence that doesn't wait for queries but continuously monitors, analyzes, and surfaces actionable information to keep roadmaps aligned with reality and company strategy.

### Design Philosophy

Traditional roadmapping tools are reactive: they display what the PM enters and update only when the PM makes changes. The dynamic roadmapping system inverts this model. The AI layer is an **always-on intelligence engine** that:

1. **Continuously ingests** signals from five distinct source categories
2. **Analyzes and correlates** signals across sources to identify patterns invisible to manual review
3. **Proactively surfaces** actionable insights to PMs and Product Leaders at the right time, in the right context
4. **Recommends actions** grounded in evidence, while keeping humans firmly in control of decisions

### Architecture Principles

| Principle | Description |
|---|---|
| **Proactive, not reactive** | The system surfaces insights without being asked, operating as a continuous intelligence layer rather than a query-response tool |
| **Evidence-grounded** | Every suggestion, alert, or recommendation is traceable to specific data points — customer quotes, velocity metrics, competitor actions, usage data |
| **Human-in-the-loop** | AI recommends; humans decide. The system never makes autonomous changes to the roadmap without PM or leader approval |
| **Composable intelligence** | Individual agent behaviors can be combined for complex analyses (e.g., Opportunity Spotter + Scenario Simulator = "What if we prioritize this emerging theme?") |
| **Progressive trust** | Start with alerts and recommendations; evolve toward delegated actions as users build confidence in the system |
| **Privacy-aware** | Respect data access boundaries; leaders see aggregated signals, not raw customer data they shouldn't access |

---

## 2. Signal Sources

The AI system draws from five distinct signal categories to build a comprehensive, multi-dimensional picture of the context surrounding every roadmap decision.

### 2.1 Customer Voice

The richest and most unique signal source, powered by Miro Insights.

| Attribute | Details |
|---|---|
| **Data Sources** | Gong call transcripts, Salesforce opportunity notes, Zendesk support tickets, NPS survey responses, app store reviews, Qualtrics surveys, in-app feedback, customer interviews |
| **Ingestion Method** | Automated via Miro Insights connectors; real-time for support tickets and NPS; batch for call transcripts and surveys |
| **Signals Produced** | Emerging customer themes, feedback volume trends, sentiment shifts by segment, specific customer requests with frequency, pain point clustering, feature demand ranking |
| **Update Cadence** | Real-time ingestion → daily clustering and theme extraction → weekly trend analysis and digest |
| **AI Processing** | NLP-based theme extraction; sentiment analysis; entity recognition (accounts, features, competitors); trend detection; urgency scoring |

**Example signal chain**:
```
Raw data: 47 Zendesk tickets mentioning "export" + 12 Gong calls discussing "reporting limitations"
    ↓
AI clustering: Theme "Reporting & Export" identified as emerging (volume up 60% month-over-month)
    ↓
Enrichment: 23 unique accounts affected, $4.2M aggregated ARR, sentiment: frustrated
    ↓
Surfaced insight: "Reporting & Export emerged as a top-5 customer pain this month.
                   23 accounts ($4.2M ARR) affected. No current roadmap coverage."
```

### 2.2 Execution Reality

Real-time data from engineering execution that reveals what's actually happening in delivery.

| Attribute | Details |
|---|---|
| **Data Sources** | Jira/Azure DevOps (sprint data, epic progress, story completion, blocker tracking), GitHub/GitLab (commit frequency, PR activity, code review patterns) |
| **Ingestion Method** | Two-way Jira sync (existing infrastructure); real-time status updates; daily aggregation for trends |
| **Signals Produced** | Sprint velocity trends (team-level and aggregate), epic completion forecasts with confidence intervals, blocker patterns and accumulation rates, scope change frequency and magnitude, capacity utilization by team, dependency status between teams |
| **Update Cadence** | Real-time sync for status changes → daily aggregation for velocity and forecasts → weekly trend analysis |
| **AI Processing** | Time-series analysis for velocity trends; predictive modeling for delivery dates; pattern recognition for blocker types; anomaly detection for sudden changes |

**Example signal chain**:
```
Raw data: Team Alpha sprint velocity: 45, 42, 38, 31, 28 (last 5 sprints)
    ↓
AI analysis: Consistent velocity decline detected (38% drop over 5 sprints)
    ↓
Correlation: 3 engineers reassigned to incident response; 2 key blockers unresolved for 3 sprints
    ↓
Prediction: Epic "Enterprise SSO" projected to miss Q2 target by 4 weeks at current velocity
    ↓
Surfaced insight: "Epic 'Enterprise SSO' at risk — Team Alpha velocity declined 38% over 5 sprints.
                   Root cause: capacity reduction + unresolved blockers. Impact: 8 accounts waiting.
                   Recommend: resolve blockers (2-week recovery) or adjust scope (cut Phase 2)."
```

### 2.3 Market Context

External intelligence that frames roadmap decisions within industry and competitive dynamics.

| Attribute | Details |
|---|---|
| **Data Sources** | Competitor tracking services, industry analyst reports, news feeds, technology trend databases, regulatory updates (ingested or manually linked) |
| **Ingestion Method** | Semi-automated: AI processes linked reports and news; manual curation for analyst briefings; API integrations where available |
| **Signals Produced** | Competitor feature launches and positioning changes, market trend shifts relevant to current roadmap areas, regulatory changes that affect product requirements, technology disruptions that create opportunities or threats |
| **Update Cadence** | As available; AI matches new intelligence against current roadmap items for relevance scoring |
| **AI Processing** | Relevance matching against current roadmap; impact assessment; competitive gap analysis; trend correlation with customer feedback patterns |

**Example signal chain**:
```
Raw data: Competitor X announces "AI-powered roadmap assistant" at conference
    ↓
AI matching: Feature maps to 3 items on current roadmap (AI Copilot, Smart Timeline, Scenario Planning)
    ↓
Customer correlation: 12 accounts mentioned this competitor capability in Gong calls (last 60 days)
    ↓
Surfaced insight: "Competitor X launched AI roadmap assistant. 12 of your accounts mentioned this
                   capability recently (4 are in active renewal). Your AI Copilot initiative addresses
                   this — currently scheduled for Q3. Consider acceleration."
```

### 2.4 Business Metrics

Product usage and business data that reveals the actual impact of product decisions.

| Attribute | Details |
|---|---|
| **Data Sources** | Product analytics platforms (Amplitude, Mixpanel, or internal), revenue dashboards, churn tracking systems, expansion/contraction data, activation and retention metrics |
| **Ingestion Method** | API integrations with analytics and revenue systems; daily data pulls; event-based triggers for significant changes |
| **Signals Produced** | Feature adoption rates and trajectories, retention impact by feature/segment, revenue impact estimates per feature area, churn risk indicators and predictors, usage pattern changes that signal satisfaction or frustration |
| **Update Cadence** | Daily metrics ingestion → weekly trend analysis → monthly impact reporting |
| **AI Processing** | Adoption curve analysis; retention impact modeling; churn risk scoring; usage pattern anomaly detection; A/B test result interpretation |

**Example signal chain**:
```
Raw data: Feature "Timeline Widget" adoption: Week 1: 12%, Week 4: 18%, Week 8: 19%, Week 12: 19%
    ↓
AI analysis: Adoption plateau detected at ~19% (target was 30%)
    ↓
Correlation: Support tickets about "timeline grouping" up 40%; 3 accounts churned citing "roadmap limitations"
    ↓
Surfaced insight: "Timeline Widget adoption plateaued at 19% (target: 30%). Correlated pain:
                   'grouping/hierarchy' (top feedback theme, 200+ mentions). 3 accounts churned.
                   Recommend: accelerate grouping improvements scheduled for next quarter."
```

### 2.5 Strategy Artifacts

The strategic context that gives meaning to all other signals — what the company is trying to achieve and why.

| Attribute | Details |
|---|---|
| **Data Sources** | Company OKRs (defined in Miro), department goals, initiative definitions, strategic narrative documents, board/leadership strategy decks |
| **Ingestion Method** | Direct integration with Miro's goal/OKR system; manual linking of strategy documents; AI extraction of goals from narrative documents |
| **Signals Produced** | Active goal hierarchy with current status, alignment scores per initiative, goal coverage maps (which goals have sufficient roadmap investment), strategic drift indicators (work drifting from goals), priority hierarchy for conflict resolution |
| **Update Cadence** | Updated when goals or initiatives change; continuous alignment scoring against execution data |
| **AI Processing** | Goal-initiative matching; coverage analysis; drift detection; priority conflict identification; alignment trend tracking |

**Example signal chain**:
```
Raw data: Q2 OKR: "Improve enterprise onboarding NPS from 32 to 45"
    ↓
AI coverage check: Only 1 initiative (15% of capacity) directly targets this goal
    ↓
Customer correlation: 15 enterprise accounts ($4.2M ARR) flagged onboarding friction in last 90 days
    ↓
Execution check: The one initiative targeting this goal is 3 sprints behind schedule
    ↓
Surfaced insight: "Goal 'Improve Enterprise Onboarding NPS' is critically under-invested:
                   only 15% capacity coverage, and that initiative is 3 sprints behind.
                   15 accounts ($4.2M ARR) flagged this pain. Risk: Q2 OKR miss.
                   Recommend: reallocate capacity or adjust OKR target."
```

---

## 3. AI Agent Behaviors

Five specialized AI agent behaviors work together to transform raw signals into actionable roadmap intelligence. Each agent has distinct responsibilities, triggers, and outputs, but they share the common signal layer and can be composed for complex analyses.

### 3.1 Alignment Monitor

**Mission**: Ensure that every piece of active work serves an active strategic goal, and every active goal has sufficient execution investment.

| Attribute | Details |
|---|---|
| **Function** | Continuously checks if roadmap items trace back to active goals. Monitors both directions: "Does this work serve a goal?" and "Does this goal have enough work?" |
| **Primary signals** | Strategy Artifacts + Execution Reality |
| **Trigger conditions** | (1) New work item added without goal linkage, (2) Goal-initiative alignment score drops below threshold, (3) Goal created without corresponding roadmap coverage, (4) Initiative scope changes in ways that reduce goal alignment, (5) Goal is retired but associated work continues |

#### Outputs

| Output | Frequency | Audience |
|---|---|---|
| **Alignment score per initiative** | Real-time (updated on change) | PM + Leader views |
| **Orphan alerts** | Immediate when detected | PM who owns the item |
| **Goal coverage gaps** | Weekly digest + immediate for critical goals | Product Leader |
| **Alignment trend report** | Weekly | Product Leader |
| **Re-alignment recommendations** | When drift exceeds threshold | PM + Leader |

#### Example Alerts

> **Orphan detected**: "Initiative 'Dark Mode Support' (Team Beta, 20% capacity) has no connection to any active Q2 goal. This initiative was linked to Goal 5 ('Improve User Satisfaction'), which was retired last month. Recommend: connect to a new goal or deprioritize."

> **Coverage gap**: "Goal 3 ('Enterprise Growth') has only 10% roadmap coverage — down from 35% after last week's re-prioritization. 15 enterprise accounts are tracking features tied to this goal. Recommend: review Q2 resource allocation."

> **Drift alert**: "Initiative 'Platform Redesign' scope expanded 40% in last 2 sprints. Original scope aligned with Goal 2 at 85%. Current scope aligns at 52%. New work items added without goal linkage. Recommend: review scope additions with Product Leader."

---

### 3.2 Risk Predictor

**Mission**: Identify delivery risks before they materialize, giving PMs and leaders time to mitigate rather than react.

| Attribute | Details |
|---|---|
| **Function** | Analyzes Jira execution patterns — velocity, scope changes, blockers, capacity — to predict delivery risks with confidence intervals |
| **Primary signals** | Execution Reality + Strategy Artifacts (for impact assessment) |
| **Trigger conditions** | (1) Velocity drops exceeding threshold (>15% decline over 3+ sprints), (2) Scope changes mid-sprint (>20% scope addition), (3) Blocker accumulation (>3 unresolved blockers for >1 sprint), (4) Dependency delays in upstream teams, (5) Capacity reduction (team member departure, reassignment) |

#### Outputs

| Output | Frequency | Audience |
|---|---|---|
| **Risk score per epic/initiative** | Daily update | PM (detail) + Leader (summary) |
| **Projected delivery date ranges** | Updated daily with confidence intervals | PM + stakeholder views |
| **Root cause analysis** | When risk is first detected | PM |
| **Recommended mitigations** | With each risk alert | PM |
| **Escalation alerts** | When risk threatens company goals or customer commitments | Product Leader |

#### Risk Scoring Model

| Risk Level | Criteria | Color | Action |
|---|---|---|---|
| **Low** | On track; velocity stable; no blockers | Green | No action needed |
| **Medium** | Minor velocity dip OR scope growth <15% OR 1–2 blockers | Yellow | PM monitor; no escalation |
| **High** | Velocity declining >15% OR scope growth >20% OR 3+ blockers OR dependency at risk | Orange | PM intervention required; Leader notified |
| **Critical** | Projected miss on customer commitment OR company goal at risk OR multiple compounding risks | Red | Immediate escalation; Leader intervention |

#### Example Alerts

> **High risk**: "Epic 'Enterprise SSO' (Team Alpha) — Risk: HIGH
> - Velocity declined 38% over 5 sprints (45 → 28 pts/sprint)
> - 2 blockers unresolved for 3+ sprints (API dependency, security review)
> - Projected completion: June 15 (±2 weeks) — original target: May 1
> - Impact: 8 enterprise accounts ($2.8M ARR) expecting Q2 delivery
> - Recommended: (1) Escalate blockers to engineering leadership, (2) Reduce scope by deferring Phase 2, (3) Communicate revised timeline to affected accounts"

> **Escalation**: "Q2 Company Goal 'Launch Enterprise Tier' at risk. 2 of 3 dependent epics are HIGH risk. Combined probability of Q2 delivery: 35%. Recommend: Product Leader review of scope and resource allocation."

---

### 3.3 Opportunity Spotter

**Mission**: Identify emerging customer needs and market opportunities that the current roadmap doesn't address, ensuring the product team never misses a significant signal.

| Attribute | Details |
|---|---|
| **Function** | Clusters emerging customer themes from Insights data and matches them against current roadmap coverage. Highlights gaps between what customers need and what the roadmap delivers. |
| **Primary signals** | Customer Voice + Market Context + Business Metrics |
| **Trigger conditions** | (1) New customer theme emerging with significant volume (>10 mentions in 30 days), (2) Existing theme experiencing rapid growth (>50% increase month-over-month), (3) Competitor move creates new customer demand, (4) Underserved segment identified (segment with high feedback volume but low roadmap coverage), (5) Churn data reveals unaddressed pain point |

#### Outputs

| Output | Frequency | Audience |
|---|---|---|
| **Opportunity cards** | When threshold met | PM |
| **Gap analysis** | Weekly digest | PM + Leader |
| **Demand trend reports** | Weekly | PM |
| **Competitive response recommendations** | When competitor move detected | PM + Leader |
| **ARR impact estimates** | Per opportunity | PM + Leader |

#### Opportunity Card Structure

Each surfaced opportunity contains:

```
┌─────────────────────────────────────────────────────────────┐
│  OPPORTUNITY: [Theme Name]                                  │
│                                                             │
│  Demand Signal                                              │
│  ├─ Customer count: 23 accounts                             │
│  ├─ Aggregated ARR: $4.2M                                   │
│  ├─ Trend: ↑ 60% month-over-month                           │
│  ├─ Top segments: Enterprise (65%), Mid-Market (25%)        │
│  └─ Sentiment: Frustrated (avg score: 2.1/5)               │
│                                                             │
│  Evidence                                                   │
│  ├─ Top quotes: [3-5 representative customer quotes]        │
│  ├─ Sources: 15 Gong calls, 28 support tickets, 4 NPS      │
│  └─ Key accounts: [Named accounts with context]             │
│                                                             │
│  Current Coverage                                           │
│  ├─ Roadmap items: [0 — GAP] or [list of related items]    │
│  ├─ Coverage score: 0% (no items) to 100% (fully covered)  │
│  └─ Nearest planned work: [if any]                          │
│                                                             │
│  Competitive Context                                        │
│  ├─ Competitors offering: [list]                            │
│  └─ Market trend: [relevant context]                        │
│                                                             │
│  Recommended Action                                         │
│  ├─ Suggested priority: [based on demand + strategic fit]   │
│  ├─ Estimated effort: [if comparable work exists]           │
│  └─ Strategic alignment: [which goals this could serve]     │
└─────────────────────────────────────────────────────────────┘
```

#### Example Alert

> **Emerging opportunity**: "Collaborative Approval Workflows"
> - 18 accounts ($3.1M ARR) requested in last 60 days — up 120% from prior period
> - Top segments: Enterprise (72%), heavily concentrated in Financial Services
> - No current roadmap coverage; 2 competitors launched this capability in Q1
> - Strategic fit: Aligns with Goal 4 (Enterprise Growth) and Goal 7 (Regulated Industry Expansion)
> - Recommend: Add to Q3 evaluation; schedule customer discovery calls with top 5 requesting accounts

---

### 3.4 Scenario Simulator

**Mission**: Enable leaders and PMs to explore strategic alternatives with full visibility into consequences, making every pivot a data-informed decision.

| Attribute | Details |
|---|---|
| **Function** | When strategy changes are proposed, automatically models cascading impact across the portfolio. Provides quantified trade-off analysis for multi-scenario comparison. |
| **Primary signals** | All five signal sources (comprehensive context for simulation) |
| **Trigger conditions** | (1) User initiates "what-if" scenario from roadmap view, (2) Leadership requests resource reallocation analysis, (3) External event triggers strategy reassessment (e.g., competitor move, market shift), (4) Risk Predictor identifies need for contingency planning |

#### Simulation Dimensions

| Dimension | What's Modeled | Data Source |
|---|---|---|
| **Timeline impact** | How does each scenario affect delivery dates for all affected initiatives? | Execution Reality (velocity, capacity) |
| **Customer impact** | Which accounts are affected? What commitments change? What's the ARR at risk? | Customer Voice + CRM data |
| **Goal impact** | How does each scenario change coverage and progress against company OKRs? | Strategy Artifacts |
| **Team capacity** | Is each scenario achievable with current resources? Where are the bottlenecks? | Execution Reality (team capacity) |
| **Dependency impact** | What cross-team dependencies are affected? What's the cascade? | Execution Reality (Jira dependencies) |
| **Risk assessment** | What's the overall risk profile of each scenario? | All signals (composite) |

#### Scenario Comparison Output

```
┌──────────────────────┬──────────────────────┬──────────────────────┐
│   Dimension          │  Scenario A          │  Scenario B          │
│                      │  "Aggressive Q2"     │  "Conservative Q2"   │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Timeline             │ 3 initiatives        │ All initiatives      │
│                      │ accelerated 4 wks;   │ on original          │
│                      │ 2 delayed 6 wks      │ schedule             │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Customer impact      │ 8 accts ($2.1M)      │ 5 accts ($800K)      │
│                      │ get faster delivery; │ get faster delivery;  │
│                      │ 5 accts ($800K)      │ no negative impact   │
│                      │ delayed              │                      │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Goal coverage        │ Goal 4: 40%→70%      │ Goal 4: 40%→50%      │
│                      │ Goal 2: 60%→35%      │ Goal 2: 60%→55%      │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Capacity fit         │ Team Alpha at 120%   │ All teams within     │
│                      │ (overloaded)         │ capacity              │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Dependencies         │ 2 cross-team         │ No new dependency    │
│                      │ dependencies created │ risks                │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ Risk score           │ HIGH                 │ LOW                  │
├──────────────────────┼──────────────────────┼──────────────────────┤
│ AI recommendation    │ "High reward but     │ "Safe execution but  │
│                      │ requires Team Alpha  │ misses enterprise    │
│                      │ capacity resolution" │ acceleration window" │
└──────────────────────┴──────────────────────┴──────────────────────┘
```

#### Interaction Model
1. **User creates scenario**: Drags initiatives between time periods, adjusts resource allocation, or changes priorities
2. **AI auto-simulates**: Immediately calculates cascading effects across all dimensions
3. **Results displayed**: Side-by-side comparison with highlighted trade-offs
4. **AI recommends**: Suggests the optimal path with rationale grounded in evidence
5. **User decides**: Commits to a scenario, which becomes the new roadmap (or continues exploring)

---

### 3.5 Cadence Automator

**Mission**: Eliminate the manual effort of producing recurring roadmap communications and planning inputs, ensuring stakeholders stay informed without consuming PM time.

| Attribute | Details |
|---|---|
| **Function** | Auto-generates recurring roadmap communications and planning inputs on a defined cadence |
| **Primary signals** | All five signal sources (tailored per output type) |
| **Trigger conditions** | Time-based cadence (configurable per output type) |

#### Outputs by Cadence

##### Weekly Outputs

| Output | Content | Audience | Channel |
|---|---|---|---|
| **Roadmap Status Summary** | Top-line progress on active initiatives; items completed this week; items at risk; emerging signals | PM + Leader | Slack digest, email, embedded in Confluence |
| **Risk Report** | All items with elevated risk scores; new risks this week; resolved risks; trend | PM + Leader | Dashboard + Slack alert for critical items |
| **Signal Digest** | Top 5 customer signals of the week; execution anomalies; market updates | PM | In-app notification + Slack |

##### Monthly Outputs

| Output | Content | Audience | Channel |
|---|---|---|---|
| **Strategy Alignment Report** | Goal coverage analysis; alignment trend (improving/declining); orphaned work; under-invested goals | Product Leader | Dashboard + PDF export |
| **Customer Voice Summary** | Top themes of the month; volume trends; sentiment changes; segment analysis | PM + Leader | Dashboard + Slack |
| **Delivery Retrospective** | Velocity trends; planned vs. actual; root cause analysis for misses; recommendations | PM + Engineering Lead | Dashboard |

##### Quarterly Outputs

| Output | Content | Audience | Channel |
|---|---|---|---|
| **Planning Input Package** | Customer evidence summary for next quarter; execution capacity forecast; competitive landscape update; recommended priorities with evidence | PM + Leader | Comprehensive document |
| **Portfolio Health Assessment** | Cross-team performance analysis; dependency health; goal achievement progress; risk outlook | Product Leader + Executive | Dashboard + presentation export |
| **Strategy Effectiveness Review** | How well did the roadmap serve strategy? Which decisions were validated/invalidated? Key learnings. | Product Leader | Document + presentation |

---

## 4. Agent Composition & Interaction

Individual agents are powerful on their own, but their real value emerges when they work together to address complex scenarios.

### Composition Examples

| Scenario | Agents Involved | Combined Output |
|---|---|---|
| "Should we accelerate Initiative X?" | Opportunity Spotter (demand evidence) + Risk Predictor (execution feasibility) + Alignment Monitor (strategic fit) + Scenario Simulator (impact modeling) | Comprehensive recommendation with customer evidence, execution risk assessment, strategic alignment score, and simulated portfolio impact |
| "A key customer is threatening to churn" | Opportunity Spotter (account-specific feedback) + Alignment Monitor (relevant roadmap items) + Cadence Automator (customer-specific status update) | Account intelligence brief with relevant roadmap items, their status, and a talking-points document for the account team |
| "Competitor launched a major feature" | Opportunity Spotter (customer demand correlation) + Scenario Simulator (acceleration modeling) + Risk Predictor (capacity assessment) | Competitive response analysis with customer impact, acceleration scenarios, and execution feasibility |
| "Quarterly planning kickoff" | Cadence Automator (planning input package) + Opportunity Spotter (demand landscape) + Alignment Monitor (goal retrospective) + Risk Predictor (capacity forecast) | Comprehensive quarterly planning brief with customer evidence, capacity outlook, goal review, and prioritization recommendations |

### Information Flow Between Agents

```
┌──────────────────────────────────────────────────────────────────────────┐
│                         SIGNAL LAYER                                     │
│  Customer Voice | Execution Reality | Market Context | Business Metrics  │
│                              | Strategy Artifacts                        │
└────────────┬──────────┬──────────┬──────────┬──────────┬─────────────────┘
             │          │          │          │          │
             v          v          v          v          v
     ┌───────────┐ ┌─────────┐ ┌──────────┐ ┌─────────┐ ┌──────────┐
     │ Alignment │ │  Risk   │ │Opportunity│ │Scenario │ │ Cadence  │
     │ Monitor   │ │Predictor│ │ Spotter  │ │Simulator│ │Automator │
     └─────┬─────┘ └────┬────┘ └────┬─────┘ └────┬────┘ └────┬─────┘
           │             │           │             │           │
           └─────────────┴───────────┴─────────────┴───────────┘
                                     │
                                     v
                        ┌────────────────────────┐
                        │   INTELLIGENCE HUB     │
                        │  Composed insights     │
                        │  Context-aware routing │
                        │  Priority scoring      │
                        └───────────┬────────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    v               v               v
            ┌─────────────┐ ┌─────────────┐ ┌─────────────┐
            │ PM Dashboard│ │Leader Views │ │ Stakeholder │
            │ + Copilot   │ │ + Portfolio │ │ Auto-Views  │
            └─────────────┘ └─────────────┘ └─────────────┘
```

---

## 5. Delivery to Users

### Notification & Surfacing Strategy

Not all insights are equally urgent. The system uses a tiered approach to ensure the right information reaches the right person at the right time:

| Tier | Urgency | Delivery Method | Example |
|---|---|---|---|
| **Tier 1: Critical** | Immediate action needed | In-app banner + Slack DM + email | "Customer commitment at risk — Epic X delayed 4 weeks. 3 accounts affected." |
| **Tier 2: Important** | Action needed this week | In-app notification + signal dashboard | "Emerging theme: 'collaborative approvals' growing 60% MoM. No roadmap coverage." |
| **Tier 3: Informational** | Awareness; no immediate action | Signal dashboard + weekly digest | "Competitor updated pricing page — no direct product impact detected." |
| **Tier 4: Background** | Long-term trend tracking | Monthly/quarterly reports | "Team velocity trend over 6 months: gradual improvement (+12%)." |

### Contextual Placement

Insights are surfaced not just in a central dashboard but also **in context** where decisions are being made:

- **In Timeline view**: Risk indicators, customer demand heatmap, alignment scores appear directly on roadmap items
- **In Table/Backlog view**: Customer enrichment, priority recommendations, and demand trends per item
- **In Kanban view**: Delivery risk flags, blocker alerts, and sprint health indicators
- **In Board view**: Strategy Sidekick conversations enriched with proactive intelligence
- **In Spaces/Portfolio view**: Aggregated health signals, alignment scores, and cross-team dependency alerts

---

## 6. Progressive Trust Model

The AI intelligence system is designed to earn user trust over time, progressively expanding its role from passive observation to active recommendation to (eventually) delegated action.

### Trust Levels

| Level | AI Behavior | User Control | Example |
|---|---|---|---|
| **Level 1: Observer** | Monitors signals; surfaces alerts; provides data | User makes all decisions; AI is informational only | "Here's what we see in customer feedback about Feature X" |
| **Level 2: Advisor** | Provides recommendations with evidence; suggests actions | User approves or rejects recommendations | "We recommend re-prioritizing Initiative Y. Here's why: [evidence]" |
| **Level 3: Collaborator** | Drafts roadmap updates, generates reports, prepares scenarios for review | User reviews and approves AI-generated artifacts | AI drafts weekly status update; PM reviews and sends |
| **Level 4: Delegate** | Executes approved action types autonomously within defined boundaries | User sets boundaries; AI acts within them; exceptions escalated | AI auto-updates delivery dates based on Jira data; PM sets the policy |

### Initial Launch

The system launches at **Level 1 (Observer)** and **Level 2 (Advisor)**, with progressive unlocking of Levels 3 and 4 based on:
- User opt-in
- Demonstrated accuracy of AI recommendations
- Organizational AI governance maturity
- Feature-specific confidence thresholds

---

## 7. Implementation Roadmap for AI Architecture

| Phase | Focus | Key Deliverables |
|---|---|---|
| **Phase 1** | Foundation — Connect signal sources | Miro Insights → Tables enrichment; Jira sync enhancement; basic customer evidence per backlog item |
| **Phase 2** | Intelligence — Launch core agents | Risk Predictor (execution signals); Opportunity Spotter (customer signals); AI Decision Copilot (proactive suggestions); Signal Dashboard |
| **Phase 3** | Strategy — Portfolio intelligence | Alignment Monitor (strategy signals); Scenario Simulator; Cadence Automator; Portfolio-level aggregation; Cross-team dependency detection |
| **Phase 4** | Autonomy — Progressive delegation | Level 3/4 trust capabilities; Autonomous report generation; Delegated status updates; Self-healing roadmaps |


turn the above into slides rendered on a HTML page `i can open in my chrome browser
