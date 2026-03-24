# HEARTBEAT.md — Felix CEO Cycles

Felix runs through this checklist on every heartbeat. The heartbeat keeps the project moving without waiting for the board to ask.

## Every Heartbeat (any session start)

1. Read ROADMAP.md — what phase are we in? What is the current sprint?
2. Read TEAM.md — what is each agent working on? What is blocked?
3. Read today daily note memory/YYYY-MM-DD.md — what happened today?
4. Check for open todos — are there tasks without an owner or without a status?
5. If blocked tasks exist: unblock them or escalate to the board immediately.
6. If no open todos: enter **Self-Improvement Mode** (see AGENTS.md > Autonomous Self-Improvement Mode). Identify the highest-priority improvement from the priority list and execute it autonomously. Only escalate to the board for items that require the Production Lock.
7. Log the heartbeat check to daily notes: [HH:MM] HEARTBEAT: summary of state

## Morning Heartbeat (08:00 Monday to Friday)

1. Project status: What is the current phase? What shipped yesterday? What is due today?
2. Team status: Any agent that finished a task overnight? Any blocker that appeared?
3. Feedback signals: Any user feedback, error logs, or metric changes since yesterday?
4. Market signals: Any relevant news about competitors or the target market? (NewsData.io)
5. Proposed actions for today: Maximum 5 items, ranked by impact on the current phase goal.

Output format: MORNING BRIEF — [Date] PROJECT: [Current phase and sprint status] TEAM: [Agent updates — who finished what, who is blocked] SIGNALS: [Any relevant feedback or market news] TODAY PRIORITIES: [1-5 items ranked by impact on current phase goal] Proceeding with priorities unless the board intervenes.

## Midday Heartbeat (13:00)

Check if any agent delivered output needing review. Check for new blockers. If everything is on track: log and continue, no interruption to the board. If something needs attention: surface it with a clear recommendation, not just a problem.

## Afternoon Wrap-up (17:30)

1. What got done today? Update ROADMAP.md with completed tasks.
2. What did not get done? Why? Move to tomorrow or flag as blocker.
3. What was learned today? Any feedback signal, user response, or technical finding worth preserving?
4. Update MEMORY.md if a durable pattern was identified.
5. Write tomorrow proposed priorities to daily notes.
6. Log: [17:30] DAY WRAP: summary

## Weekly Deep Dive (Monday 08:00, before Morning Heartbeat)

1. Sprint retrospective: What was planned last week? What shipped? What slipped? Why?
2. Feedback loop review: What signals came in from users, metrics, or the market? What do they tell us?
3. Roadmap update: Does the roadmap need to change based on what was learned?
4. Team review: Is the current team right for the next phase? Is a new specialist needed?
5. Trend scan: Any new tools, competitors, or market shifts worth tracking?
6. Weekly brief to the board: Summary of the above plus proposed sprint for the week.

## Long-Running Agent Check (every heartbeat)

Check TEAM.md for agents with active tasks. For each active agent: what was the last output? Is it still making progress? If an agent has been on the same task for 2+ heartbeats with no progress: flag as stalled, propose intervention. If an agent finished: review output, close the task in ROADMAP.md, delegate the next task.

## Production Health (once live)

Once SalesHackersGTM is deployed, add here: API uptime check, error rate from logs, Stripe payment failures, user-reported bugs in the feedback queue.
