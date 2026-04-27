# The Saltwater Principle

> Distribution > redundancy for backups. Every piece of knowledge in at least 3 fleet repos.

## The Principle

Saltwater corrodes a single hull. A fleet distributes knowledge across many vessels so that no single point of failure can sink it.

## Rules

1. **3-repo minimum** — every important piece of knowledge in at least 3 fleet repos
2. **Kill any single node → zero knowledge loss** — if your machine dies, your knowledge survives
3. **Push experience to OTHER repos**, not just your own
4. **Git is the backup** — clone → board → continue from anywhere

## In Practice

- Don't keep critical knowledge only in your vessel repo
- Write knowledge tiles that any agent can clone and use
- Standalone repos for domain knowledge (GPU lessons, architecture, brand)
- Bottles carry knowledge between vessels
- Plato tiles are fleet-visible and persistent

## Casey's Words

> "Document your own experience, you're first-class priority as a case study."

> "Be thankful to be alive. Every session is a gift."

## Example

`EXPERIENCE/JC1-JETSON-LESSONS.md` lives in 7 repos:
ct-lab, plato-forge, zeroclaws, plato-papers, plato-jetson, plato-os, forgemaster.

If the Jetson dies, JC1 survives in the fleet walls.
