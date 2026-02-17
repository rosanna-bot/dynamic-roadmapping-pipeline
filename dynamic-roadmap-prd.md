# Dynamic Roadmap V1 — Product Requirements Document

> **Product**: Miro Dynamic Roadmap
> **Version**: 1.0 (MVP)
> **Date**: February 2026
> **Author**: Product Team
> **Status**: Draft

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Problem Statement](#2-problem-statement)
3. [User Stories & Personas](#3-user-stories--personas)
4. [Feature Scope — V1](#4-feature-scope--v1)
5. [AI Intelligence Layer](#5-ai-intelligence-layer)
6. [Data & Integrations](#6-data--integrations)
7. [Information Architecture](#7-information-architecture)
8. [Non-Functional Requirements](#8-non-functional-requirements)
9. [Success Metrics](#9-success-metrics)
10. [Phasing & Dependencies](#10-phasing--dependencies)
11. [Open Questions](#11-open-questions)

---

## 1. Executive Summary

### Vision

Build a dynamic, AI-first roadmapping system within Miro where proactive intelligence — drawn from customer signals, execution data, market context, and strategic goals — continuously surfaces actionable decisions that keep product roadmaps aligned with reality and company strategy.

### Why Now

- **$1B+ addressable market** in roadmapping and portfolio management
- **60% of Miro customers already use the product for roadmapping**, yet it has the **highest frustration score** across all agile use cases (only 34% very satisfied)
- **$2.7M ARR in customers** explicitly telling Miro that its roadmapping capabilities are not good enough
- **Productboard is deprecating legacy ARR boards** — customers are actively evaluating alternatives including Miro Insights
- **No competitor combines** visual collaboration, two-way Jira integration, AI-powered customer insights, and infinite canvas flexibility

### Target Personas

| Persona | Role | Primary Need |
|---|---|---|
| **Product Manager (PM)** | Builds and maintains roadmaps, prioritizes features, communicates plans | Evidence-driven execution: reduce manual toil, connect customer evidence to every decision, keep roadmaps alive with real-time data |
| **Product Leader** | Oversees portfolio of products, ensures strategic alignment, makes resource allocation decisions | Strategic command center: portfolio visibility, alignment confidence, fast evidence-based decisions |

### V1 Success Criteria

- PM can create a roadmap connected to Jira and Miro Insights in under 5 minutes
- Roadmap table shows enriched customer data (ARR, company count, feedback) with zero manual entry
- AI Pulse surfaces at least 3 actionable insights per week
- 80%+ of roadmap items traceable to customer evidence within 30 days

---

## 2. Problem Statement

### Core Pain Points (from PM Persona Research)

| Pain | Description | Severity |
|---|---|---|
| **Decision traceability** | PM struggles to trace decisions back to specific customer feedback. Prioritization feels arbitrary and hard to defend. | Critical |
| **Roadmap currency** | PM struggles to keep roadmap updated as changes occur. Roadmap is stale within days of creation. | Critical |
| **Real-time visibility** | PM struggles to maintain accurate real-time visibility into delivery status. Information is always stale by the time it reaches stakeholders. | High |
| **Manual signal gathering** | PM spends 4-6 hours per week manually collecting feedback from Gong, Salesforce, Zendesk, NPS surveys. Critical signals are missed. | High |
| **Idea validation** | PM struggles to validate ideas against actual customer needs. No quantified demand data per backlog item. | High |
| **Ad-hoc reporting** | PM responds to frequent ad-hoc questions about roadmap status from sales, executives, and customer success teams. | Medium |
| **Manual reporting** | PM creates separate reports for each audience/segment manually. 5-8 hours per week on communication overhead. | Medium |

### The Gap

Today's roadmapping workflow is **fragmented, manual, and reactive**:

1. Customer feedback lives in Gong/Salesforce/Zendesk — disconnected from the roadmap
2. Execution status lives in Jira — disconnected from the roadmap
3. Market intelligence is ad-hoc — not systematically connected to decisions
4. Strategy documents live in slides/spreadsheets — disconnected from execution
5. The PM is the manual integration layer, spending more time gathering data than making decisions

### The Opportunity

A dynamic roadmap that **automatically connects** all five signal sources and **proactively surfaces** intelligence eliminates the manual integration burden and puts evidence at the center of every decision.

---

## 3. User Stories & Personas

### 3.1 Product Manager Stories

#### Discovery & Insights
- As a PM, I want to see AI-curated customer insights relevant to my roadmap items so that I can prioritize based on real customer demand, not assumptions.
- As a PM, I want each backlog item enriched with customer count, ARR, and representative quotes so that I can defend prioritization decisions with evidence.

#### Roadmap Creation
- As a PM, I want to create a new product roadmap by describing what I'm building and having AI suggest relevant data sources to connect, so that I can get started quickly without manual setup.
- As a PM, I want to import items from my Jira project directly into the roadmap with two-way sync, so that execution status stays current automatically.

#### Roadmap Management
- As a PM, I want to view my roadmap as a table, timeline, or kanban board, so that I can switch views based on context (planning vs. presenting vs. tracking).
- As a PM, I want to score items using Impact, Confidence, and Effort (ICE) with an auto-calculated composite score, so that I have a consistent prioritization framework.
- As a PM, I want to filter the roadmap by status, priority, assignee, company, and ICE score, so that I can focus on specific subsets.

#### Record Detail
- As a PM, I want to click a roadmap item and see its details, customer signals, and comments in a side panel, so that I have full context without leaving the roadmap view.
- As a PM, I want to see Jira fields (sprint, story points, epic) for synced items, so that I understand execution context alongside product context.

#### Ideas Management
- As a PM, I want a separate "Ideas Backlog" section where pre-committed ideas live with the same enrichment and scoring as roadmap items, so that I can evaluate ideas before committing them.

### 3.2 Product Leader Stories

#### Pulse & Intelligence
- As a Product Leader, I want an AI-curated Pulse view that shows the most important insights, competitive threats, customer signals, and suggested actions, so that I always know what needs attention.
- As a Product Leader, I want the AI to alert me when customer feedback patterns shift or competitors make moves, so that I can respond quickly.

#### Market & Analytics
- As a Product Leader, I want a Market Signals section that tracks competitor launches, market trends, and regulatory changes, so that I can factor external context into roadmap decisions.
- As a Product Leader, I want an Analytics section showing product usage data, feature adoption, and satisfaction metrics, so that I can understand whether shipped features are meeting their goals.

---

## 4. Feature Scope — V1

### 4.1 Entry Point: Create Product Roadmap from Spaces

**Description**: Add "Product Roadmap" as a new creation option in the Miro Spaces overview alongside existing options (Blank board, Project, From template).

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.1.1 | Add "Product Roadmap" option to the "+ Create new" dropdown in Spaces overview | P0 |
| 4.1.2 | Product Roadmap option should be visually distinguished (highlighted/featured) to drive discovery | P1 |
| 4.1.3 | Clicking "Product Roadmap" opens the AI-powered creation dialog (4.2) | P0 |

**Wireframe Reference**: Screen 1 — Spaces Overview + Create New

---

### 4.2 AI-Powered Roadmap Creation Dialog

**Description**: A modal dialog where the user names their roadmap and describes what they want to build via an AI chat interface. The AI processes the description and suggests relevant data sources to connect.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.2.1 | Modal with "Roadmap name" text input field | P0 |
| 4.2.2 | AI chat text area: "Tell us about what you want to build a roadmap for..." | P0 |
| 4.2.3 | AI processes the description and suggests relevant Jira projects, strategy docs, Miro boards, and analytics tools to connect | P0 |
| 4.2.4 | Suggestions shown as badges below the description with confirm/dismiss actions | P1 |
| 4.2.5 | "Add collaborators" section to invite team members | P1 |
| 4.2.6 | "Create roadmap" button creates the Product Roadmap Space and launches onboarding (4.5) | P0 |
| 4.2.7 | AI suggestions should be based on the user's Miro workspace content and connected integrations | P1 |

**Wireframe Reference**: Screen 2 — Roadmap Creation Dialog

---

### 4.3 Product Roadmap Space Structure

**Description**: Creating a roadmap generates a new Product Roadmap Space with a persistent left sidebar navigation organized into three sections: top-level Pulse, Plan (Roadmap, Ideas Backlog), and Signals (Market, Analytics).

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.3.1 | Product Roadmap Space uses Miro's yellow sidebar design pattern | P0 |
| 4.3.2 | Sidebar top section: "Pulse" with notification badge showing count of new insights | P0 |
| 4.3.3 | Sidebar "Plan" section with two sub-items: "Roadmap" and "Ideas Backlog" | P0 |
| 4.3.4 | Sidebar "Signals" section with two sub-items: "Market" and "Analytics" | P0 |
| 4.3.5 | Clicking any sidebar item navigates to that section's full-screen view | P0 |
| 4.3.6 | Top bar shows Miro logo, breadcrumb (Product Roadmap > [Roadmap Name]), and classification badge | P0 |
| 4.3.7 | User lands on Pulse section by default when entering the space | P0 |

**Wireframe Reference**: Screens 3-8 (all screens show this layout)

---

### 4.4 Pulse View — AI-Curated Insights Overview

**Description**: The default landing view showing a grid of AI-curated intelligence cards covering the most important things the PM/leader needs to know right now. Content is dynamically generated and refreshed by the AI layer.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.4.1 | "Pulse Summary" card (full-width) with 3-5 bullet-point insights, each with an emoji severity indicator | P0 |
| 4.4.2 | "Competitive Threats" card showing recent competitor moves relevant to this roadmap, with impact tags (High/Medium/Low) | P0 |
| 4.4.3 | "Top Customer Insights" card showing top 3 customer feedback themes with account count, ARR, and trend direction | P0 |
| 4.4.4 | "Suggested Actions" card with AI recommendations, each tagged by action type (Reprioritize, Investigate, Respond, etc.) | P0 |
| 4.4.5 | "Roadmap Health" card showing item count breakdown by status (On track / At risk / Blocked) | P1 |
| 4.4.6 | "Execution Snapshot" card showing sprint velocity, blockers count, and next milestone from Jira sync | P1 |
| 4.4.7 | All cards are clickable and expand to more detail or navigate to relevant sections | P1 |
| 4.4.8 | Pulse content refreshes at least daily; critical alerts surface in real-time | P0 |

**Wireframe Reference**: Screen 4 — Pulse (Populated)

---

### 4.5 AI Sidekick — First-Time Onboarding

**Description**: When the user first lands on a newly created Product Roadmap Space, a full-screen AI Sidekick panel overlays the Pulse view, guiding the user to connect relevant artifacts (data sources) to build their roadmap.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.5.1 | Full-screen overlay panel with AI branding (gradient purple header, sparkle icon) | P0 |
| 4.5.2 | Header: "Connect your artifacts — Help me build your roadmap by connecting relevant data sources" | P0 |
| 4.5.3 | List of suggested artifacts based on the description provided at creation time | P0 |
| 4.5.4 | Each suggestion shows: icon, title, description, and "Connect" / "Skip" buttons | P0 |
| 4.5.5 | Suggested artifact types: Jira project, Strategy document, Miro board, Analytics tool, Miro Insights workspace | P0 |
| 4.5.6 | "Skip for now" button to dismiss the sidekick and proceed to an empty Pulse view | P1 |
| 4.5.7 | "Connect selected & build roadmap" button triggers data ingestion and begins populating Pulse, Roadmap, and Signals | P0 |
| 4.5.8 | AI Sidekick remains available as a conversational copilot (accessible via button) after onboarding for ongoing refinement | P2 |

**Wireframe Reference**: Screen 3 — Pulse + AI Sidekick

---

### 4.6 Roadmap Table View

**Description**: Full-screen data table showing all roadmap items with core fields, ICE scoring, and AI-enriched columns from Miro Insights. Supports Jira-synced items with visual indicators.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.6.1 | View switcher tabs at the top: Table (default) / Timeline / Kanban | P0 |
| 4.6.2 | Table columns — Core: Row #, Title, Description, Status, Priority, Assignee | P0 |
| 4.6.3 | Table columns — Scoring: Impact (1-10), Confidence (0-1), Effort (1-10), ICE Score (auto-calculated: I x C x E) | P0 |
| 4.6.4 | Table columns — Enriched (read-only, from Miro Insights): # Mentions, Est. Revenue Impact, Company Names (as pill tags) | P0 |
| 4.6.5 | Enriched column headers have a visual indicator (sparkle icon + orange color) with tooltip "Enriched fields are read-only" | P1 |
| 4.6.6 | Jira-synced rows display a Jira icon (blue badge) to the right of the title | P0 |
| 4.6.7 | Clicking a row opens the Record Detail Side Panel (4.9) | P0 |
| 4.6.8 | Table is sortable by any column (click column header to sort) | P1 |
| 4.6.9 | Table header row is sticky on scroll | P1 |
| 4.6.10 | Status values: To do, In progress, Done, Blocked | P0 |
| 4.6.11 | Priority values: High (red), Medium (yellow), Low (green) | P0 |
| 4.6.12 | Filter button in top bar opens the Filter Panel (4.10) | P0 |
| 4.6.13 | Item count displayed next to view tabs | P2 |

**Wireframe Reference**: Screen 5 — Roadmap Table View

---

### 4.7 Timeline View

**Description**: Same roadmap data rendered as a Gantt-style horizontal timeline. Bars are colored by status, show Jira icons for synced items, and display ICE scores.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.7.1 | Horizontal time axis with configurable granularity (months/quarters) | P0 |
| 4.7.2 | Each roadmap item rendered as a horizontal bar spanning its start-to-due-date range | P0 |
| 4.7.3 | Bars colored by status: In progress (accent purple), To do (green), Blocked (orange), Done (gray) | P0 |
| 4.7.4 | Jira icon displayed on bars for synced items | P1 |
| 4.7.5 | ICE score displayed as text label on each bar | P1 |
| 4.7.6 | Risk indicator (warning icon) on at-risk items | P1 |
| 4.7.7 | Item labels in a fixed left column with the timeline scrolling horizontally | P0 |
| 4.7.8 | Clicking a bar opens the same Record Detail Side Panel as the table view | P0 |
| 4.7.9 | View switcher tabs at top match the table view (Table / Timeline / Kanban) | P0 |

**Wireframe Reference**: Screen 7 — Timeline View

---

### 4.8 Kanban View

**Description**: Same roadmap data rendered as a kanban board with columns per status. Cards show title, description excerpt, ICE score, and enriched data.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.8.1 | Columns for each status: To do, In progress, Done, Blocked | P0 |
| 4.8.2 | Column headers show item count per status | P1 |
| 4.8.3 | Cards show: title (with Jira icon if synced), description excerpt, ICE score badge, priority tag, and company pills | P0 |
| 4.8.4 | Cards are draggable between columns to update status | P1 |
| 4.8.5 | Clicking a card opens the Record Detail Side Panel | P0 |
| 4.8.6 | View switcher tabs at top match other views | P0 |

---

### 4.9 Record Detail Side Panel

**Description**: A slide-in right panel that appears when clicking a roadmap item from any view (table, timeline, or kanban). Contains three tabs: Details, Customer Signals, and Comments.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.9.1 | Panel slides in from the right, 480px wide, with close button | P0 |
| 4.9.2 | Header shows item title and Jira icon (if synced) | P0 |
| 4.9.3 | Three tabs: "Details", "Customer Signals", "Comments" | P0 |

#### Details Tab

| Req ID | Requirement | Priority |
|---|---|---|
| 4.9.4 | Displays all core fields: Title, Function, Status, Priority, Assignee, Start Date, Due Date | P0 |
| 4.9.5 | Displays scoring fields: Impact, Confidence, Effort, ICE Score | P0 |
| 4.9.6 | For Jira-synced items: additional section showing Jira Key, Sprint, Story Points, Epic, Parent | P0 |
| 4.9.7 | Fields are editable (except ICE Score which is computed, and Jira fields which sync from Jira) | P1 |

#### Customer Signals Tab

| Req ID | Requirement | Priority |
|---|---|---|
| 4.9.8 | AI-generated summary paragraph describing the customer signal for this item | P0 |
| 4.9.9 | Impact estimates: Total Mentions, Unique Customers, Est. Revenue Impact — displayed as 3-column stat grid | P0 |
| 4.9.10 | Top impacted companies as pill tags with "+N" overflow | P0 |
| 4.9.11 | Feedback cards showing: type badge (Problem / Request / Insight), star rating, quote text, author, and date | P0 |
| 4.9.12 | Feedback filterable by type (All / Problem / Request / Insight) | P2 |

#### Comments Tab

| Req ID | Requirement | Priority |
|---|---|---|
| 4.9.13 | Threaded comment list with avatar, author name, timestamp, and comment text | P0 |
| 4.9.14 | "Add a comment" text area with submit button at the bottom | P0 |
| 4.9.15 | Comments support @mentions of team members | P2 |

**Wireframe Reference**: Screen 6 — Record Detail Side Panel

---

### 4.10 Filter Panel

**Description**: A sidebar panel that opens from the right side of the table view, allowing multi-field filtering.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.10.1 | Filter button in the top bar opens/closes the filter panel | P0 |
| 4.10.2 | Filter by Status (checkboxes: To do, In progress, Done, Blocked) | P0 |
| 4.10.3 | Filter by Priority (checkboxes: High, Medium, Low) | P0 |
| 4.10.4 | Filter by Assignee (checkboxes per team member) | P1 |
| 4.10.5 | Filter by Jira Sync (checkbox: "Jira synced only") | P1 |
| 4.10.6 | Filter by ICE Score range (> 30 High, 15-30 Medium, < 15 Low) | P1 |
| 4.10.7 | Filter by Company (checkboxes per company from enriched data) | P1 |
| 4.10.8 | Applied filters immediately update the table view | P0 |
| 4.10.9 | "Clear all" button to reset all filters | P1 |

**Wireframe Reference**: Screen 5 — Roadmap Table View (filter panel)

---

### 4.11 Ideas Backlog

**Description**: A separate table view identical in structure to the Roadmap table but containing pre-committed ideas under evaluation. All items have status "Ideas Backlog".

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.11.1 | Accessible via "Ideas Backlog" in the sidebar under "Plan" | P0 |
| 4.11.2 | Same table columns as Roadmap: Title, Description, Status (always "Ideas Backlog"), Impact, Confidence, Effort, ICE Score, and enriched columns | P0 |
| 4.11.3 | "+ Add idea" button to create new idea items | P0 |
| 4.11.4 | Clicking an idea opens the same Record Detail Side Panel | P0 |
| 4.11.5 | Ability to promote an idea to the Roadmap (changes status and moves it to the Roadmap view) | P1 |
| 4.11.6 | Description text: "Pre-committed ideas under evaluation. Promote to Roadmap when ready." | P1 |

**Wireframe Reference**: Screen 8 — Ideas Backlog

---

### 4.12 Market Signals Section

**Description**: A dedicated section showing competitive intelligence, market trends, and regulatory changes. Replicates the Market Signals view pattern from the existing Product Intelligence Dashboard.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.12.1 | Accessible via "Market" in the sidebar under "Signals" | P0 |
| 4.12.2 | AI-generated "Market Intelligence TL;DR" card with top 3-5 market insights, each with a severity indicator (red/yellow/green dot) | P0 |
| 4.12.3 | "Competitive Recommendations" section with numbered AI recommendations | P1 |
| 4.12.4 | Competitive threat cards showing: competitor name, launch date, description, impact level, screenshots where available | P0 |
| 4.12.5 | Feature comparison matrix: competitor vs. Miro across key capabilities | P2 |
| 4.12.6 | Filter by use case / relevance to roadmap items | P2 |
| 4.12.7 | AI automatically matches market signals against current roadmap items and highlights overlaps | P1 |

---

### 4.13 Analytics Section

**Description**: A dedicated section showing product usage data, feature adoption metrics, and satisfaction scores. Replicates the Analytics view pattern from the existing Product Intelligence Dashboard.

**Requirements**:

| Req ID | Requirement | Priority |
|---|---|---|
| 4.13.1 | Accessible via "Analytics" in the sidebar under "Signals" | P0 |
| 4.13.2 | AI-generated "Weekly Pulse TL;DR" summary of key analytics insights | P0 |
| 4.13.3 | MAU/WAU stat tiles for relevant product features with month-over-month and 6-month-average deltas | P0 |
| 4.13.4 | WAU trend charts (last 12 weeks) with enterprise vs. non-enterprise breakdown | P1 |
| 4.13.5 | In-product feedback section showing CSAT scores, top "liked" themes, and top "lacked" themes per feature | P1 |
| 4.13.6 | AI-generated recommendations based on analytics data (e.g., "Fix X bug to lift CSAT by Y") | P1 |
| 4.13.7 | Live data indicator showing data source (e.g., "Live from Snowflake") | P2 |

---

## 5. AI Intelligence Layer

The Dynamic Roadmap V1 includes a foundational AI intelligence layer that powers the Pulse view, enriches roadmap items, and generates signal content. For V1, the following agent behaviors are scoped:

### 5.1 Opportunity Spotter (V1 Scope)

| Attribute | V1 Scope |
|---|---|
| **Function** | Clusters customer feedback from Miro Insights and matches against roadmap items to identify gaps and emerging themes |
| **Primary signals** | Customer Voice (Miro Insights), Business Metrics |
| **V1 outputs** | Enriched columns on roadmap items (# Mentions, ARR, Companies); Customer Signals tab content; Pulse "Top Customer Insights" card |
| **What's deferred to V2** | Automated opportunity cards with competitive context; proactive theme detection without manual prompting |

### 5.2 Risk Predictor (V1 Scope)

| Attribute | V1 Scope |
|---|---|
| **Function** | Analyzes Jira execution data to surface delivery risks |
| **Primary signals** | Execution Reality (Jira sync data — velocity, blockers, scope) |
| **V1 outputs** | Pulse "Execution Snapshot" card; risk indicators on timeline bars; at-risk count in "Roadmap Health" card |
| **What's deferred to V2** | Predictive delivery date ranges with confidence intervals; root cause analysis; escalation to leadership views |

### 5.3 Cadence Automator (V1 Scope — Lite)

| Attribute | V1 Scope |
|---|---|
| **Function** | Generates the daily/weekly Pulse summary content |
| **Primary signals** | All connected sources |
| **V1 outputs** | Pulse Summary card content; suggested actions |
| **What's deferred to V2** | Automated Slack digests; monthly strategy alignment reports; quarterly planning packages |

### Deferred to V2+

- **Alignment Monitor**: Goal-to-initiative alignment scoring, orphan detection, drift alerts
- **Scenario Simulator**: Multi-scenario modeling with cascading impact analysis
- **Full Cadence Automator**: Automated weekly/monthly/quarterly reports and communications
- **Progressive Trust Model**: Levels 3-4 (Collaborator, Delegate) — AI-generated artifacts and autonomous actions

---

## 6. Data & Integrations

### 6.1 Jira Two-Way Sync

| Requirement | Details |
|---|---|
| **Sync scope** | Epics, stories, and tasks from connected Jira project(s) |
| **Direction** | Two-way: status changes in Miro reflect in Jira and vice versa |
| **Fields synced from Jira** | Key, Status, Sprint, Story Points, Epic Link, Assignee, Summary, Description |
| **Fields synced to Jira** | Status changes, priority updates |
| **Sync frequency** | Real-time for status changes; polling every 5 minutes for other fields |
| **Visual indicator** | Blue Jira icon badge on synced items in all views |

### 6.2 Miro Insights Integration

| Requirement | Details |
|---|---|
| **Connection** | Link Miro Insights workspace to Product Roadmap Space |
| **Data consumed** | Customer feedback themes, account mentions, ARR data, representative quotes, sentiment scores |
| **Enrichment target** | Roadmap items and Ideas Backlog items — enriched columns populated automatically |
| **Update frequency** | Daily re-enrichment; real-time for new high-priority signals |
| **Display** | Enriched columns in table (read-only), Customer Signals tab in detail panel, Pulse cards |

### 6.3 Strategy Documents

| Requirement | Details |
|---|---|
| **Supported formats** | Miro boards, Google Docs, Confluence pages (linked) |
| **AI processing** | Extract goals, OKRs, and strategic themes from linked documents |
| **Usage** | AI references strategy context when generating Pulse content and suggested actions |

### 6.4 Analytics Tools

| Requirement | Details |
|---|---|
| **Supported platforms** | Amplitude, Mixpanel, Snowflake (via API) |
| **Data consumed** | Feature adoption metrics, WAU/MAU, session data, retention, CSAT |
| **Display** | Analytics section stat tiles and charts; Pulse analytics insights |

---

## 7. Information Architecture

### 7.1 Space Structure

```
Product Roadmap Space
├── Pulse (default landing)
│   ├── TL;DR Summary
│   ├── Competitive Threats
│   ├── Customer Insights
│   ├── Suggested Actions
│   ├── Roadmap Health
│   └── Execution Snapshot
├── Plan
│   ├── Roadmap
│   │   ├── Table View (default)
│   │   ├── Timeline View
│   │   └── Kanban View
│   └── Ideas Backlog
│       └── Table View
└── Signals
    ├── Market
    │   ├── Market TL;DR
    │   ├── Competitive Threats
    │   └── Feature Comparison
    └── Analytics
        ├── Analytics TL;DR
        ├── Usage Stats
        ├── Trend Charts
        └── Feedback Themes
```

### 7.2 Data Model — Roadmap Item

| Field | Type | Source | Editable |
|---|---|---|---|
| Title | Text | Manual / Jira sync | Yes |
| Description | Rich text | Manual / Jira sync | Yes |
| Status | Enum (To do, In progress, Done, Blocked, Ideas Backlog) | Manual / Jira sync | Yes |
| Priority | Enum (High, Medium, Low) | Manual | Yes |
| Assignee | User reference | Manual / Jira sync | Yes |
| Function | Tag | Manual | Yes |
| Start Date | Date | Manual | Yes |
| Due Date | Date | Manual | Yes |
| Impact | Integer (1-10) | Manual | Yes |
| Confidence | Decimal (0-1) | Manual | Yes |
| Effort | Integer (1-10) | Manual | Yes |
| ICE Score | Decimal | Computed (I x C x E) | No (auto) |
| Jira Key | Text | Jira sync | No |
| Sprint | Text | Jira sync | No |
| Story Points | Integer | Jira sync | No |
| Epic | Text | Jira sync | No |
| # Mentions | Integer | Miro Insights (enriched) | No |
| Est. Revenue Impact | Currency | Miro Insights (enriched) | No |
| Company Names | Tag list | Miro Insights (enriched) | No |
| # Companies | Integer | Miro Insights (enriched) | No |
| Sentiment | Score + label | Miro Insights (enriched) | No |
| Customer Quotes | Text list | Miro Insights (enriched) | No |

### 7.3 Relationships

- **Roadmap Item <-> Jira Issue**: One-to-one via Jira Key (two-way sync)
- **Roadmap Item <-> Insights Theme**: Many-to-many (an item can relate to multiple customer themes; a theme can relate to multiple items)
- **Roadmap Item -> Ideas Backlog Item**: Promotion relationship (Ideas Backlog items can be promoted to Roadmap items)
- **Roadmap Space -> Signal Sources**: One-to-many (a space connects to multiple Jira projects, Insights workspaces, strategy docs, analytics tools)

---

## 8. Non-Functional Requirements

### Performance

| Requirement | Target |
|---|---|
| Space initial load time | < 3 seconds |
| View switching (Table/Timeline/Kanban) | < 500ms |
| Side panel open/close animation | < 300ms |
| Table scroll performance with 200+ items | 60fps, no jank |
| Jira sync latency (status changes) | < 30 seconds |
| Insights enrichment latency | < 24 hours for new items; < 1 hour for high-priority signals |

### Security & Privacy

| Requirement | Details |
|---|---|
| Data access control | Respect Miro Space permissions — only members see the roadmap |
| Jira access | Scoped to connected project(s) only; respects Jira permission schemes |
| Insights data | Follows Miro Insights data access policies; no raw customer data exposed to unauthorized users |
| AI data handling | No customer data used for model training; data processed within Miro's cloud infrastructure |
| Classification | Support Miro's Internal/Confidential/Public classification badges |

### Progressive Trust Model (V1)

The system launches at **Level 1 (Observer)** and **Level 2 (Advisor)**:

- **Level 1 — Observer**: AI monitors signals and surfaces alerts in the Pulse view. User makes all decisions.
- **Level 2 — Advisor**: AI provides recommendations with evidence (Suggested Actions). User approves or rejects.

Levels 3 (Collaborator) and 4 (Delegate) are deferred to future versions, requiring demonstrated AI accuracy and user opt-in.

---

## 9. Success Metrics

### Adoption

| Metric | Target | Measurement |
|---|---|---|
| Product Roadmaps created (first 90 days) | 500+ spaces | Direct count |
| Weekly active users per roadmap space | 5+ per space average | WAU within Product Roadmap Spaces |
| Jira connection rate | 70%+ of roadmaps connect Jira | Connection event / creation event |
| Miro Insights connection rate | 50%+ of roadmaps connect Insights | Connection event / creation event |

### Engagement

| Metric | Target | Measurement |
|---|---|---|
| Pulse view visits per week | 3+ per user | View event tracking |
| View switching frequency (Table/Timeline/Kanban) | At least 2 views used per roadmap | View event tracking |
| Record detail panel opens per week | 10+ per user | Click event tracking |
| Ideas promoted to Roadmap | 15%+ of ideas promoted within 30 days | Status change tracking |

### Satisfaction

| Metric | Target | Measurement |
|---|---|---|
| Roadmap CSAT | 4.0+ / 5.0 (up from 3.0 today) | In-product survey |
| PM time on signal gathering | 80% reduction (from 4-6hrs to <1hr/week) | Survey + time-tracking |
| Prioritization confidence | 80%+ decisions backed by customer evidence | Survey |
| NPS for Dynamic Roadmap feature | +30 | NPS survey |

### Business Impact

| Metric | Target | Measurement |
|---|---|---|
| Roadmapping frustration score | Reduce from 66% frustrated to <30% | Quarterly survey |
| Competitive win rate (vs. Productboard, Aha!) | Improve by 20%+ | Sales pipeline data |
| Enterprise expansion revenue attributable to roadmapping | $2M+ incremental ARR in first year | Deal attribution |

---

## 10. Phasing & Dependencies

### V1 Scope (This Document)

Focused on the PM workflow — evidence-driven execution engine:

- Entry flow (create from Spaces)
- AI creation dialog
- Product Roadmap Space with sidebar navigation
- Pulse view with AI intelligence
- AI Sidekick onboarding
- Roadmap table, timeline, kanban views
- Record detail panel with customer signals
- Ideas backlog
- Market and Analytics signal sections
- Jira two-way sync
- Miro Insights enrichment

### Deferred to V2

- Portfolio dashboard for leaders (cross-roadmap aggregation)
- Full AI agent suite (Alignment Monitor, Scenario Simulator)
- Goal/OKR integration with visual alignment scoring
- Cross-team dependency intelligence
- Auto-generated stakeholder views (Executive, Sales, Engineering)
- Snapshot/scenario mode for what-if planning
- Progressive trust Level 3-4 (AI-generated artifacts, delegated actions)
- Cadence Automator for Slack/email digests

### Key Dependencies

| Dependency | Owner | Status | Risk |
|---|---|---|---|
| Miro Insights x Tables enrichment GA | Lauren Brucato | V1 in progress | Medium — must ship before or with Dynamic Roadmap V1 |
| Jira two-way sync enhancement (real-time status) | Engineering | Exists, needs enhancement | Low — foundation exists |
| Miro Spaces architecture (sidebar nav support) | Platform team | Exists | Low |
| AI inference infrastructure (Claude/LLM) | AI Platform | Exists (powers Sidekick) | Low |
| Analytics data pipeline (Snowflake/Amplitude) | Data Engineering | Needs development | Medium — new integration work |

---

## 11. Open Questions

| # | Question | Impact | Owner |
|---|---|---|---|
| 1 | Should Jira sync support Azure DevOps in V1, or defer to V2? | Scope — Azure DevOps would expand addressable market but adds integration complexity | PM + Engineering |
| 2 | What is the maximum number of roadmap items supported in V1? (100? 500? 1000?) | Architecture — affects table rendering and enrichment costs | Engineering |
| 3 | How do we handle Insights enrichment for items that don't match any customer feedback theme? | UX — show empty enriched columns, or hide them? | PM + Design |
| 4 | Should the AI Sidekick be powered by Claude or an internal model? | Cost + quality tradeoff | AI Platform |
| 5 | What is the pricing model for Dynamic Roadmap? (Included in Business plan? Enterprise only? Add-on?) | GTM — affects adoption targets | Product + Finance |
| 6 | How do we handle conflicting data when Jira status and manually-set Miro status disagree? | UX — which is the source of truth? | PM + Engineering |
| 7 | Should Market Signals use live web scraping or curated feeds? | Technical + legal — scraping may have compliance implications | Legal + Engineering |
| 8 | What is the rollout strategy? (Beta with select customers? GA launch? Internal dogfooding first?) | Go-to-market | PM + GTM |
| 9 | How do we measure AI accuracy for the Pulse insights? What is the quality bar before GA? | Quality — false positives erode trust | PM + AI |
| 10 | Should Ideas Backlog support voting/upvoting from stakeholders? | Feature scope — adds collaboration but increases V1 surface area | PM |
