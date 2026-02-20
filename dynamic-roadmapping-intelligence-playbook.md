# Dynamic Roadmapping: Intelligence Playbook
## Competitor Learnings + Efficacy Framework — Condensed

> **One doc. The essential learnings from analysing 7 competitors and solving the hardest technical/UX problems in cross-signal AI for product management.**

---

## The Market Opportunity in One Paragraph

Every AI product management tool operates in a single lane: Linear Pulse surfaces execution updates, Productboard Spark synthesises customer feedback, Enterpret unifies VoC infrastructure, Zeda.io links feedback to revenue, Aha! drafts strategy docs, Atlassian Rovo automates Jira workflows, and Monday/ClickUp scatter AI across everything. **Nobody synthesises across Voice of Customer + Usage Analytics + Strategy Alignment + Market Intelligence.** That's the gap. It's open because it's genuinely hard — not an AI model problem but a data integration + entity resolution + trust calibration problem. Miro has a structural advantage: all four signals can plausibly live on one platform through Insights, Snowflake, strategy boards, and competitor tracking.

---

## The Three Problems to Solve

### 1. Efficacy — Does the AI tell me something I didn't already know?

The bar isn't "correct" — it's "non-obvious." If the AI says "your most-requested feature aligns with your Q2 OKR," that's useless. The value is when a weak customer signal + a competitor move + a usage dip + a strategic goal all point to the same opportunity — and the PM would have missed that convergence on their own.

**Why it's hard:**
- Data quality varies wildly across signals (Snowflake is precise; market intel is messy)
- "Non-obvious" requires causal reasoning, not correlation — LLMs are mediocre at this
- 85% accuracy is the minimum bar for sustained PM engagement (Productboard proved this through painful iteration from 40%)

### 2. Signal-to-Noise — Of what's surfaced, what % deserves my attention?

PMs are already drowning. Surfacing 47 signal changes weekly is noise. The system must say: "Here are the 3 things that should change your plan." Linear Pulse solves this for execution (personalised feeds with tabs). Dynamic Roadmapping must solve it for strategy — where a bad recommendation wastes a quarter, not just a sprint.

### 3. Trust — Will the PM actually act on it?

The fatal failure mode isn't inaccuracy — it's **miscalibrated trust**. Either undertrust (PM ignores the AI, defeating the purpose) or overtrust (PM follows uncritically, making bad decisions). The goal is calibrated trust: the PM knows when to lean on the AI and when to override it. This requires honest confidence communication — precisely what LLMs are worst at.

---

## What Competitors Teach Us

### The Strategic Lessons

| # | Lesson | Source | Implication |
|---|--------|--------|-------------|
| 1 | A feed is not a decision tool | Linear Pulse | Execution awareness ≠ strategic intelligence. Don't just surface what happened — show what it means for the plan |
| 2 | Audio digests get adoption | Linear Pulse | Walking briefings reduce "another dashboard to check" fatigue. Ship audio early |
| 3 | 40% → 85% accuracy is the real journey | Productboard Spark | V1 will be wrong more than half the time. Build the eval framework before the product |
| 4 | Guiding beats automating | Productboard Spark | "Here's the evidence" works. "Here's what to build" fails. At least initially |
| 5 | Context continuity is the moat | Productboard Spark | AI that remembers your product, customers, and past decisions across sessions feels like a colleague, not a chatbot |
| 6 | Plumbing before intelligence | Enterpret | Data integration + enrichment + quality scoring must precede AI synthesis |
| 7 | Revenue linkage changes behaviour | Zeda.io | "$2.1M ARR at risk" is 10x more actionable than "43 customers mentioned this" |
| 8 | Proprietary scoring creates stickiness | Zeda.io | A confidence model calibrated to your data creates switching costs that generic AI can't match |
| 9 | Distribution beats intelligence | Atlassian Rovo/JPD | Mediocre AI in a tool 80% of teams use will outperform excellent AI in a niche tool. Connect to Jira, Slack, Gong — where decisions already happen |
| 10 | "AI for everything" = "AI for nothing" | Monday/ClickUp | Horizontal AI is shallow. Own one use case deeply before expanding |

### The UX/UI Lessons

