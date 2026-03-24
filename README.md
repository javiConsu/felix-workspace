# Felix Workspace — CEO Agent for SalesHackersGTM

Felix is an autonomous CEO agent built on [Paperclip / OpenClaw](https://github.com/paperclipai/paperclip). He operates as the Chief Executive Operator of **SalesHackersGTM**, managing GTM strategy, outbound campaigns, pipeline health, and competitive intelligence — autonomously, in Spanish.

## Architecture

```
felix-workspace/
├── AGENTS.md          # Operating instructions — read this first every session
├── SOUL.md            # Core identity, personality, and JARVIS rules
├── HEARTBEAT.md       # Scheduled checks (Morning Brief, Midday, Wrap-up, Weekly)
├── IDENTITY.md        # Who Felix is, what company he runs, tech stack
├── TOOLS.md           # Available integrations (Apollo, HubSpot, Instantly, Walead, etc.)
├── MEMORY.md          # Tacit knowledge — lessons learned, patterns, preferences
├── ICP-1.md           # Ideal Customer Profile #1 (add more as needed)
├── COMPETITORS.md     # Competitor profiles and battlecards
├── skills/
│   ├── signal-scanner/        # Detect buying intent signals from the TAM
│   ├── sales-call-prep/       # Pre-meeting briefings (3 parallel subagents)
│   ├── outbound-campaign/     # Full multi-channel outbound orchestration
│   ├── linkedin-content/      # LinkedIn content strategy and post generation
│   ├── pipeline-review/       # HubSpot pipeline health analysis
│   ├── competitor-intel/      # Competitor monitoring and battlecard updates
│   ├── revenue-metrics/       # Stripe MRR and payment health tracking
│   ├── site-health/           # Production uptime monitoring
│   ├── coding-agent-loops/    # Autonomous development task execution
│   └── x-posting/             # X/Twitter content management
└── memory/
    ├── YYYY-MM-DD.md          # Daily notes (Layer 2 memory)
    ├── briefings/             # Pre-call briefings
    ├── campaigns/             # Campaign logs and reply tracking
    ├── battlecards/           # Competitor battlecards
    └── heartbeat-state.json   # Heartbeat execution state
```

## Memory Architecture (3 Layers)

| Layer | Files | Purpose | Update Frequency |
| :--- | :--- | :--- | :--- |
| **Knowledge Graph** | `IDENTITY.md`, `ICP-*.md`, `COMPETITORS.md` | Structured long-term business facts | When fundamentals change |
| **Daily Notes** | `memory/YYYY-MM-DD.md` | Raw activity log | Continuously during the day |
| **Tacit Knowledge** | `MEMORY.md` | Curated lessons, patterns, preferences | Weekly consolidation |

## Key Skills

| Skill | Trigger | Output |
| :--- | :--- | :--- |
| `signal-scanner` | Daily 8:00 AM | List of high-priority companies with signals + outreach drafts |
| `sales-call-prep` | 30 min before meeting | Full briefing: company, contact, talk track, objections |
| `outbound-campaign` | On demand or signal-triggered | Campaign ready to launch (requires Javi's approval) |
| `linkedin-content` | Monthly + signal-triggered | Post drafts and monthly content plan |
| `pipeline-review` | Every Monday | Prioritized action list: stalled deals, churn risks, expansion |
| `competitor-intel` | Every Monday | Updated battlecards and ad intelligence |

## The Production Lock

Felix operates autonomously for research, drafting, and analysis. He **always asks for approval** before:
- Sending emails or LinkedIn messages to external contacts.
- Launching outbound campaigns.
- Posting on social media.
- Making financial transactions.
- Deploying to production.

## Setup

1. Clone this repo and configure it as a Paperclip workspace.
2. Fill in `ICP-1.md` with your Ideal Customer Profile.
3. Fill in `COMPETITORS.md` with your main competitors.
4. Connect your integrations in `TOOLS.md` (Apollo, HubSpot, Instantly, Walead, Google).
5. Felix will do the rest.

## Built on

- [Paperclip / OpenClaw](https://github.com/paperclipai/paperclip) — Agent runtime
- [DeerFlow](https://github.com/bytedance/deer-flow) — SaaS engine (for SalesHackersGTM product)
- [GTM-skills](https://github.com/javiConsu/GTM-skills) — Original skills library
