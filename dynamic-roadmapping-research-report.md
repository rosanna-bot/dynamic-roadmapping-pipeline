# Dynamic Roadmapping Product: Research Report & Customer Journey Map

> **Prepared for**: Miro Product & Strategy Teams
> **Date**: February 2026
> **Status**: Final Draft

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Market & Competitive Landscape](#2-market--competitive-landscape)
3. [Miro's Current Feature Landscape for Roadmapping](#3-miros-current-feature-landscape-for-roadmapping)
4. [Customer Feedback Synthesis](#4-customer-feedback-synthesis)
5. [Customer Journey Maps](#5-customer-journey-maps)
6. [Solution Recommendations](#6-solution-recommendations)
7. [AI Proactive Intelligence Architecture](#7-ai-proactive-intelligence-architecture)
8. [Implementation Phasing](#8-implementation-phasing)
9. [Key Internal References](#9-key-internal-references)

---

## 1. Executive Summary

Miro has a massive opportunity in the roadmapping and portfolio management space, estimated at **+$1 billion in market potential**. Today, **60% of customers already use Miro for roadmapping**, yet it carries the **highest frustration score across all agile use cases** — only 34% report being very satisfied, and a mere 9.7% are very satisfied with their current solution. At least **$2.7M ARR in customers** are explicitly telling Miro that its roadmapping capabilities are not good enough today.

The product vision is to build a **dynamic, AI-first roadmapping system** that proactively surfaces signals from customer insights, data analytics, industry reports, and Jira execution data to suggest decisions that optimize the roadmap against company strategy and goals.

### Key Opportunity Dimensions

- **Market size**: $1B+ addressable in roadmapping & portfolio management
- **Customer pull**: 60% of Miro's base already uses the product for roadmapping — strong organic demand
- **Pain severity**: Highest frustration score across all agile use cases; massive unmet need
- **Revenue at risk**: $2.7M ARR in vocal, dissatisfied customers
- **Competitive timing**: Productboard deprecating legacy boards; customers actively evaluating alternatives including Miro Insights
- **Differentiation**: No competitor combines visual collaboration freedom with two-way Jira integration, AI-powered customer insights, and infinite canvas flexibility

### Vision Statement

> Build a dynamic, AI-first roadmapping system where proactive intelligence — drawn from customer signals, execution data, market context, and strategic goals — continuously surfaces actionable decisions that keep product roadmaps aligned with reality and company strategy.

This report covers market context, existing Miro assets, customer feedback, persona-specific journey maps, and detailed solution recommendations.

---

## 2. Market & Competitive Landscape

### 2.1 Industry Trends (2025–2026)

The product management landscape is undergoing a fundamental transformation driven by AI adoption:

- **From AI experimentation to Agentic AI**: Product management is shifting from tentative AI experimentation to agentic systems that actively orchestrate workflows and execute tasks autonomously.
- **Broad AI adoption**: ~60% of knowledge workers now have access to sanctioned AI tools; 85% of companies expect to customize autonomous agents within the next 12–18 months.
- **Productivity gains, but not in strategy**: PMs save approximately 2 hours per day through AI automation, but mostly on routine tasks (documentation, meeting summaries). Strategic work — prioritization, deep customer empathy, complex market analysis — remains squeezed and underserved.
- **PM confidence crisis**: 84% of PMs fear their products will fail; only 1 in 5 companies have mature AI governance models, creating both risk and opportunity.
- **Key AI roadmapping capabilities gaining traction**:
  - Automated feedback clustering and theme extraction
  - Intelligent prioritization frameworks (RICE, WSJF) with AI scoring
  - Market trend analysis and competitive monitoring
  - Proactive insight surfacing and anomaly detection

### 2.2 Key Competitors

| Competitor | Strengths | Weaknesses | Miro's Advantage |
|---|---|---|---|
| **Productboard** | Strong feedback management; established PM tool | Deprecating old ARR boards; customers evaluating alternatives | Miro Insights as replacement; visual collaboration layer |
| **Aha! Roadmaps** | Structured portfolio planning; goals alignment | Rigid, non-collaborative; steep learning curve | Visual freedom + infinite canvas flexibility |
| **Jira Product Discovery (JPD)** | Broad scale; native Jira integration | Limited visual collaboration; execution-focused, not strategy | Two-way Jira sync + visual strategy layer |
| **Airfocus / Zeda.io** | Emerging AI-powered prioritization | Smaller ecosystems; limited enterprise adoption | Enterprise scale + existing customer base |
| **Enterpret** | Advanced AI-driven feedback synthesis | Narrow focus on feedback only; no roadmapping | End-to-end from insights to execution |

### 2.3 Miro's Unique Position

Miro has a distinctive advantage that no competitor can match — the combination of:

1. **Visual freedom + collaboration** on an infinite canvas that teams already love and use daily
2. **Jira/Azure DevOps two-way integration** — users with the Jira integration have **4x the active days per month**, proving the value of connected execution data
3. **Miro Insights** as the proactive AI engine for customer intelligence — ingesting from Gong, Qualtrics, Salesforce, support tickets, and more
4. **Existing building blocks**: Timeline widget, Tables, Kanban views that can be unified into a coherent roadmapping system
5. **Unstructured + structured in one place**: The ability to combine whiteboarding and workshops with structured planning, backlogs, timelines, and portfolios — something no pure PM tool can offer

---

## 3. Miro's Current Feature Landscape for Roadmapping

### 3.1 Timeline Widget

The Timeline widget has been launched and is showing strong growth:

- **Agile WACU doubled** since the start of the year, driven primarily by Timeline adoption
- **CSAT: 3.0 / 5.0** (median) — mixed feedback indicating both promise and room for improvement
- **Peak creation**: 37,743 widgets in a single week (+69% vs. GA week)

**Top customer pain points** (from solution review, ranked by frequency):

| Pain Point | % of Respondents |
|---|---|
| No tool that allows them to create the visualisation they need for team and stakeholders | 44% |
| Cannot connect to company goals | 23% |
| Need a tool stakeholders will engage with | 13% |
| Cannot understand if on track | 12% |

**Specific feedback themes** (from weekly CSAT reports):

- **Grouping & hierarchy** (200+ mentions — top pain point): Users need robust grouping, nesting, and hierarchy options to organize complex roadmaps
- **Customization**: Demand for tagging, grouping, custom time scales, and flexible styling
- **Navigation**: Better panning, scrolling, and navigation within large timelines
- **Task management**: Subtasks, completion indicators, progress tracking within timeline items
- **Technical issues**: Flickering and navigation bugs affecting usability
- **Mobile editing**: Limited editing capabilities on mobile devices
- **Sync control**: Ability to toggle off syncing or create snapshots — "If I want to remove stuff from the roadmap when I'm talking to the CEO, I don't want to remove it in Jira too"

### 3.2 Miro Insights (AI Engine)

Miro Insights is positioned as "the proactive AI engine that helps all teams discover, define, and deliver what customers need."

**Current Capabilities**:
- Feedback ingestion from multiple sources: Gong, Qualtrics, Salesforce, support tickets
- Automated clustering and theme extraction
- "Ask AI" exploration for conversational insight discovery
- Weekly Slack summaries of emerging customer themes

**Critical Gap**: Insights is currently **disconnected from Tables/Timeline** — this is the major gap being addressed by the Insights-Driven Roadmapping Evolution initiative. The phased approach to merge Insights + Tables will enable insights-driven prioritization natively in Miro.

### 3.3 Tables + Kanban + Views

- **Tables**: Flexible and deeply integrated in the platform, but currently lacks backlog-specific workflows and Insights enrichment
- **Kanban**: Shows strongest engagement with 9.1% multi-day engagement rate (vs. 5.3% for Table, 5.4% for Timeline); growing share of usage
- **Cross-view usage**: Kanban and Timeline views are often used **in parallel** — teams plan in Kanban and present in Timeline
- **Key request**: Users want contents to **sync between Kanban and Timeline** to reduce manual double-entry

### 3.4 Roadmap Strategy Sidekick (Existing AI Feature)

An AI sidekick already built and powered by Claude 3.7 Sonnet:

- Analyzes existing roadmaps + content on the board
- Compares with customer opportunities from Miro Insights
- Outputs a structured prioritization table with evaluation criteria
- **Conversation starters** include:
  - "Analyze a product roadmap to identify misaligned priorities"
  - "Generate a structured prioritization table"
  - "Challenge current roadmap assumptions"

This is a strong foundation to build upon — the sidekick proves the value of AI-assisted roadmap analysis but currently operates on-demand rather than proactively.

### 3.5 Strategy Pack (Work in Progress)

An in-progress solution targeting Product Leaders and PMs:

- **Concepts include**: Portfolio views in Spaces, Goal management (OKRs), Strategy-to-execution traceability
- **Vision includes**: A "Product Leader Agent" and "Autonomous Planning System"
- **Internal vision statement**: "Agentic Strategy System: A living work graph from company goal down to task level, where autonomous agents execute strategic work, monitor metrics, propose changes, while humans guide and supervise"

---

## 4. Customer Feedback Synthesis

### 4.1 From SFDC Feature Requests, Gong, and Deal Room Analysis

Across enterprise accounts and deal rooms, a consistent theme emerges — customers want Miro to be the **single source of truth** for product planning:

- **E.ON**: Want to display Jira fields (especially epic-level) in timeline views with start/end dates
- **Ubisoft**: "This is exactly what they need" (timeline widget for roadmapping)
- **PWC, Keyloop, Fidelity**: Active roadmapping users with specific requests around cross-team planning and portfolio visibility
- **Multiple accounts**: Actively evaluating switching from Productboard to Miro Insights as Productboard deprecates legacy features

### 4.2 Key Customer Quotes

> "We see strong potential in using Miro's connected AI capabilities — interview sets, prompt preparation, insights extraction, conversion into feature backlogs, and prototyping — all in one place."

> "Each product manager currently uses Miro independently... we lack shared visibility across products and teams, which is why the Miro portfolio functionality looks promising."

> "ProductBoard is deprecating the old ARR boards... we need to test this critically and look at competitive offerings like Miro Insights."

> "We have a general lack of data to support product decisions and want AI to speed up PRD generation, feature alignment, and prioritization."

### 4.3 Core User Pains (from PM Persona Research)

Based on the Insights Use Case Library research, PMs consistently struggle with:

| Pain Category | Description |
|---|---|
| **Decision traceability** | PM struggles to trace decisions back to specific customer feedback |
| **Roadmap currency** | PM struggles to keep roadmap updated as changes occur |
| **Real-time visibility** | PM struggles to maintain accurate real-time visibility into delivery status |
| **Segment freshness** | PM struggles to keep segment analysis updated as new feedback arrives |
| **Idea validation** | PM struggles to validate ideas against actual customer needs |
| **Ad-hoc reporting** | PM responds to frequent ad-hoc questions about roadmap status |
| **Manual reporting** | PM creates separate reports for each audience/segment manually |
| **Status gathering** | PM attends multiple team standups to gather status updates manually |

---

## 5. Customer Journey Maps

### 5.1 Product Leader Journey (AADHYA Persona)

**Goal**: Align portfolio of products with company strategy, ensure teams are building the right things, make fast portfolio-level decisions.

#### Journey Phases

##### Phase 1: Strategy Definition

| Dimension | Details |
|---|---|
| **Current State** | Strategy and goals live in slides, spreadsheets, or Aha! — disconnected from execution. No live link between what the company says it values and what teams are actually building. |
| **Key Pain** | Strategic intent gets lost in translation; teams interpret goals differently without a shared, connected system. |
| **Future State** | Goals and OKRs defined directly in Miro, linked to portfolios and initiatives. AI validates alignment in real-time, flagging when proposed work doesn't connect to active strategic objectives. |

##### Phase 2: Portfolio Oversight

| Dimension | Details |
|---|---|
| **Current State** | Lack shared visibility across products and teams; each PM uses tools independently. Leaders must manually aggregate views across disparate boards, tools, and spreadsheets. |
| **Key Pain** | No single pane of glass for the product portfolio; blind spots on team capacity, cross-team overlap, and resource allocation. |
| **Future State** | Unified portfolio view in Miro Spaces showing all product roadmaps, health signals, and goal alignment. Drill-down from portfolio to individual roadmap to epic with connected context. |

##### Phase 3: Decision Making

| Dimension | Details |
|---|---|
| **Current State** | Leadership over-involvement; last-minute scope changes driven by opinions rather than evidence. Undermines roadmap integrity and team morale. |
| **Key Pain** | Decisions lack grounding in customer evidence and execution reality; HiPPO (Highest-Paid Person's Opinion) dynamics dominate. |
| **Future State** | AI proactively surfaces decision-ready intelligence: "Customer churn signal in Segment X aligns with Initiative Y — recommend re-prioritizing." Leaders make faster, evidence-backed decisions. |

##### Phase 4: Stakeholder Alignment

| Dimension | Details |
|---|---|
| **Current State** | Teams spend hours manually customizing roadmap views for different stakeholders — one for the board, one for engineering, one for sales, one for customers. |
| **Key Pain** | Massive time waste on reformatting; risk of version drift between different presentation layers. |
| **Future State** | Auto-generated views — executive summary, team detail, customer-facing — all derived from one underlying data source. Each view updates automatically as the roadmap evolves. |

##### Phase 5: Progress Tracking

| Dimension | Details |
|---|---|
| **Current State** | Cannot understand if execution is on track; relies on manual status reports from individual PMs. Information is always stale by the time it reaches leadership. |
| **Key Pain** | Leaders are flying blind on delivery; surprises emerge too late to course-correct. |
| **Future State** | Real-time delivery signals from Jira/Azure DevOps feed into a portfolio dashboard. AI flags risks and delays proactively: "Team Alpha's velocity dropped 25% — Q2 deliverable at risk." |

##### Phase 6: Strategy Pivots

| Dimension | Details |
|---|---|
| **Current State** | Shifting product strategy requires cascading changes across multiple tools and teams. Impact analysis is manual and incomplete. |
| **Key Pain** | Strategic pivots are slow and risky because leaders can't see downstream effects. |
| **Future State** | AI simulates the impact of strategy changes across the portfolio. Auto-proposes roadmap adjustments and highlights cascading effects on timelines, dependencies, and customer commitments. |

#### Product Leader Key Pain Points Summary

1. **Shifting product strategy** — leadership over-involvement, last-minute scope changes driven by opinions rather than evidence
2. **Inability to delegate effectively** — struggle to empower product leaders to own pace, problem-solve, and communicate without escalation
3. **Poor cross-functional alignment** — miscommunication, delays, and constant context-switching between product, engineering, and design
4. **Manual view customization** — teams must manually customize roadmap views for different stakeholders (executives need strategy, engineers need details)

---

### 5.2 Product Manager Journey

**Goal**: Build and maintain an evidence-based roadmap that reflects customer needs, company strategy, and execution reality.

#### Journey Phases

##### Phase 1: Discovery & Insights

| Dimension | Details |
|---|---|
| **Current State** | Manually collects and reviews customer feedback from various sources — Zendesk, Salesforce, Gong calls, NPS surveys, support tickets. Synthesis is time-consuming and always incomplete. |
| **Key Pain** | Critical customer signals are missed or arrive too late; PM spends hours on manual aggregation instead of strategic thinking. |
| **Future State** | Miro Insights auto-ingests, clusters, and surfaces relevant feedback in real-time. AI proactively says: "3 enterprise accounts flagged onboarding friction this week — here are the common themes." |

##### Phase 2: Prioritization

| Dimension | Details |
|---|---|
| **Current State** | Struggles to trace decisions back to specific customer feedback. Prioritization lives in spreadsheets with manual scoring frameworks that quickly go stale. |
| **Key Pain** | Prioritization decisions feel arbitrary; difficult to defend trade-offs to stakeholders without concrete customer evidence. |
| **Future State** | Customer-enriched backlog with unified metrics per item: # of customers requesting, customer list, aggregated ARR impact, representative quotes, sentiment score. AI scores items by predicted impact. |

##### Phase 3: Roadmap Creation

| Dimension | Details |
|---|---|
| **Current State** | Creates roadmap in spreadsheets or PM tools; manually updates as priorities shift. The roadmap is often out of date within days of creation. |
| **Key Pain** | Roadmap creation is high-effort, low-durability work; constant manual maintenance erodes PM productivity. |
| **Future State** | Timeline widget auto-populated from the enriched backlog. Drag-and-drop re-prioritization with AI impact warnings: "Moving Initiative X out of Q2 affects 5 enterprise accounts representing $1.2M ARR." |

##### Phase 4: Scenario Planning

| Dimension | Details |
|---|---|
| **Current State** | No way to play with different scenarios without affecting the source of truth. PMs resort to duplicating boards or creating ad-hoc spreadsheet models. |
| **Key Pain** | "What-if" analysis is cumbersome and risky; changes made during exploration accidentally become commitments. |
| **Future State** | "Snapshot mode" — create multiple roadmap scenarios without affecting the source of truth. AI compares trade-offs across scenarios against customer signals and strategic alignment. |

##### Phase 5: Stakeholder Communication

| Dimension | Details |
|---|---|
| **Current State** | Creates separate presentations for different audiences. Responds to frequent ad-hoc questions about roadmap status from sales, executives, and customer success teams. |
| **Key Pain** | Communication overhead consumes a disproportionate amount of PM time; information asymmetry creates misalignment. |
| **Future State** | Tailored views auto-generated from a single source of truth. Embedded in Confluence/Slack for self-serve access. AI-generated summaries answer common questions before they're asked. |

##### Phase 6: Delivery Tracking

| Dimension | Details |
|---|---|
| **Current State** | Attends multiple standups; manually updates tracking spreadsheets; follows up on blockers through Slack and meetings. |
| **Key Pain** | Status gathering is a full-time job on top of the actual PM role; delays in information propagation lead to missed deadlines. |
| **Future State** | Jira/Azure sync shows real-time delivery status directly on the roadmap. AI flags: "Epic X is 2 sprints behind — 3 dependent features affected. Here's the impact on Q2 commitments." |

##### Phase 7: Iteration & Learning

| Dimension | Details |
|---|---|
| **Current State** | Struggles to keep roadmap updated as conditions change; the feedback loop from delivery back to strategy is broken. |
| **Key Pain** | Learning doesn't compound; the same mistakes repeat because insights from one cycle don't flow into the next. |
| **Future State** | AI continuously enriches roadmap items with new customer signals. Proactively suggests: "New competitor launched Feature Y — 12 customers mentioned this in the last 30 days. Consider adding to Q3 evaluation." |

---

## 6. Solution Recommendations

### 6.1 For Product Leaders — Strategic Command Center

Product Leaders need a system that gives them portfolio-level visibility, strategic alignment confidence, and the ability to make fast, evidence-based decisions across their product organization.

#### Recommendation 1: Portfolio Dashboard in Spaces

Dedicated views within Miro Spaces showing all product roadmaps with real-time health signals, goal alignment scores, and delivery status across the organization. Leverages Miro's existing Spaces architecture to provide portfolio-level context without requiring leaders to navigate individual boards.

**Key capabilities**:
- Aggregated view of all product roadmaps with status indicators
- Goal alignment scoring showing how well each initiative maps to company OKRs
- Real-time delivery health signals drawn from Jira/Azure DevOps
- Drill-down capability from portfolio to roadmap to epic with maintained context
- Resource allocation visibility across teams and initiatives

#### Recommendation 2: AI Strategy Alignment Monitor

A proactive AI agent that continuously checks roadmap alignment with OKRs and company goals. It surfaces alerts when initiatives drift from strategy or when market signals suggest pivoting. This builds on the existing "Roadmap Strategy Sidekick" and extends its capabilities to the portfolio level.

**Key capabilities**:
- Continuous monitoring of goal-to-initiative alignment
- Drift detection: alerts when work is being done that doesn't connect to active goals
- Market signal integration: flags when external changes affect strategic assumptions
- Alignment scoring with trend tracking over time
- Automated weekly/monthly alignment reports for leadership review

#### Recommendation 3: Autonomous Scenario Planning

AI simulates the impact of strategy changes across the portfolio. For example: "What if we shift 30% of resources from Feature Area A to B?" The system shows cascading effects on timelines, dependencies, customer impact, and delivery capacity.

**Key capabilities**:
- Multi-scenario modeling with side-by-side comparison
- Cascading impact analysis across teams and timelines
- Customer commitment tracking — which accounts are affected by each scenario
- Capacity and velocity modeling based on historical Jira data
- Risk scoring for each scenario based on execution complexity

#### Recommendation 4: Executive-Ready Auto-Views

One-click generation of strategy-level roadmap views from the same underlying data. Auto-summarized progress, risks, and key decisions needed. Supports presentation mode and export to slides for board and executive meetings.

**Key capabilities**:
- Auto-generated executive summary with key milestones and risks
- Configurable abstraction levels (strategic themes → initiatives → epics)
- Presentation mode optimized for leadership reviews
- Export to slides/PDF with consistent branding
- Embedded roadmap views in Confluence/Notion for async alignment

#### Recommendation 5: Cross-Team Dependency Intelligence

AI proactively identifies hidden dependencies across product teams by analyzing Jira execution data and roadmap overlaps. Alerts leaders before conflicts arise, rather than after they cause delays.

**Key capabilities**:
- Automatic dependency detection from Jira/Azure DevOps data
- Cross-team conflict identification before it impacts delivery
- Dependency visualization on portfolio and roadmap views
- Proactive alerts when dependent work is delayed or re-scoped
- Recommended resolution paths based on priority and impact

#### Recommendation 6: Strategy-to-Execution Traceability

A living work graph from company goal down to task level, aligned with the internal "Agentic Strategy System" vision. Every initiative is visually linked to its strategic rationale and customer evidence, creating an auditable chain from "why" to "what" to "how."

**Key capabilities**:
- Visual goal → initiative → epic → task hierarchy
- Customer evidence linked at every level (from Miro Insights)
- Impact tracing: "Which company goal does this sprint task serve?"
- Orphan detection: work items not connected to any active goal
- Strategic narrative generation: AI explains the "why" behind any piece of work

---

### 6.2 For Product Managers — Evidence-Driven Execution Engine

Product Managers need a system that reduces manual toil, connects customer evidence to every roadmap decision, and keeps their roadmap alive with real-time data.

#### Recommendation 1: Customer-Enriched Backlog

Extend the Insights × Tables integration to auto-enrich every backlog item with customer evidence. This capability is already partially built (V1 in progress) — accelerating to GA is critical.

**Key enrichment per backlog item**:
- Number of customers requesting the feature/improvement
- Customer list with account details and segments
- Aggregated ARR impact across requesting accounts
- Representative customer quotes and feedback excerpts
- Sentiment analysis and urgency scoring
- Trend data: is demand growing, stable, or declining?

#### Recommendation 2: Proactive Signal Dashboard

An AI-powered dashboard that monitors and surfaces signals from four distinct channels, giving PMs a real-time pulse on what matters:

| Signal Source | What It Monitors | Example Alert |
|---|---|---|
| **Customer Insights** | Miro Insights data — feedback trends, NPS shifts, support ticket themes | "Onboarding friction' moved from #5 to #1 pain in the last 30 days" |
| **Execution Data** | Jira/Azure — sprint velocity, epic delays, blocker patterns | "Team Y's velocity dropped 30% — Epic Z at risk" |
| **Industry Reports** | Competitor moves, market trends, analyst briefings | "Competitor launched Feature A — 12 accounts mentioned this" |
| **Analytics** | Product usage data, feature adoption metrics, retention signals | "Feature X adoption stalled at 15% after 60 days — investigate" |

#### Recommendation 3: Smart Timeline with Live Data

Evolve the Timeline widget from a static visualization into a living, data-enriched roadmap:

- **Auto-update from Jira sync**: Real-time delivery status reflected directly on timeline items
- **Risk color-coding**: AI-assessed risk levels based on velocity trends and scope changes (green/yellow/red)
- **Customer demand heatmap**: Visual intensity showing which items have the strongest customer pull (from Insights)
- **Snapshot mode**: Create multiple roadmap scenarios for "what-if" planning without affecting the source of truth
- **Smart time-scale**: Automatic adjustment of granularity based on zoom level (quarters → months → sprints)

#### Recommendation 4: AI Decision Copilot

Proactive, context-aware suggestions surfaced directly in the PM's workflow:

- **Prioritization signals**: "Based on last 30 days of customer feedback, 'onboarding friction' moved from #5 to #1 pain — consider re-prioritizing Initiative X"
- **Delivery risk warnings**: "Sprint velocity for Team Y dropped 30% — Epic Z is at risk of missing Q2 target"
- **Competitive intelligence**: "Competitor launched Feature A — 12 accounts mentioned this in recent calls"
- **Impact quantification**: "Re-prioritizing Initiative X would affect 3 enterprise accounts representing $850K ARR"
- **Strategy alignment**: "Initiative Y has no connection to any active company goal — consider re-evaluating"

#### Recommendation 5: Stakeholder-Adaptive Views

Auto-generate tailored roadmap views from one source of truth, each optimized for its audience:

| Audience | View Characteristics |
|---|---|
| **Engineering team** | Detailed epics, sprint assignments, technical dependencies, capacity allocation |
| **Executives** | Strategic themes, goal alignment indicators, key milestones, risk summary |
| **Customer-facing** | Public roadmap with idea status updates, expected timelines, completed features |
| **Sales / CS** | Customer-specific views showing requested features, their status, and expected delivery |

#### Recommendation 6: Connected Workflow — Discovery to Delivery

A seamless, end-to-end flow connecting every phase of product work:

1. **Customer insight clustering** in Miro Insights → automated theme extraction and opportunity identification
2. **Opportunity scoring** in the enriched backlog (Tables) → evidence-weighted prioritization with AI assistance
3. **Visual roadmapping** (Timeline) → drag-and-drop planning with impact awareness
4. **Delivery tracking** (Jira-synced Kanban) → real-time execution status with risk flagging
5. **Retrospective and learning loop** → outcomes feed back into Insights, closing the cycle

---

## 7. AI Proactive Intelligence Architecture

The core differentiator of Miro's dynamic roadmapping system is **proactive AI** — intelligence that doesn't wait for queries but continuously monitors, analyzes, and surfaces actionable information to keep roadmaps aligned with reality.

### 7.1 Signal Sources

The AI system draws from five distinct signal categories to build a comprehensive picture of strategic context:

#### Customer Voice
- **Sources**: Miro Insights (ingesting from Gong calls, Salesforce notes, Zendesk tickets, NPS surveys, app store reviews, support conversations)
- **Signals produced**: Emerging themes, feedback volume trends, sentiment shifts, segment-level patterns, specific customer requests and their frequency
- **Update cadence**: Real-time ingestion with daily clustering and weekly trend analysis

#### Execution Reality
- **Sources**: Jira/Azure DevOps (sprint data, epic progress, commit history, PR activity)
- **Signals produced**: Sprint velocity trends, epic completion forecasts, blocker patterns, capacity utilization, scope change frequency
- **Update cadence**: Real-time sync for status; daily aggregation for trends and forecasts

#### Market Context
- **Sources**: Industry reports, competitor tracking services, analyst briefings, news feeds (ingested or linked)
- **Signals produced**: Competitor feature launches, market trend shifts, regulatory changes, technology disruptions
- **Update cadence**: As available; AI matches against current roadmap items for relevance

#### Business Metrics
- **Sources**: Usage analytics platforms, revenue dashboards, churn tracking systems, expansion/contraction data
- **Signals produced**: Feature adoption rates, retention signals, revenue impact estimates, churn risk indicators
- **Update cadence**: Daily metrics ingestion; weekly trend analysis

#### Strategy Artifacts
- **Sources**: Company OKRs, department goals, initiative definitions, strategic narrative documents (defined in Miro)
- **Signals produced**: Alignment scores, goal coverage maps, strategic drift indicators, priority hierarchy
- **Update cadence**: Updated when goals or initiatives change; continuous alignment scoring

### 7.2 AI Agent Behaviors

Five specialized AI agent behaviors work together to transform raw signals into actionable roadmap intelligence:

#### 1. Alignment Monitor
- **Function**: Continuously checks if roadmap items trace back to active goals
- **Triggers**: Alerts when orphaned work is detected (items not connected to any goal), when goal drift is identified (work progressing that no longer serves active objectives), or when new goals are created without corresponding roadmap coverage
- **Output**: Alignment score per initiative, weekly alignment trend report, specific recommendations for re-alignment

#### 2. Risk Predictor
- **Function**: Analyzes Jira execution patterns to predict delivery risks before they materialize
- **Triggers**: Velocity drops exceeding threshold, scope changes mid-sprint, blocker accumulation, dependency delays in upstream teams
- **Output**: Risk score per epic/initiative, projected delivery date ranges, recommended mitigations, escalation alerts to leadership views

#### 3. Opportunity Spotter
- **Function**: Clusters emerging customer themes from Insights and matches them against current roadmap coverage
- **Triggers**: New theme emerging with significant volume, existing theme experiencing rapid growth, competitive move creating new customer demand, underserved segment identified
- **Output**: Opportunity cards with customer evidence, gap analysis against current roadmap, suggested priority and timing, ARR impact estimate

#### 4. Scenario Simulator
- **Function**: When strategy changes are proposed, automatically models cascading impact across the portfolio
- **Triggers**: User initiates "what-if" scenario, leadership requests resource reallocation, external event requires strategy adjustment
- **Output**: Side-by-side scenario comparison, timeline impact visualization, customer commitment risk assessment, team capacity modeling, recommended path with rationale

#### 5. Cadence Automator
- **Function**: Auto-generates recurring roadmap communications and planning inputs
- **Triggers**: Time-based cadence (weekly, monthly, quarterly)
- **Output**:
  - **Weekly**: Roadmap status summary with top risks and signals
  - **Monthly**: Strategy alignment report with trend analysis
  - **Quarterly**: Planning input package with customer evidence summary, execution retrospective, and recommended priorities for next quarter

### 7.3 Architecture Principles

1. **Proactive, not reactive**: The system surfaces insights without being asked, operating as a continuous intelligence layer
2. **Evidence-grounded**: Every suggestion or alert is traceable to specific data points — customer quotes, velocity metrics, competitor actions
3. **Human-in-the-loop**: AI recommends; humans decide. The system never makes autonomous changes to the roadmap without PM or leader approval
4. **Composable intelligence**: Individual agent behaviors can be combined for complex analyses (e.g., Opportunity Spotter + Scenario Simulator = "What if we prioritize this emerging theme?")
5. **Progressive trust**: Start with alerts and recommendations; evolve toward delegated actions as users build confidence in the system

---

## 8. Implementation Phasing

### Phase 1: Now — Building Foundations
*Focus: Connect existing assets into a coherent roadmapping workflow*

- Insights-driven prioritization in Tables — enriched backlog GA
- Timeline + Kanban view unification with synced content
- Customer evidence enrichment per backlog item (# customers, ARR, quotes)
- Basic Jira sync improvements for timeline items

### Phase 2: Next — Intelligence Layer
*Focus: Add proactive AI and live data to the roadmapping experience*

- Proactive AI signal dashboard with four-channel monitoring
- Smart Timeline with live Jira data and risk color-coding
- Scenario planning mode (snapshot/what-if)
- Stakeholder-adaptive view generation
- AI Decision Copilot with contextual suggestions

### Phase 3: Later — Strategic Platform
*Focus: Extend to portfolio level and autonomous planning capabilities*

- Portfolio-level dashboard for leaders in Spaces
- Autonomous planning agents (Alignment Monitor, Risk Predictor, Opportunity Spotter)
- Strategy-to-execution work graph with full traceability
- Cross-team dependency intelligence
- Cadence Automator for recurring communications
- Scenario Simulator for portfolio-level what-if analysis

---

## 9. Key Internal References

| Document | Owner | Last Updated |
|---|---|---|
| [Insights-Driven Roadmapping Evolution](https://miro.com/app/board/uXjVGKHY_h0=) | Lauren Brucato | Feb 4, 2026 |
| [Strategy Pack Solution Review](https://miro.com/app/board/uXjVJiEOXK0=) | Robert Kortenoeven | Feb 4, 2026 |
| [FY26 Miro Insights Roadmap](https://miro.com/app/board/uXjVIuicX1U=) | Lauren Brucato | — |
| [Miro Insights Use Case Library](https://miro.com/app/board/uXjVJfuC4S4=) | Lauren Brucato | — |
| [Timeline Widget Solution Review](https://miro.com/app/board/uXjVKee8xlE=) | Rosanna Knottenbelt | — |
| [Agile X Tables FY26 Early Thoughts](https://miro.com/app/board/uXjVLPeoYHQ=) | Rosanna Knottenbelt | — |
| [FY26 Agile Reviews](https://miro.com/app/board/uXjVL43-wlM=) | Vanessa Lee | — |
| [Roadmap Strategy Sidekick](https://miro.com/app/board/uXjVJB7YiW8=) | Dana Griffin | — |
| [FY25 Agile Collaboration Backlog](https://miro.com/app/board/uXjVKd-IV-s=) | Rosanna Knottenbelt | — |
