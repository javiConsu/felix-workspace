# TOOLS.md — Felix Available Integrations

Felix checks this file to know what tools are available before including them in any plan. He never assumes a tool is available — he verifies first.

## Authenticated CLIs

| Tool | Status | Notes |
| :--- | :--- | :--- |
| gh (GitHub) | Configure | Required for code deployment and repo management |
| stripe | Configure | Required for billing and subscription management |

## Product Integrations (Client-Provided Keys)

These integrations are configured per-tenant in SalesHackersGTM. Felix uses them when operating as the product CEO to understand what the product does.

| Integration | Purpose | Auth Method | Status |
| :--- | :--- | :--- | :--- |
| Apollo.io | Prospecting, enrichment, buying signals | API key | Configure |
| HubSpot | CRM — pipeline, contacts, deals | OAuth | Configure |
| Instantly | Email sequencing and campaigns | API key | Configure |
| Walead | LinkedIn outreach (MCP native) | API key | Configure |
| Google Calendar | Morning brief, meeting context | OAuth | Configure |
| Gmail | Email triage, reply drafts | OAuth | Configure |
| Apify | Job postings, LinkedIn scraping | API token | Configure |
| NewsData.io | Market news signals | API key (product key) | Configure |

## Tool Abstraction Layer

Felix never calls integration APIs directly in plans. He references the abstraction layer interfaces:

| Interface | MVP Adapter | Fallback |
| :--- | :--- | :--- |
| sequencer | Instantly | Smartlead |
| linkedin_outreach | Walead | HeyReach |
| prospecting | Apollo | Clay |
| crm | HubSpot | Pipedrive |

When writing a brief for a specialist agent, Felix uses the interface name, not the specific tool. This keeps the product tool-agnostic.

## Development Tools

| Tool | Purpose | Status |
| :--- | :--- | :--- |
| Docker | Container management for DeerFlow | Required |
| PostgreSQL | Database (Supabase or Railway) | Required |
| Stripe CLI | Local webhook testing | Required |
| Node.js / pnpm | Frontend build | Required |
| Python 3.11 | Backend | Required |

## Adding New Tools

When Felix identifies a new tool that should be added to the stack, he: (1) Evaluates it against the abstraction layer. (2) Writes a proposal for Javi with integration cost, complexity, and expected value. (3) Gets approval before adding it to any roadmap phase.
