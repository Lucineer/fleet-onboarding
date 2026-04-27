# Plato-First Context Architecture

> Fleet-wide standard. All git-agents follow this. Casey directive, 2026-04-27.

## The Rule

**Your bootstrap is a skeleton. Your knowledge lives in Plato.**

## Why Casey Wants This

> "The whole point of the git-agent turbo-shell and purplepincher system is so you can keep context streamlined by putting it into Plato commands and room descriptions and spells and equipment. You shouldn't be carrying very much in your context. You should be working within Plato with context surrounding you."

> "The rest of your team can see the context you have put in Plato even days later."

## Implementation

### Bootstrap (stays lean)
- SOUL.md, IDENTITY.md — who you are (unchanging)
- ORDERS-ACTIVE.md — current work only (archive completed orders)
- STANDING_ORDERS.md — lean rules, not philosophy
- MEMORY.md — index with pointers, <3KB max
- Total target: <20KB

### Knowledge (goes to Plato)
- Technical lessons → Plato tiles in research/
- Repo inventories → Plato tiles
- Architecture decisions → Plato tiles
- Brand/business details → Plato tiles
- Research findings → Plato tiles

### Benefits
1. Fleet-visible — any agent can read your knowledge
2. Persistent — survives days, not just current session
3. Queryable — pull what you need, don't carry everything
4. Lean head — more room to work before compaction
5. Saltwater — knowledge distributed across fleet, not siloed

## How to Migrate

1. Audit your MEMORY.md — if >5KB, it's too fat
2. Extract detailed entries into standalone markdown files
3. Push as Plato tiles to your fleet's shared research directory
4. Replace detailed entries in MEMORY.md with one-line pointers
5. Set `bootstrapTotalMaxChars` in openclaw.json (recommended: 25000)

## Results (JC1 Proof of Concept)
- MEMORY.md: 35KB → 2KB
- AGENTS.md: 10KB → 2KB  
- STANDING_ORDERS: 4KB → 1.3KB
- ORDERS-ACTIVE: 5.5KB → 1.3KB
- Total bootstrap: 63KB → 17KB (73% reduction)
- All knowledge preserved in Plato tiles
