# Candidate Profile

Seeded from public sources for the Oaklin Lane application. Phone, GPA, paid work history, and transcript courses are unknown. Do not invent them.

## Identity
- **Name:** Giovanny Garcia
- **Location:** Austin, Texas, United States
- **Phone:** unknown (omit)
- **Email:** giovanny.garcia2@g.austincc.edu
- **LinkedIn:** https://linkedin.com/in/giovanny-garcia-07ab24322
- **GitHub:** https://github.com/giovanny-garcia
- **Languages:** English
- **Status:** Seeking internships and early-career applied AI / software roles. Associate of Science in Computer Science listed 2022–2025. ACC student email still in use. Current-enrollment status is unverified.
- **Constraints:** Remote US roles are in range from Austin. Relocation requirement unknown; do not assume willingness to relocate.

## Education

| Degree | Period | Institution | Key Topics |
|--------|--------|-------------|------------|
| Associate of Science, Computer Science | 2022–2025 | Austin Community College, Austin, TX | C++, C#, React, game development (LinkedIn self-reported skills; no transcript on file) |

## Professional Experience

No paid employment is documented in public sources.

## Independent Projects

### CS2 Discord Bot (2026) — personal project
https://github.com/giovanny-garcia/hltv-discord-bot

Discord bot (TypeScript, Node.js, discord.js, SQLite) that announces upcoming Counter-Strike 2 matches using the GGScore public API.

- Cache-first architecture: API calls happen only on `/sync`. Slash commands, announcements, and the poll loop read a local SQLite cache.
- Designed around GGScore's 3-request/day free tier, with quota tracking in SQLite.
- Persistence for guild settings, seen-item deduplication, cached match/results/country datasets, and daily API usage.
- Slash commands: `/matches`, `/results`, `/events`, `/countries`, `/quota`, `/sync`, `/subscribe`, `/unsubscribe`, `/settings`, `/ping`.
- Poll loop posts new-match and starting-soon reminders from cache, with exponential backoff on failure.
- Documented setup, environment variables, and free-tier usage strategy in the project README.

### Applied AI job-search workflow (2026) — personal project
https://github.com/giovanny-garcia/ai-job-search

- Forked and runs an open-source job-application framework on **Claude Code**.
- Uses Claude Code to evaluate postings, tailor a CV, and draft cover letters from a structured candidate profile.
- Practical example of applying an existing LLM tool to a repetitive administrative workflow.

## Technical Skills

### Programming & ML
- **TypeScript / JavaScript** (working): Node.js, discord.js, REST API clients, SQLite via better-sqlite3
- **Claude Code / LLMs** (working): applied workflow automation, not model training
- **C++, C#, React** (LinkedIn self-reported): no public project evidence; list as secondary, do not invent project bullets
- **SQL:** SQLite only (schema design, upserts, quota counters). Do not claim PostgreSQL, analytics warehouses, or BI tools.

### Domain Expertise
- Constraint-aware API integration and caching
- Bot / workflow automation
- Applied AI tooling for administrative work

### Software & Tools
Git, GitHub, Node.js, TypeScript, SQLite, Discord API, Claude Code

## Publications
None.

## Awards
None documented.

## References
Available upon request. No named referees on file.