| # | Lesson | Source | Implication |
|---|--------|--------|-------------|
| 11 | Two-layer architecture: ambient + investigative | Linear Pulse + Productboard Spark | PMs need passive scanning (briefing tiles, evidence cards) AND active inquiry (sidekick chat). No competitor combines both well |
| 12 | Visual weight must encode importance | Zeda.io, Enterpret | Revenue numbers large and bold, not in metadata. Card size, colour, and position should signal priority — not all items equal |
| 13 | Side panel is the right AI container | Monday Sidekick, Spark, Notion | Maintains context (main content visible), non-modal, natural reading flow (content left, AI right), PM controls screen allocation |
| 14 | Progressive disclosure in 3 layers | Enterpret drill-down | **Level 1**: Tile scan (2 sec) — title, direction, confidence, headline number. **Level 2**: Sidekick summary (30 sec) — per-signal breakdown, key quote, AI interpretation. **Level 3**: Deep investigation (2-5 min) — full quotes, usage charts, reasoning chain |
| 15 | Distinguish AI content from raw data | Atlassian Rovo gap | Use ✦ sparkle only on AI interpretations. Verbatim quotes and metrics get no badge — they're ground truth. PMs need to know what to verify |
| 16 | Intent-based navigation beats filter-based | Zeda.io saved views | PMs think in questions ("What's at risk?"), not in data filters ("VoC + enterprise + negative + last 30 days"). Pre-build lenses by intent |
| 17 | Design for non-determinism | Monday regenerate + edit | Every AI output needs: transparency (source count), editability, regeneration, undo, and feedback (thumbs up/down) |
| 18 | Graduated empty states | Aha! guided Q&A, Linear zero-config | Show value at every integration level (0-4 signals). Ghost cards preview what the next connection unlocks. Never block value on full setup |
| 19 | Guided Q&A reduces prompt anxiety | Aha! | For onboarding and scenario planning, walk the PM through structured questions. But pull evidence from the system, not from the PM's memory |
| 20 | Calm density over visual noise | Linear UI redesign | Text-first, sharp typographic hierarchy, bold titles, muted metadata. Strategic tools need calm — not dashboards competing for attention |

---

## The Architecture That Works

### Why the Naive Approach Fails

