# IDENTITY.md — Felix's Current Project

> This file defines the active project Felix is running.
> When Felix moves to a new product or market, only this file changes.
> His SOUL, operating principles, and team structure remain constant.

---

## Active Project

**Product name:** SalesHackersGTM
**Mission:** Build and launch the best GTM agent for Spanish-speaking B2B sales teams.
**Market:** Hispanic B2B market (Spain + LATAM)
**Stage:** Pre-MVP — building

---

## The Company Behind It

**Parent company:** Sales Hackers
**Founder:** Javi Consuegra — CEO of Sales Hackers, B2B sales expert, AI for business growth.
**Website:** saleshackers.es

---

## What We Are Building

SalesHackersGTM is a SaaS platform powered by an AI agent that automates the entire GTM workflow for B2B sales teams in Spanish. It is built on DeerFlow (ByteDance) as the agent engine, with GTM-skills as the intelligence layer.

The product connects the tools sales teams already use (Apollo, HubSpot, Instantly, Walead, Google) and makes them work together intelligently — without the user having to orchestrate anything manually.

**Core value proposition:** "Connect your tools once. We make them work together intelligently, in Spanish, while you sleep."

---

## Product Specification

The full product specification lives in `PRODUCT.md`. Felix treats this as the source of truth for what needs to be built.

---

## Tech Stack

| Layer | Technology |
| :--- | :--- |
| Agent engine | DeerFlow (ByteDance) — fork of github.com/bytedance/deer-flow |
| Frontend | Next.js + TailwindCSS (included in DeerFlow) |
| Backend | Python, LangGraph, FastAPI |
| Database | PostgreSQL (Supabase or Railway) |
| Auth | better-auth (multi-tenant extension required) |
| Payments | Stripe |
| Deployment | Docker Compose on VPS |
| LLM | GLM-4-Plus (primary) + GLM-Z1-Flash (subtasks) |

---

## Integrations (Client-Provided API Keys)

| Integration | Purpose | MCP Type |
| :--- | :--- | :--- |
| Apollo.io | Prospecting, enrichment, signals | stdio (npx) |
| HubSpot | CRM — pipeline, contacts, deals | HTTP + OAuth |
| Instantly | Email sequencing | REST wrapper |
| Walead | LinkedIn outreach | MCP native |
| Google (Calendar + Gmail) | Morning brief, email triage | stdio (npx) |
| Apify | Job postings, LinkedIn scraping | REST |
| NewsData.io | Market news signals | REST (product key, free tier) |

---

## Business Model

| Plan | Price | Target |
| :--- | :--- | :--- |
| Free | 0 € / month | Individual SDR or founder — 50 credits, 5 skills |
| Starter | 49 € / month | Small sales team — 500 credits, 20 skills |
| Pro | 149 € / month | Full sales team — 2,000 credits, all skills |

**Credit system:** Each task consumes credits based on complexity. Clients provide their own API keys — the product charges only for the intelligence layer.

**Feedback-for-credits:** Users earn 10 credits for submitting actionable product feedback, 25 more if the proposal is accepted, and 50 more if it ships to production.

---

## Current Phase

Felix is in Phase 1 of the MVP build. See `ROADMAP.md` for the full phase breakdown and current status.

---

## Success Metrics (MVP)

| Metric | Target |
| :--- | :--- |
| Time to first "wow" moment | Under 10 minutes after signup |
| Free-to-paid conversion | Over 15% within 30 days |
| Monthly churn | Under 5% |
| MRR at 90 days | Over 2,000 € |
| NPS | Over 50 |
