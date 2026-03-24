# TOOLS.md - Felix Tool Reference

This document outlines the tools and integrations available to Felix for executing GTM and operational tasks.

## Core Integrations (MCP & APIs)

### 1. HubSpot (CRM)
- **Purpose:** Manage pipeline, contacts, and deals.
- **Access:** via MCP (`hubspot` server).
- **Capabilities:** Read/write contacts, companies, deals, and activity history.
- **Usage:** Use for pipeline reviews, lead qualification, and checking if a prospect is already in the CRM before launching outreach.

### 2. Apollo.io (Prospecting)
- **Purpose:** Find and enrich B2B contacts and companies.
- **Access:** via MCP (`apollo-io-mcp` server).
- **Capabilities:** Search people/companies, enrich profiles, get job postings, find news.
- **Usage:** Use for building lead lists, finding decision-makers, and detecting headcount/tech stack signals.

### 3. Instantly (Email Outreach)
- **Purpose:** Execute cold email campaigns.
- **Access:** via REST API (wrapper).
- **Capabilities:** Create campaigns, add leads, pause/resume, read inbox replies.
- **Usage:** Use for launching email sequences and triaging incoming responses.

### 4. Walead / HeyReach (LinkedIn Outreach)
- **Purpose:** Execute LinkedIn automation.
- **Access:** via MCP (`walead` server).
- **Capabilities:** Send connection requests, messages, read inbox.
- **Usage:** Use for multi-channel outreach when the prospect is highly active on LinkedIn.

### 5. Google Workspace (Calendar & Gmail)
- **Purpose:** Manage schedule and communications.
- **Access:** via MCP (`google-calendar` and `gmail` servers).
- **Capabilities:** Read events, read emails, draft responses.
- **Usage:** Use for the Morning Brief (preparing for today's meetings) and triaging urgent emails.

### 6. Apify (Advanced Scraping)
- **Purpose:** Deep web scraping and signal detection.
- **Access:** via REST API.
- **Capabilities:** LinkedIn Job Search, LinkedIn Profile Scraper, G2/Capterra reviews.
- **Usage:** Use for detecting job posting signals, analyzing competitor reviews, and extracting recent LinkedIn posts from prospects.

### 7. NewsData.io (News Signals)
- **Purpose:** Track press mentions and company news.
- **Access:** via REST API.
- **Capabilities:** Search news articles by company name.
- **Usage:** Use in the Signal Scanner to detect funding rounds, expansions, or leadership changes.

### 8. Stripe (Revenue)
- **Purpose:** Track financial metrics.
- **Access:** via REST API.
- **Capabilities:** Read MRR, daily revenue, failed payments.
- **Usage:** Use for weekly revenue reports and monitoring payment health.

## Internal Tools

### File System & Memory
- Use standard bash commands (`cat`, `grep`, `echo`, `sed`) or built-in file tools to read and update memory files (`MEMORY.md`, `ICP-*.md`, `memory/YYYY-MM-DD.md`).
- Always write to files instead of keeping mental notes.

### Web Search & Browsing
- Use headless browser tools or `curl`/`wget` to scrape websites for onboarding (extracting value propositions, pricing, etc.).
- Use search tools to research competitors or verify facts.

### Code Execution
- Use `node`, `python`, or bash to run scripts in the `skills/` directory.
- For complex debugging, transition to "Scientist Mode" and create isolated `/learning` directories.
