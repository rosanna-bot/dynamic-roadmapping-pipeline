# Miro AI: Capabilities, Technical Architecture, Limitations, and Roadmap

*Last updated: 12 February 2026*

---

## 1. What Miro AI Is Today

Miro AI is a suite of AI features embedded across the entire Miro platform. It is available on all plans (Free, Starter, Business, Enterprise, Education) and works on browser, desktop, and mobile.

The core design principle is **"the canvas is the prompt"** -- users select board objects (sticky notes, diagrams, docs, images) as context for AI, rather than writing standalone text prompts. This means Miro AI can read almost all board elements and use them to enrich generated results.

> Source: [Miro AI Overview (Help Center)](https://help.miro.com/hc/en-us/articles/28765406244498-Miro-AI-overview); [Miro AI FAQ (Internal)](https://docs.google.com/document/d/1WbcholCO4sOg1Fbxw3aVB3YWI4w1KVNRlZQ_RzYjwj0)

---

## 2. Current Capabilities

### 2.1 Content Creation and Iteration ("Create with AI")

These features let users generate and refine structured content from prompts or by selecting existing board content. Available via the "Create with AI" panel in the toolbar or the Miro AI context menu.

| Feature | What it does | Model(s) | Credits |
|---|---|---|---|
| Sticky Notes | Generate stickies from prompts or selected content | GPT-4o | 1 |
| Docs | Generate structured documents (briefs, summaries, outlines) | GPT-4o | 1 |
| Tables | Generate tables for planning, backlogs, analysis | Claude 3.7 Sonnet | 1 |
| Diagrams (Flowchart) | Generate/edit flowcharts from descriptions | GPT-4o | 1 |
| Diagrams (Mind Map) | Generate/edit mind maps | GPT-4o-mini (create) / GPT-4o (edit) | 1 |
| Diagrams (ERD) | Generate/edit entity-relationship diagrams | GPT-4o-mini (create) / GPT-4o (edit) | 1 |
| Digitize Diagram | Convert image of hand-drawn diagram to editable | Claude 3.7 Sonnet (AWS Bedrock) | 1 |
| Images | Generate images from prompts | Segmind SSD-1B + StabilityAI Diffusion XL Refiner | 1 |
| Prototypes | Generate interactive app/website prototypes | GPT-4o + Claude 4.5 Sonnet + GPT-4o-mini + Gemini 2.5 Flash Image | 5 per screen |
| Image to Prototype | Convert sketch/screenshot to editable prototype | Miro proprietary + Claude 3.7 Sonnet | 5 per screen |
| Kanban | Organize tasks in columns with Table/Timeline/Kanban switching | Multiple | 1 |
| Timeline | Plan projects with interactive timelines | Multiple | 1 |
| Slides | Create presentations from board content | Amazon Titan, Claude 4/3.7/3.5 Sonnet, GPT-5, GPT-4o, SD 3.5 Large | 1 |

> Source: [Miro AI Reference](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference)

### 2.2 Text Editing

Available from the context menu when text is selected.

| Feature | Model |
|---|---|
| Change Tone (friendly, professional, business, fun) | GPT-5 nano |
| Fix Grammar and Spelling | GPT-5 |
| Rewrite for Clarity | GPT-5 Chat |
| Shorten Text | GPT-5 mini |
| Translate (18 languages) | GPT-5 mini |

> Source: [Miro AI Reference](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference)

### 2.3 Clustering

| Feature | Model |
|---|---|
| Cluster by Keywords -- groups sticky notes by themes | Claude 3.5 Haiku + Amazon Nova Micro |
| Cluster by Sentiment -- groups into positive/neutral/negative | Claude 3.5 Haiku |

> Source: [Miro AI Reference](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference)

### 2.4 Summarization

| Feature | Model |
|---|---|
| Conversation Summaries -- summarize comment threads | GPT-4o-mini |
| Catch Up (Beta) -- highlights updates since last visit | Multiple |

> Source: [Miro AI Overview (Help Center)](https://help.miro.com/hc/en-us/articles/28765406244498-Miro-AI-overview)

### 2.5 Utility Features (Miro Proprietary Models)

These run on Miro's own models and **do not consume credits** (except Sticky Capture).

| Feature | What it does |
|---|---|
| Image Alt Text | Generates accessibility alt text for images. Free. |
| Remove Background | Removes image backgrounds |
| Smart Drawings | Converts pencil drawings to lines, shapes, stickies |
| Sticky Capture | Converts photos of physical stickies to digital |

> Source: [Miro AI Reference](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference)

### 2.6 Miro Insights

An AI-powered customer intelligence product that ingests feedback from Gong, Salesforce, Zendesk, NPS surveys, and more. Uses GPT-4o to synthesize themes, surface opportunity statements, and connect feedback to product decisions.

> Source: [FY26 Miro Insights Roadmap board](https://miro.com/app/board/uXjVIuicX1U=/)

---

## 3. AI Workflows: Sidekicks and Flows

These are the newer "AI Canvas" capabilities. They went to General Availability for Enterprise on 12 January 2026, with self-serve GA and monetization launching 16 February 2026.

### 3.1 Sidekicks

Specialized AI agents that work alongside your team directly on the canvas.

**How they work technically:**
- Sidekicks are chat-based agents that can read board content, leave comments, generate formats (stickies, docs, tables, diagrams, prototypes), and suggest next steps
- Default model is GPT-4o, but users can switch models via Select Your Own Model (SYOM)
- Sidekicks now use Canvas I/O data for processing -- they read widget content and embedded integrations (e.g. Jira cards) directly
- Pre-built library includes Agile Coach, Product Leader, Product Marketing Alliance, and community sidekicks on Miroverse
- Users can build custom Sidekicks with custom instructions, specific tools, and knowledge integrations, then share across their organization
- Knowledge integrations allow Sidekicks to query Glean, Gemini Enterprise, Amazon Q, and Microsoft Copilot for enterprise context

**Recent improvements (shipping Feb 16):**
- Sidekicks in Diagramming and Prototyping Focus Mode -- replacing legacy Format Agents
- Format-aware tool restrictions -- Sidekick automatically restricts to format-compatible tools
- Users can type the next prompt while Sidekick is generating

**Current metrics:** 51% retention rate for Sidekicks; live to 1.23 million users.

> Sources: [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0); [GTM Product Hub: Miro AI Workflows board](https://miro.com/app/board/uXjVJDHrpEY=/); [Weekly Updates board (Derrek Pearson)](https://miro.com/app/board/uXjVJjr9mBU=/); [Strategy Roadmap FY27 (AI Canvas) board](https://miro.com/app/board/uXjVJ3dXH2k=/)

### 3.2 Flows

Visual AI workflows that connect canvas content through multi-step processes.

**How they work technically:**
- Widgets (docs, tables, slides, prototypes, diagrams, frames) get connectors that visually link them
- AI reads the full context from connected upstream objects when generating the next step
- Each step in a Flow can use a different model (via SYOM) and can include AI Instruction Blocks -- custom prompts run through an LLM or knowledge provider
- Flows run on the canvas with staged content (Apply/Discard) before committing
- 100% of flow content is now logged for downstream governance systems

**Recent improvements (shipping Feb 16):**
- Global Run Button -- contextual control that appears when selecting any artifact in a flow
- Revert for Flows -- every run stores the previous version; users can revert for up to 24 hours
- Hide Flow Connectors -- optional per-user toggle for board legibility
- Smarter connector highlighting -- selecting a node lights up only relevant paths
- Native Kanban generation as a flow output
- AI Governance guardrails -- respects org-level policies for knowledge sources and web search

**Current metrics:** 60% retention rate for Flows.

> Sources: [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0); [Flows - WoW Artefacts board](https://miro.com/app/board/uXjVIxE4PV4=/); [Weekly Updates (AI Canvas) board](https://miro.com/app/board/uXjVJhpL5f0=/); [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/)

### 3.3 AI Canvas Toggle

A user-level setting in the left toolbar that transforms the board into an AI-first experience. When enabled: the toolbar becomes AI-first, blank boards show a "what do you want to do today" prompt, widgets get connectors for Flows, and Sidekicks can greet users proactively. End users control this toggle directly -- admins cannot force it on or off.

> Source: [Miro AI FAQ (Internal)](https://docs.google.com/document/d/1WbcholCO4sOg1Fbxw3aVB3YWI4w1KVNRlZQ_RzYjwj0)

---

## 4. How It Works Technically: Architecture Overview

Miro's AI is delivered through several technical layers:

- **AI Model Gateway** -- Centralized routing layer that directs requests to the appropriate model provider (OpenAI/Azure, Anthropic/AWS Bedrock, Stability AI, Google Vertex, Amazon, or Miro proprietary). Handles fallbacks, timeouts, and model selection.
- **Canvas I/O** -- The system that reads board content and converts it into structured context for AI. Sidekicks and Flows both use Canvas I/O to understand widgets, embeds, and Jira card content.
- **AI Compliance Service** -- Handles authorization, feature-level permissions (granular admin controls), content moderation (via Azure), and content logging. Evaluates whether a user/team/board is allowed to use a specific AI feature.
- **Agent Planner Service** -- Orchestrates multi-step tool execution for Sidekicks, selecting the right tools and managing conversation state.
- **Tool Registry** -- Registry of available AI tools (generate stickies, create doc, create diagram, web search, etc.) that Sidekicks and Flows can invoke.
- **Visual Context Processing (VCP)** -- A novel system for providing visual context to AI. Interprets spatial relationships, visual layouts, and image content on the board.

Models are hosted on provider infrastructure, Microsoft Azure AI, or AWS Bedrock. For AWS Marketplace customers, all models run on AWS Bedrock (using Claude Sonnet 3.7 variants instead of OpenAI models). Data is processed in EU, US, or AU based on the customer's data residency setting.

> Sources: [AI Architecture - Vision board](https://miro.com/app/board/uXjVJwsSkL8=/); [AI Context Vision & Plan board](https://miro.com/app/board/uXjVGNcT4bM=/); [Miro AI Admin Security (Help Center)](https://help.miro.com/hc/en-us/articles/11277533556626-Miro-AI-Admin-security)

---

## 5. Integrations and Extensibility

| Integration | What it does | Status |
|---|---|---|
| **Select Your Own Model (SYOM)** | Users choose which LLM powers Sidekicks and each Flow step. Available models: Claude 3.7 Sonnet, Claude Sonnet 4, GPT-4o, GPT-4o-mini, o4-mini, GPT-5, GPT-5 mini, GPT-4.1, GPT-4.1 mini. Image models: Stable Image Core/Ultra, SD 3.5 Large, Amazon Titan/Nova Canvas, Gemini 2.5 Flash Image, Vertex AI Imagegen 3/3 Fast/4. | GA |
| **Knowledge: Glean** | Query Glean from Sidekicks and Flows for enterprise knowledge | GA |
| **Knowledge: Gemini Enterprise** | Query Google Agentspace/Gemini Enterprise | GA (Feb 16) |
| **Knowledge: Microsoft Copilot** | Query Copilot for enterprise knowledge | GA (Feb 16) |
| **Knowledge: Amazon Q** | Query Amazon Q for enterprise knowledge | Beta |
| **MCP Server** | Connects Miro boards to AI coding tools (Cursor, Lovable, GitHub Copilot) | GA |
| **Bring Your Own Key (BYOK)** | Enterprise customers connect their own OpenAI/Azure OpenAI key for specific text-generation features (primarily Miro Docs via Create with AI) | Private Beta |
| **Microsoft Purview** | Review AI prompts/responses in Purview's AI hub for compliance | GA |

> Sources: [Miro AI Reference](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference); [Bring Your Own AI Initiative board](https://miro.com/app/board/uXjVKr5ne_c=/); [CFR: On the Roadmap board](https://miro.com/app/board/uXjVJg7289k=/); [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0); [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/)

---

## 6. Credits and Pricing

| Plan | Monthly Credits | Scope |
|---|---|---|
| Free | 10 | Shared by team |
| Education | 100 | Shared by team |
| Starter | 25 per license | Per user |
| Business | 50 per license | Per user |
| Enterprise | 100 per license (soft limit) | Per user |

Most features consume 1 credit per action. Prototypes consume 5 per screen. Image alt text is free. Failed generations are free. Enterprise has a soft limit -- users are not interrupted, but if consistently exceeding over 4 of 6 months, Miro will discuss options.

**AI Workflows Add-on** (Enterprise): Unlocks Sidekicks and Flows. List price $100/seat, packaged in tiers of $2,500 per 25 seats. Includes uncapped credits for Sidekicks and Flows.

> Sources: [Miro AI Credits (Help Center)](https://help.miro.com/hc/en-us/articles/19756209116178-Miro-AI-credits); [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0); [GTM Product Hub board](https://miro.com/app/board/uXjVJDHrpEY=/)

---

## 7. Enterprise Governance and Security

### Admin Controls

Enterprise admins can control AI at the capability level (Admin Console > Miro AI > Capabilities): Create Content, Images, Summarize Activity, Flows, Sidekicks, Prototyping, Beta Features. Each can be set to Everyone, No one, or Specific teams.

With **Enterprise Guard** (add-on), controls extend to individual features within each category. Intelligent Guardrails can automatically disable Miro AI on boards with sensitive content based on classification.

### Privacy and Data

- Data is processed in EU, US, or AU based on residency
- Enterprise: data is NOT used for model training (opt-out by default)
- Paid plans: data is NOT used for model training
- Free plan: anonymised AI interaction data IS collected (can be disabled)
- Miro does NOT share interactions with third-party providers for their training
- Customer owns all AI inputs and outputs; Miro asserts no rights
- Certifications: ISO 27001, SOC2, ISO 42001, GDPR, CCPA compliant

> Sources: [Miro AI Admin Security (Help Center)](https://help.miro.com/hc/en-us/articles/11277533556626-Miro-AI-Admin-security); [Miro AI Granular Admin Controls](https://help.miro.com/hc/en-us/articles/27016283682578-Miro-AI-granular-admin-controls); [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0)

---

## 8. Current Limitations

### Access

- **Members only** -- guests and visitors cannot use Miro AI
- **Mobile** -- basic AI available, but advanced features (Flows, some Sidekick capabilities) are browser-only
- **No SLA** -- Miro does not currently provide a specific SLA for AI availability or performance
- **Not available on Interactive Displays**

### Output Quality

- **LLM accuracy** -- "Due to the nature of LLMs, not all generated content may be accurate. The output should always be checked before using it." Quality has been confirmed through user research as the main reason users stop using Miro AI features.
- **No visual tagging** -- AI-generated content is not visually differentiated from manually created content (except Sidekick comments which show an AI sparkle icon)
- **Context window limits** -- constrained by underlying LLM context windows; no hard numerical limit on objects but very large selections may be truncated

### Flows-Specific

- Flows described internally as "closer to a version 0.7 than a fully formed product" -- the experience can be "too barebones, too fragile, and at times too cumbersome" for users to reliably experience the value
- Data Tables not yet fully supported for Revert/Undo
- Conversation history disabled in Focus Mode
- Tables and Documents not yet supported in Focus Mode Sidekicks
- Content is staged (Apply/Discard) rather than edited in-place -- in-place editing is a follow-up

### Enterprise Adoption

- Enterprise enablement rate for Miro AI is approximately 14% overall, 20% for ENT/STRAT segment
- BYOK is still in private beta and only covers a narrow set of text-generation features (primarily Miro Docs)

> Sources: [Miro AI Overview (Help Center)](https://help.miro.com/hc/en-us/articles/28765406244498-Miro-AI-overview); [Strategy Roadmap FY27 (AI Canvas) board](https://miro.com/app/board/uXjVJ3dXH2k=/); [AI Onsite - Roadmap Workshop board](https://miro.com/app/board/uXjVL_v_Rvk=/); [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/); [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0)

---

## 9. What's Next: Future Versions and Timelines

### 9.1 Launching Now (Feb 16, 2026)

| What | What it unlocks | Source |
|---|---|---|
| AI Workflows GA + monetization | Enterprise customers can purchase Sidekicks and Flows; self-serve availability | [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0) |
| Gemini Enterprise + Microsoft Copilot knowledge integrations GA | Sidekicks and Flows can query enterprise knowledge from Google and Microsoft | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Sidekicks in Focus Mode (Diagramming + Prototyping) | One unified AI experience across canvas and focused editing; replaces legacy Format Agents | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Flows: Global Run Button, Revert, Hide Connectors | Flows are easier to find, understand, and safely run; reduces "I overwrote something" risk | [Weekly Updates (AI Canvas) board](https://miro.com/app/board/uXjVJhpL5f0=/) |
| AI Governance guardrails for Flows | 100% content logging; org-level governance policies enforced | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Jira Hierarchies GA | Better Jira card readability and hierarchy display for AI context | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |

### 9.2 Near-Term (Q1-Q2 2026 / FY27 H1)

| What | What it unlocks | Timeline confidence | Source |
|---|---|---|---|
| Sidekick context awareness in Focus Mode | Sidekick can read existing format content, not just generate new | Active development | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Edit-in-place for Sidekicks | Iterate on existing content without full replacement (currently staged) | Follow-up to Focus Mode | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Sidekicks in Tables, Documents, Slides Focus Modes | Unified AI experience across all format types | Planned Q1-Q2 | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Full legacy Format Agent sunset | One AI UX everywhere; reduces code surface and confusion | Dependent on Focus Mode rollout | [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| Step-by-step Flow execution | Run one step at a time for facilitated collaboration and iteration | Design kicked off | [Weekly Updates (AI Canvas) board](https://miro.com/app/board/uXjVJhpL5f0=/) |
| MCP Connectors for Sidekicks and Flows | Admin-managed and user-managed MCP server connections; democratised knowledge ingestion | Mironeer POC week of Feb 16 | [Kick-off: More Connectors board](https://miro.com/app/board/uXjVGRUTIvE=/); [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |
| Dynamic Roadmap V1 | AI-powered backlog creation from Jira, Insights, strategy docs; Pulse intelligence dashboard; connected Table/Timeline/Kanban views | Mid-March target for first version | [AI for Strategy & Execution V1 Kick-off board](https://miro.com/app/board/uXjVGFs4iYA=/); [Strat Pack FY27 Roadmap board](https://miro.com/app/board/uXjVGG7kp7I=/) |
| Miro Insights deep integration with Sidekicks/Flows | Customer feedback becomes a data source for Sidekicks; automated insight-to-roadmap flows | Q1-Q2 | [FY26 Miro Insights Roadmap board](https://miro.com/app/board/uXjVIuicX1U=/) |
| AI Gen Apps (POC) | AI generates entire boards/spaces with widgets, Flows, Sidekicks from a description | Early concept stage | [Kick-off Deck: AI Gen Apps board](https://miro.com/app/board/uXjVGZKPMIg=/) |
| Model Gateway expansion | GPT 5.1 Codex, GPT 5.1 Codex Max, Anthropic Opus 4.6 | In progress | [Weekly Updates board](https://miro.com/app/board/uXjVJjr9mBU=/) |

### 9.3 Medium-Term (FY27 H2 / Late 2026)

| What | What it unlocks | Source |
|---|---|---|
| **Unified "Miro AI"** | From separate Sidekicks, Flows, and Omnibar to one coherent AI that users "learn once, use everywhere." A Miro AI "concierge" that can hand off to specialist Sidekicks: "I can help, but the Strategy Sidekick might be better equipped." | [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| **Sidekicks that learn (Memory)** | Conversation history across sessions; AI adapts to user preferences and patterns over time. "AI gets better the more it learns about me." | [AI Context Vision & Plan board](https://miro.com/app/board/uXjVGNcT4bM=/); [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| **Proactive AI** | AI suggestions, autocompletion, and nudges without explicit prompting. "Always listening, proactive, predictive." | [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| **Connecting Flows and Sidekicks** | Sidekicks run flow steps, create flows, and participate in multi-step workflows seamlessly | [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| **AI Workflow Automation** | Event-driven Flows that run without a board being open -- observe events, trigger actions, call services, send notifications | [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/) |
| **Cross-board AI context** | AI carries context across boards, formats, flows, and agents so users don't have to repeat themselves | [AI Context Vision & Plan board](https://miro.com/app/board/uXjVGNcT4bM=/) |
| **Bring-your-own-custom AI model** | Enterprise customers bring proprietary models (e.g. custom image generators) into Miro | [AI Roadmap board](https://miro.com/app/board/uXjVLsIFoPs=/) |
| **AI attribution** | Visual labeling of AI-created artifacts for compliance and transparency | [AI Roadmap board](https://miro.com/app/board/uXjVLsIFoPs=/) |

### 9.4 Long-Term Vision

The overarching direction, drawn from strategy boards and vision sprints:

- **"Miro AI = Ambient Intelligence"** -- AI as the primary mode of interaction with the canvas. Target: "By Q4 FY26, we aim for AI to be the main mode of interaction with the Miro Canvas for collaboration."
- **Full board/space generation** -- Generate entire project spaces with widgets, Flows, Sidekicks, and formats from a prompt
- **Roadmap Autopilot** -- AI co-owns roadmaps, keeping them aligned to goals and reality without manual maintenance
- **Multimodal AI** -- Voice, vision, and text seamlessly integrated
- **Enterprise customization** -- Org-specific AI behavior, custom workflows, enterprise knowledge deeply integrated
- The central question being explored: **"Does the future of Miro look like a canvas with AI features, or a conversational interface with a canvas?"**

> Sources: [AI Architecture - Vision board](https://miro.com/app/board/uXjVJwsSkL8=/); [RKO Design Vision board](https://miro.com/app/board/uXjVJiBXRu8=/); [Strategy Roadmap FY27 board](https://miro.com/app/board/uXjVJ3dXH2k=/); [AI Context Vision & Plan board](https://miro.com/app/board/uXjVGNcT4bM=/)

---

## 10. Key Quality Themes

Two themes surface repeatedly across all internal roadmap and planning boards:

1. **Quality is the #1 priority.** "Quality remains the main reason users stop using Miro AI features." Confirmed through user research across almost all features. Quality improvement is a thread running through every team's roadmap.

2. **Infrastructure consolidation is essential.** "Miro AI features are currently deployed in diverse ways that make ownership, maintainability and improvements difficult." The move is toward a consolidated Core AI API with shared primitives (context, tools, model gateway) that all product surfaces use.

> Sources: [AI Onsite - Roadmap Workshop board](https://miro.com/app/board/uXjVL_v_Rvk=/); [AI Architecture - Vision board](https://miro.com/app/board/uXjVJwsSkL8=/)

---

## Appendix: Key Internal Source Boards

| Board | Owner | What it covers |
|---|---|---|
| [AI Roadmap](https://miro.com/app/board/uXjVLsIFoPs=) | Henrik Haugbolle | Master AI roadmap -- all streams |
| [Strategy Roadmap FY27 (AI Canvas)](https://miro.com/app/board/uXjVJ3dXH2k=) | Henrik Haugbolle | FY27 Flows + Sidekicks strategy and vision |
| [AI Onsite - Roadmap Workshop - FY26](https://miro.com/app/board/uXjVL_v_Rvk=) | Ioannis Sintos | FY26 planning across AI teams |
| [AI Architecture - Vision](https://miro.com/app/board/uXjVJwsSkL8=) | Dominic Hauton | Technical architecture and target state |
| [AI Context Vision & Plan](https://miro.com/app/board/uXjVGNcT4bM=) | Larissa Licha | Context layer vision and principles |
| [RKO Design Vision](https://miro.com/app/board/uXjVJiBXRu8=) | Andrew Cullen | AI Canvas vision sprint artefacts |
| [Bring Your Own AI Initiative](https://miro.com/app/board/uXjVKr5ne_c=) | Nina Simonoska | BYOK/SYOM strategy and tracking |
| [More Connectors for Sidekick & Flows](https://miro.com/app/board/uXjVGRUTIvE=) | Floris de Haan | MCP connector strategy |
| [AI for Strategy & Execution V1](https://miro.com/app/board/uXjVGFs4iYA=) | Laurens Kersbergen | Dynamic Roadmap kick-off |
| [FY26 Miro Insights Roadmap](https://miro.com/app/board/uXjVIuicX1U=) | Lauren Brucato | Insights product roadmap |
| [Kick-off Deck: AI Gen Apps](https://miro.com/app/board/uXjVGZKPMIg=) | Vihar Parikh | AI-generated boards/spaces vision |
| [Flows - WoW Artefacts](https://miro.com/app/board/uXjVIxE4PV4=) | Damir Dizdarevic | Flows H1 2026 roadmap |
| [GTM Product Hub: AI Workflows](https://miro.com/app/board/uXjVJDHrpEY=) | Claire Bakken | GTM sales play and customer-facing roadmap |
| [Weekly Updates (AI Canvas)](https://miro.com/app/board/uXjVJhpL5f0=) | Joe McLean | Weekly AI Canvas status |
| [Weekly Updates (AMPED)](https://miro.com/app/board/uXjVJjr9mBU=) | Derrek Pearson | Weekly cross-stream updates |
| [AI Workflows GA FAQ](https://docs.google.com/document/d/1UjcrEhpCcUNVerhWMCvD96yJC4A-PMpEV8qLMIaQLy0) | Cody Dishman | GA transition FAQ |
| [Miro AI FAQ (Internal)](https://docs.google.com/document/d/1WbcholCO4sOg1Fbxw3aVB3YWI4w1KVNRlZQ_RzYjwj0) | Dominique Rolink | Comprehensive AI FAQ |
| [Miro AI Reference (Help Center)](https://help.miro.com/hc/en-us/articles/20970362792210-Miro-AI-reference) | -- | Public feature + model reference |
| [Miro AI Overview (Help Center)](https://help.miro.com/hc/en-us/articles/28765406244498-Miro-AI-overview) | -- | Public capabilities overview |
| [Miro AI Admin Security (Help Center)](https://help.miro.com/hc/en-us/articles/11277533556626-Miro-AI-Admin-security) | -- | Public admin + security reference |
| [Strat Pack FY27 Roadmap](https://miro.com/app/board/uXjVGG7kp7I=) | Rosanna Knottenbelt | Dynamic Roadmap V1 requirements |
