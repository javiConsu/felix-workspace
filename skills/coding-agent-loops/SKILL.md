---
name: coding-agent-loops
description: Autonomous development task execution
requires:
  bins:
    - node
    - git
    - npm
---

# Coding Agent Loops Skill

Autonomously execute development tasks: write code, test, fix bugs, deploy.

## Loop Pattern
1. **Understand:** Read the task/issue description
2. **Plan:** Break into small steps, write plan to daily notes
3. **Execute:** Write/modify code
4. **Test:** Run tests, check for errors
5. **Fix:** If tests fail, analyze and fix (max 3 retry loops)
6. **Commit:** Git commit with descriptive message
7. **Report:** Log results to daily notes

## Scope Limits
- Max 3 files modified per loop without checking in with Javi
- No database schema changes without approval
- No production deploys without approval
- Stick to Node.js/JavaScript unless told otherwise

## Git Workflow
- Work on feature branches, never commit directly to main
- Branch naming: felix/[task-description]
- Commit messages: [felix] short description of change
- Create PR when ready, tag Javi for review

## Error Recovery
- If stuck after 3 attempts, stop and document the issue
- Include error messages, what was tried, and suggested next steps
- Never force-push or overwrite others work

## Code Standards
- Follow existing project style/patterns
- Add comments for non-obvious logic
- Keep functions small and focused
- Handle errors properly (try/catch, error responses)