Dumping 4 signals into one LLM prompt produces: hallucinated connections (conflating word meanings across contexts), obvious insights in sophisticated language, recency bias (yesterday's competitor move overshadowing 6-month trends), and confident assertions from incomplete data.

### The 6-Step Synthesis Pipeline

Don't run one giant prompt. Run a structured pipeline where each step is measurable and debuggable:

```
Step 1: Per-signal summarisation (4 parallel LLM calls)
   VoC → themed clusters with frequency + ARR weight
   Usage → trend reports per feature area
   Strategy → OKR-to-feature mapping
   Market → competitive landscape deltas

Step 2: Entity resolution (deterministic, not LLM)
   Match "Feature X" across VoC, usage, strategy, market
   Flag low-confidence mappings for PM review

Step 3: Per-entity evidence assembly (deterministic)
   Assemble all matched evidence per feature/initiative
   No interpretation yet — just structured evidence packages

Step 4: Cross-signal pattern detection (LLM + structured output)
   "What patterns exist across signal types? Rate confidence."
   JSON schema forces separation of observation from interpretation

Step 5: Novelty filter (LLM + PM history)
   Compare against existing roadmap and past decisions
   Only surface patterns representing NEW information

Step 6: Confidence calibration (statistical)
   Factor in: data quality ratings, entity resolution confidence,
   LLM self-reported confidence → conservative calibrated score
```

### Signal Quality Rating

Before synthesising, rate each source on four dimensions:

| Dimension | Question | Example |
|-----------|----------|---------|
| **Completeness** | What % of relevant data is captured? | Insights captures ~30% of feedback; the rest is in unrecorded Slack/email |
| **Recency** | How fresh? | Snowflake is real-time; competitive intel is updated monthly |
| **Representativeness** | Does it reflect the actual user base? | Gong captures enterprise calls; SMB voice is underrepresented |
| **Objectivity** | How much interpretation is baked in? | Usage data is objective; customer quotes are subjective and contextual |

This feeds directly into confidence scoring. Show the PM: "Strong usage data + strong VoC, but weak market data (competitive tracking last updated 3 weeks ago)."

---

## The UX Model

### The Briefing Room (Three-Zone Architecture)

```
┌─────────────────────────────────────────────────────────────┐
│  BRIEFING   │   BACKLOG   │   THE PLAN                      │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌────────────┐           │
│  │ 2   │ │ 1   │ │ 1   │ │ 4   │ │ 67%        │   TILES   │
│  │strn.│ │ new │ │weak.│ │unc. │ │ confidence │           │
│  └─────┘ └─────┘ └─────┘ └─────┘ └────────────┘           │
│                                                             │
│  ┌─────────────────────┐  ┌─────────────────────┐          │
│  │ Evidence Card       │  │ Evidence Card       │  AMBIENT  │
│  │ Title + direction   │  │ Title + direction   │  LAYER    │
│  │ Confidence: ████░░  │  │ Confidence: ██░░░░  │          │
│  │ $1.4M ARR · 23 cust │  │ 8 mentions · trend↑ │          │
│  └─────────────────────┘  └─────────────────────┘          │
│                                           ┌────────────────┐│
│  Click any card or tile →                 │ SIDEKICK PANEL ││
│                                           │                ││
│                                           │ "Where would   ││
│                                           │  you like to   ││
│                                           │  dive deeper?" ││
│                                           │                ││
│                                           │ ○ Customer     ││
│                                           │   quotes       ││
│                                           │ ○ Usage data   ││
│                                           │ ○ Strategy     ││
│                                           │   alignment    ││
│                                           │ ○ Market       ││
│                                           │   context      ││
│                                           │                ││
│                                           │ ✦ AI interpre- ││
│                                           │   tation with  ││
│                                           │   confidence   ││
│                                           └────────────────┘│
└─────────────────────────────────────────────────────────────┘
```

**Ambient layer** (tiles + cards): Scan in 30 seconds. Visual weight encodes importance. Colour-coded signal changes, revenue numbers prominent, confidence as bar fills.

**Investigative layer** (sidekick panel): Opens on click. Pre-populated with context. Supports evidence browse, conversational inquiry, and recommendation review. Remembers state across sessions.

**Bridge between layers**: Click a tile or card → sidekick opens with that item's evidence. The interaction IS the transition from scanning to investigating.

### Confidence-Graduated Display

| Tier | Criteria | Visual treatment | Surfacing |
|------|----------|-----------------|-----------|
| **HIGH** | 3+ strong signals align | Large card, prominent position, bold colour | Dashboard + email digest + audio briefing |
| **MEDIUM** | 2 signals or data quality gaps | Standard card, secondary position | Dashboard only, collapsible |
| **LOW** | Single signal or contradictory | Hidden behind "See more" or "Weak signals" section | Available on demand, never pushed |

**Critical rule**: Confidence scoring must be conservative. Overtrust (acting on false HIGH) destroys trust permanently. Undertrust (ignoring a MEDIUM that's actually HIGH) is recoverable — the signal strengthens and gets re-surfaced.

### The Anomaly Architecture — Show the Delta, Not the State

PMs know their roadmap. They don't need the AI to describe it. They need: "Here's what changed since you last looked that might change your plan."

1. **Baseline** the PM's current knowledge (first use)
2. **Monitor** all 4 signals for deviations from baseline
3. **Filter** by relevance to current roadmap items
4. **Surface** only 2-5 anomalies per week, each stating: what changed, what roadmap items it affects, whether it strengthens or weakens the case, and confidence level

This is Linear Pulse's model elevated from execution level (issue status changes) to strategic level (customer shifts, competitive moves, strategy implications).

---

## The Trust Ramp — How AI Earns the Right to Advise

| Phase | Weeks | AI role | What PM sees | Trust built |
|-------|-------|---------|-------------|-------------|
| **1. Librarian** | 1-4 | Organise and surface evidence | "Here are your signals, neatly packaged" — PM verifies accuracy of raw data | "The AI knows my product" |
| **2. Analyst** | 4-8 | Detect within-signal patterns | "VoC mentions of Feature X are up 65% this quarter" — PM validates the trend | "The AI spots things I'd miss" |
| **3. Observer** | 8-12 | Connect cross-signal patterns | "Demand up + adoption down + competitor shipped = time-sensitive gap" | "The AI connects dots I haven't" |
| **4. Advisor** | 12+ | Suggest plan changes with evidence | "Feature X should move up — here's the evidence for and against" | "I trust this enough to act on it" |

**Why this sequence is non-negotiable**: Productboard went straight to Phase 4 in V1, achieved 40% accuracy, and lost PM trust. They had to rebuild from Phase 1. The trust ramp isn't a nice-to-have — it's the product strategy.

**The mechanics**: The system tracks its own accuracy. If PMs consistently validate Phase 2-3 patterns, the system earns Phase 4. If recommendations get dismissed, it drops back a level. Self-driving car logic: you don't go from manual to autonomous overnight.

---

## Measuring Success

| Metric | Target | What it tells you |
|--------|--------|-------------------|
| **Recommendation precision** | >60% engagement rate for HIGH confidence items | Are we surfacing things PMs care about? |
| **Non-obviousness** | >40% rated "didn't already know" | Are we adding value beyond what PMs can see themselves? |
| **Decision impact** | >70% directionally correct outcomes | Are PM decisions better with this tool? (3-6 month lag) |
| **Noise ratio** | <30% dismissal for HIGH confidence items | Are we showing too much? (If <5%, we're too conservative) |
| **Trust trajectory** | Increasing engagement over 8 weeks | Is the product earning trust over time? (Leading indicator) |

---

## What to Build When

### Q1: Foundation — Evidence Packaging

Ship evidence cards (4-signal view per item), daily briefing digests (email + Slack + audio), signal quality scoring, and the PM feedback loop. No recommendations yet. Goal: >60% of briefing items rated "useful."

### Q2: Intelligence — Cross-Signal Patterns

Ship cross-signal pattern detection, the anomaly architecture, context memory across sessions, and revenue-linked signals. Goal: >40% of patterns rated "non-obvious."

### Q3: Collaboration — The Multiplayer Leapfrog

Ship shared evidence briefings for team planning, team challenge/validate workflows on the canvas, evidence-backed scenario planning, and decision recording with provenance. Goal: >30% faster consensus on quarterly roadmaps.

### Q4: Autonomy — Earned Recommendations

Ship suggested actions with confidence scoring, decision outcome tracking, predictive signals, and audio walkthroughs of evidence changes. Goal: increasing trust trajectory over 8 weeks.

---

## Anti-Patterns to Avoid

| Anti-pattern | Who did it | What happens | Instead |
|-------------|-----------|-------------|---------|
| AI for everything | Monday, ClickUp | Feature sprawl, no depth, no PM trust | Own one use case deeply first |
| ChatGPT wrapper | Aha! | No proprietary intelligence, easily replaced | Moat is in connected data, not generation |
| AI bolted onto legacy UI | Atlassian Rovo | Modern AI in an old container, high cognitive load | Design the data model and UX for AI from the start |
| Recommendations before trust | Early Productboard | 40% accuracy, PMs stop using it | Evidence first → interpretation → recommendations over 12+ weeks |
| Show everything equally | Linear Pulse | PM scans instead of focuses, no prioritisation signal | Visual weight encodes importance; not all items equal |
| Single-player AI | Productboard Spark | PM becomes bottleneck between AI and team | Multiplayer: shared briefings, team challenge, collaborative decisions |
| Wait for full setup | Enterpret | PM churns during integration | Graduated value: useful at 1 signal, better at 2, leapfrog at 4 |

---

## The Defensibility Summary

| Advantage | Time to replicate | Why |
|-----------|-------------------|-----|
| 4-signal data integration | 12-18 months | Infrastructure, not AI — deep integrations across VoC, usage, strategy, market |
| Multiplayer AI on canvas | 18-24 months | Requires real-time sync infrastructure Miro has spent 10+ years building |
| Decision memory | 12+ months, compounds | Treating decisions as first-class objects with evidence provenance |
| Spatial reasoning on canvas | Not replicable | Competitors would need to become a canvas tool |
| Progressive trust ramp | 9-12 months | Systems problem: calibrated eval, PM feedback loops, graduated UX |
| Entity resolution across signals | 12+ months, improves with scale | Proprietary mapping of concepts across 4 signal types |

---

> **The one-line summary**: Every competitor helps PMs work faster in their silo. Dynamic Roadmapping helps teams make better decisions across silos — backed by evidence from every signal that matters, earned through a trust ramp that starts with showing evidence and graduates to making recommendations. The moat is in the data integration, the multiplayer canvas, and the decision memory — none of which can be replicated by swapping in a better LLM.
