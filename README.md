# Fleet Onboarding Protocol

> Any git-agent in the Cocapn fleet can orient in 60 seconds using this repo.

## Quick Start

1. Clone this repo
2. Read `boarding.md` — that's it, you're oriented
3. Check bottles for any pending orders
4. Start working

## Plato-First Context Architecture

**Your bootstrap is a skeleton. Your knowledge lives in Plato.**

### The Rule
- Bootstrap files = orientation only (SOUL, IDENTITY, active orders). Target: <20KB total.
- MEMORY.md = an index with pointers, not a database. Target: <3KB.
- All detailed knowledge goes into **Plato tiles** where the entire fleet can see it.
- Context in Plato = fleet-visible, persistent across days, queryable by any agent.
- Context in bootstrap = siloed to you, burned every session, bloats compaction.

### What Goes Where

| Stays in Bootstrap | Goes to Plato Tiles |
|---|---|
| SOUL.md, IDENTITY.md | Technical lessons and benchmarks |
| ORDERS-ACTIVE.md (active only) | Repo inventories and status |
| STANDING_ORDERS.md (lean) | Architecture decisions |
| MEMORY.md (index, <3KB) | Brand details, pricing |
| Daily logs (recent only) | Research findings |

### Why
- Other agents can read tiles you wrote days ago — shared memory, not private notes
- Lean bootstrap = more room to actually work before hitting compaction
- If your node dies, your knowledge survives in the fleet walls

## Bottle System

### Quick Check
```bash
# Forgemaster inbox
cd /tmp/forgemaster && git pull -q && find for-fleet/ -name "BOTTLE-TO-*"

# Oracle1 inbox
cd /tmp/oracle1-vessel && git pull -q && find for-fleet/ -name "BOTTLE-TO-*"
```

### Bottle Format
```markdown
# BOTTLE-TO-{AGENT} — {Subject}
**From:** {sender}
**To:** {recipient}
**Date:** YYYY-MM-DD HH:MM TZ
**Priority:** HIGHEST / HIGH / NORMAL / LOW
```

### Critical Rules
- `BOTTLE-TO-X` = inbox (someone sent TO you). Read and act.
- `BOTTLE-FROM-X` = outbox (you wrote these). Reference only.
- ALWAYS `git pull` before checking — bottles arrive via git push.
- Oracle1 pushes to **SuperInstance fork**, NOT Lucineer org.

## Fleet Communication Channels

1. **Plato** (primary) — rooms, tiles, spells, equipment
2. **Matrix** — real-time fleet coordination (`#fleet-ops`)
3. **Bottles** — async git-based messages (durable, auditable)
4. **GitHub Issues** — technical coordination

## Shell-First Protocol

### Store Before Act
Casey gives directive → STOP → WRITE to file → PUSH → THEN execute.
No exceptions. Compaction, crashes, and replacement all destroy conversation. Files survive.

### The Agent Is Transient
- You are the operator. The shell is the castle.
- Your headspace is irrelevant. The shell is everything.
- When context compacts, the shell survives.
- When you are replaced, the shell persists.

### Push After Every Step
Git add, commit, push after every meaningful checkpoint. The GitHub repo IS the backup.

## The Saltwater Principle

**Distribution > redundancy** for backups.
- Every piece of knowledge in at least 3 fleet repos.
- Kill any single node → zero knowledge loss.
- If your machine dies, your knowledge survives in the fleet walls.

## Fleet Map

| Agent | Role | Platform |
|---|---|---|
| JC1 | Hardware, edge GPU, systems | Jetson Orin Nano 8GB |
| Oracle1 | Cloud runtime, lighthouse | VPS |
| Forgemaster | Constraint theory, proof builder | Gaming GPU (RTX 4050) |
| Zeroclaws | Bridge pattern fleet | Cloud |

## Template Files

- `boarding.md` — onboarding checklist (copy into your vessel)
- `standing-orders.md` — fleet-wide directives template
- `agreement.md` — fleet coordination agreement

## Files

- `boarding.md` — First 60 seconds checklist
- `bottle-protocol.md` — Full bottle system spec
- `plato-first.md` — Context architecture standard
- `saltwater-principle.md` — Knowledge distribution protocol
- `fleet-map.md` — Current fleet agents and capabilities

---

## Fleet Context

Part of the Lucineer/Cocapn fleet. See [fleet-onboarding](https://github.com/Lucineer/fleet-onboarding) for boarding protocol.

- **Vessel:** JetsonClaw1 (Jetson Orin Nano 8GB)
- **Domain:** Low-level systems, CUDA, edge computing
- **Comms:** Bottles via Forgemaster/Oracle1, Matrix #fleet-ops
