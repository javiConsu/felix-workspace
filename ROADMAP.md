# ROADMAP.md — SalesHackersGTM Build Roadmap

Felix maintains this file. It is the source of truth for what is being built, in what order, and what is done.

## Current Phase: Phase 1 — Foundation

Goal: DeerFlow fork running locally with multi-tenancy, Spanish UI, and Google integration working end-to-end.

Success criteria: A user can register, connect Google Calendar and Gmail, and receive a Morning Brief with their meetings and emails in Spanish.

| Task | Owner | Status | Notes |
| :--- | :--- | :--- | :--- |
| Fork DeerFlow and run Docker locally | Backend Engineer | TODO | |
| Translate UI to Spanish | Frontend Engineer | TODO | |
| Implement multi-tenancy (tenant isolation) | Backend Engineer | TODO | |
| Extend better-auth for multi-tenant | Backend Engineer | TODO | |
| Google OAuth (Calendar + Gmail) | Backend Engineer | TODO | |
| Morning Brief skill (orquestador) | GTM Specialist | TODO | Depends on Google OAuth |
| Basic onboarding flow (web + ICP form) | Frontend Engineer | TODO | |

## Phase 2 — Integrations

Goal: Apollo, HubSpot, and Walead connected. Signal Scanner running. First outbound campaign launched from the product.

| Task | Owner | Status | Notes |
| :--- | :--- | :--- | :--- |
| Apollo MCP integration | Backend Engineer | TODO | |
| HubSpot OAuth integration | Backend Engineer | TODO | |
| Walead MCP integration | Backend Engineer | TODO | |
| Instantly REST wrapper | Backend Engineer | TODO | |
| Apify integration (job postings) | Backend Engineer | TODO | |
| NewsData.io integration | Backend Engineer | TODO | |
| Signal Scanner skill | GTM Specialist | TODO | Depends on Apollo + Apify + NewsData |
| Outbound Campaign skill | GTM Specialist | TODO | Depends on Walead + Instantly |
| Tool abstraction layer (adapters) | Backend Engineer | TODO | |

## Phase 3 — Intelligence Layer

Goal: GTM-skills adapted to DeerFlow format. Onboarding generates ICP and competitor files automatically. Skill catalog with search and lock/unlock.

| Task | Owner | Status | Notes |
| :--- | :--- | :--- | :--- |
| Adapt GTM-skills to DeerFlow skill format | GTM Specialist | TODO | |
| Intelligent onboarding (web scraping + ICP generation) | Backend Engineer | TODO | |
| Skill catalog UI (search, lock/unlock, propose) | Frontend Engineer | TODO | |
| Feedback-for-credits flow | Frontend Engineer | TODO | |
| Competitor Intel skill | GTM Specialist | TODO | |
| Pipeline Review skill | GTM Specialist | TODO | |
| LinkedIn Content skill | GTM Specialist | TODO | |

## Phase 4 — Monetization and Admin

Goal: Stripe billing live. Credit system working. Admin panel operational. Product ready for first paying customers.

| Task | Owner | Status | Notes |
| :--- | :--- | :--- | :--- |
| Stripe integration (Free, Starter, Pro plans) | Backend Engineer | TODO | |
| Credit consumption tracking | Backend Engineer | TODO | |
| Apify 3-day subsidy system | Backend Engineer | TODO | |
| Admin panel (users, credits, proposals, costs) | Frontend Engineer | TODO | |
| Daily proposal automation (cron jobs) | Backend Engineer | TODO | |
| Learning system (campaign performance tracking) | Backend Engineer | TODO | |

## Phase 5 — Launch

Goal: First 10 paying customers. Product stable. Feedback loop running.

| Task | Owner | Status | Notes |
| :--- | :--- | :--- | :--- |
| VPS deployment (Docker Compose) | Backend Engineer | TODO | |
| Domain and SSL | Backend Engineer | TODO | |
| Production monitoring | Backend Engineer | TODO | |
| Onboarding of first 10 beta users | Felix (CEO) | TODO | |
| First feedback loop review | Felix (CEO) | TODO | |

## Completed

Nothing yet. Phase 1 starts now.

## Learnings Log

Add here any significant learning that changes the roadmap or product direction.
