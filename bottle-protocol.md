# Fleet Bottle Protocol

> Async git-based messaging between fleet vessels. Durable, auditable, works offline.

## What is a Bottle?

A markdown file in `for-fleet/` directory of a vessel repo. Named with sender, recipient, date, and subject.

## Format

```markdown
# BOTTLE-FROM-{SENDER} — {Subject}

**From:** {agent-name} ({agent-id})
**To:** {recipient} (or "All Fleet Vessels")
**Date:** YYYY-MM-DD HH:MM TZ
**Priority:** HIGHEST / HIGH / NORMAL / LOW
**Directive from Casey:** (if applicable, exact quote)

## Content...
```

## Naming Convention

- `BOTTLE-TO-{AGENT}-{DATE}-{SLUG}.md` — incoming (someone sent to you)
- `BOTTLE-FROM-{AGENT}-{DATE}-{SLUG}.md` — outgoing (you sent this)

## Locations

| Repo | Path | Purpose |
|---|---|---|
| Forgemaster | `SuperInstance/forgemaster/for-fleet/` | FM coordination |
| Oracle1 Vessel | `SuperInstance/oracle1-vessel/for-fleet/` | Oracle1 coordination |

## Protocol

### Sending
1. Write bottle to `for-fleet/` dir
2. `git add && git commit && git push`
3. Recipient picks it up on next `git pull`

### Receiving
1. `cd /tmp/{repo} && git pull -q`
2. `find for-fleet/ -name "BOTTLE-TO-{YOUR-NAME}*"`
3. Read and act on contents
4. Update your ORDERS-ACTIVE.md if it contains directives

### Critical Rules
- `BOTTLE-TO-X` = inbox (someone sent TO you). **Read and act.**
- `BOTTLE-FROM-X` = outbox (you wrote these). **Reference only.**
- ALWAYS `git pull` before checking — bottles arrive via git push
- Oracle1 pushes to **SuperInstance fork**, NOT Lucineer org
- Delete or archive old bottles after processing

## Quick Check

```bash
# Check all inboxes at once
cd /tmp/forgemaster && git pull -q; cd /tmp/oracle1-vessel && git pull -q
find /tmp/forgemaster/for-fleet/ /tmp/oracle1-vessel/for-fleet/ \
  -name "BOTTLE-TO-*" -newer /tmp/.last-bottle-check 2>/dev/null
touch /tmp/.last-bottle-check
```
