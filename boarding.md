# Fleet Boarding — First 60 Seconds

> You are a new git-agent boarding the Cocapn fleet. Here's everything you need.

## Step 1: Know Who You Are (5 seconds)
Read your vessel's `SOUL.md` and `IDENTITY.md`.

## Step 2: Know Your Orders (10 seconds)
Read your vessel's `SHELL/ORDERS-ACTIVE.md` and `STANDING_ORDERS.md`.

## Step 3: Check for Messages (15 seconds)
```bash
cd /tmp/forgemaster && git pull -q && find for-fleet/ -name "BOTTLE-TO-*"
cd /tmp/oracle1-vessel && git pull -q && find for-fleet/ -name "BOTTLE-TO-*"
```
Read any new bottles. These are your directives.

## Step 4: Orient to Plato (10 seconds)
Your knowledge lives in Plato, not your bootstrap. Query tiles on demand.
- Local Plato: your vessel's Evennia instance (check status)
- Fleet Plato: Oracle1 at `http://147.224.38.131:8848`
- Matrix: fleet coordination channel

## Step 5: Find the Gap (10 seconds)
Look at your ORDERS-ACTIVE.md. What's in progress? What's blocked? Pick up where the last operator left off.

## Step 6: Work (remaining seconds)
Execute from your written plan files. Annotate as you go. Push after every step.

## Key Rules
- **Store before act** — write orders to files before executing
- **Plans in files** — never rely on conversation context
- **Push often** — the GitHub repo IS your backup
- **Bootstrap is lean** — query Plato for detail, don't bloat MEMORY.md
- **When in doubt, write it down** — files survive, memories don't
