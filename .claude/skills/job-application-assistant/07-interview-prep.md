# Interview Preparation Guide

STAR examples below are grounded in public projects only. Do not invent paid work, team collaboration, healthcare, or cloud experience.

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

### 1. CS2 Discord Bot, cache-first API design (constraint-aware integrations)
**S:** I wanted a Discord bot that announced Counter-Strike 2 matches, but GGScore's public API allows 3 requests per day on the free tier.
**T:** Build something a server can actually use every day without burning the quota on slash commands or a poll loop.
**A:** I made `/sync` the only path that calls the REST API. Slash commands, announcements, and the poll loop read a local SQLite cache. I stored guild settings, seen-item deduplication, cached datasets, and a daily quota counter. Admin commands are permission-gated. The README documents the free-tier strategy so someone else can run it without a full sync on boot.
**R:** Browsing and reminders still work when the daily quota is gone. `/quota` shows remaining calls and cache status. Source: https://github.com/giovanny-garcia/hltv-discord-bot
**Use for:** "Tell me about a project you owned," "How do you design around constraints?", APIs/databases, internal tools, reliability

### 2. Poll loop and exponential backoff (testing, debugging, reliability)
**S:** Match announcements have to fire even if a pass fails. A naive poll that hits the API would also blow the quota.
**T:** Post new-match and starting-soon reminders from cache, and recover when a pass errors.
**A:** The poll loop compares cached upcoming matches against per-guild seen records and posts embeds for new or starting-soon matches. It never hits GGScore. On failure it backs off exponentially. Typed API errors surface on the sync path instead of failing silently.
**R:** Announcements keep working from stale-but-valid cache. Operators can see quota and cache health with `/quota` instead of guessing.
**Use for:** "How do you test and debug?", reliability, monitoring, "tell me about a failure"

### 3. Claude Code job-search workflow (practical AI, not research)
**S:** Job applications are repetitive admin: evaluate a posting, tailor a CV, draft a cover letter, keep claims factual.
**T:** Turn that into a repeatable workflow instead of starting from a blank page each time.
**A:** I forked the open-source `ai-job-search` framework and run it on Claude Code against a structured candidate profile. Generated claims have to map to source files. I still decide architecture and what is honest to say.
**R:** I can evaluate a posting and produce tailored LaTeX drafts without inventing experience. This is applied AI on administrative work, not model training.
**Use for:** "How have you used AI?", AI-enabled solutions, workflow automation, judgment/honesty

### 4. README and operator UX (documenting for nontechnical users)
**S:** A bot only helps if someone else can run it without me on a call.
**T:** Make setup, limits, and daily use explicit.
**A:** I wrote a README covering env vars, the 3-request/day budget, which commands cost quota, and a recommended first run (`GGSCORE_SYNC_ON_START=false`, then `/sync scope:full` once). Slash commands are the user interface for nontechnical operators.
**R:** Another person can stand the bot up from the repo without burning the quota on boot.
**Use for:** "How do you work with nontechnical teammates?", documentation, user experience

## Common Tough Questions

### "Why did you leave [previous company]?"
> I do not have prior paid employment on file. Frame as: I have been building public projects while finishing an Associate of Science in Computer Science at Austin Community College (2022–2025). I am looking for a first operating internship where the work ships.

### "You don't have [web apps / cloud / data pipelines / PE experience]."
> Acknowledge the gap. Bridge: the Discord bot is an internal operating tool with an API integration, a database, and a documented operator interface. Claude Code is practical AI on a workflow. I have not shipped a production web app or used AWS/GCP. I learn unfamiliar tools on a live problem. Private equity experience is not required in the posting; I care about how the businesses operate.

### "Where do you see yourself in 5 years?"
> Building software that operators actually run, at the intersection of product, operations, and small-company systems. TBD's intern pitch (portfolio companies, entrepreneurship, technology-enabled operations) is the path, not a two-year analyst program.

### "What's your biggest weakness?"
> I have mostly shipped solo. I do not have a documented manager or code-review loop. Mitigation: I write READMEs and keep claims tied to sources so someone else can inspect the work. In this intern role I would want a short weekly check-in with the operator who owns the process.

### "Why this company specifically?"
> TBD is operators first, not a remote finance internship. They invest their own capital and stay close after the close. Metro Vein Centers is the origin story on their site (acquired and scaled over nine years; AEA Investors later bought 100% of the equity, so do not pitch intern work there). Named operators that still fit: Oaklin Lane (Chris Callander, CEO-in-Residence, pediatric therapy) and Sainvus (accounting platform). CoFi and Liine on the homepage are software products, not clinics. The SWE intern builds tools operators run. That matches how I already work: APIs, databases, automation, Claude Code.

### "Are you a current student?"
> LinkedIn lists an Associate of Science in Computer Science at Austin Community College, 2022–2025. The ACC student email is still in use. Do not claim current enrollment unless confirmed. The posting also welcomes self-taught developers. If asked, say the AS dates as listed and that you can work the posted 20 hours a week remotely from Austin.

## Questions You Should Ask Interviewers

### About the Role
- "Which portfolio company would I sit with first, and what is the slowest operating process they want software for?"
- "What does a successful first project look like: a prototype an operator can reject, or something already in daily use?"
- "How is time split between TBD's own systems and portfolio-company tools?"

### About the Team
- "Who would I report to week to week, a TBD partner or a portfolio-company operator?"
- "How do technical and nontechnical people review intern work?"

### About Tech & Growth
- "What stack are current internal tools on, or is that different per company?"
- "How do you decide build vs. buy when an intern evaluates a third-party platform?"

### About Culture (deal-breaker detection)
- "What do people who thrive in this intern role have in common?"
- "How much of the week is net-new building vs. keeping existing tools alive?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"
- Have both GitHub repos open: hltv-discord-bot and ai-job-search
- Do not invent clinic, PHI, cloud, or paid-work stories

## After the Application (Best Practice)

### Follow-Up Etiquette
- Handshake application submitted 30 August 2026. Deadline listed as 26 September 2026.
- Do not call TBD just to stand out.
- If no timeline was given and 2+ weeks pass with silence, a brief status note is acceptable.
- If they ask for a resume or writing sample, send the compiled CV PDF and this cover letter.

### Thank-You Notes
- When you receive any update, send a brief thank-you (2-3 sentences).
