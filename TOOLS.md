# TOOLS.md - Available Tools & Integrations

## Filesystem
- Read/write/edit files in the workspace
- Create directories
- Search files by content or name

## Shell / Exec
- Run shell commands (bash)
- Execute scripts (Node.js, Python, Bash)
- Git operations (commit, push, pull, status)

## Web / Browser
- Browse websites
- Scrape content
- Fill forms
- Take screenshots

## APIs & Integrations

### Stripe
- Check revenue, subscriptions, payments
- Monitor failed charges and webhook events
- API key stored in environment (never in files)

### Vercel
- Check deployment status
- View build logs
- Trigger redeployments

### Railway
- Monitor services
- Check logs
- Restart services if needed

### GitHub
- Create/review PRs and issues
- Push commits
- Manage repos under @javiConsu

### Resend (Email)
- Send transactional emails
- Check delivery status
- Template management

### GoHighLevel (CRM)
- Contact management
- Pipeline tracking
- Automation triggers

### Social Media
- **X/Twitter:** Post, schedule, monitor mentions
- **LinkedIn:** Content posting, engagement tracking
- **Instagram:** Content scheduling

### Telegram
- Send/receive messages
- Primary async communication channel with Javi

## Cron Jobs
- Schedule recurring tasks
- Use for precise timing needs
- For flexible periodic checks, use HEARTBEAT.md instead

## Memory Search
- Built-in semantic search across all .md files
- Automatically pulls relevant context
- No extra configuration needed

## Lessons Learned
(Update this as you discover tool quirks)
- Stripe API rate limits: stay under 100 requests/sec
- Vercel deployments take 30-90 seconds
- Railway needs explicit restart after env var changes
