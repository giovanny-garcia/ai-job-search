# LinkedIn Profile Improvements: Giovanny Garcia

**Profile:** https://www.linkedin.com/in/giovanny-garcia-482376243/  
**Sources used:** GitHub (`giovanny-garcia`), ACC student email, public project READMEs  
**Limitation:** LinkedIn blocks anonymous access, so this is **not** a line-by-line audit of your live page. Paste or export your current About / Experience into this folder (`More → Save to PDF`) for a second pass that matches every existing bullet.

---

## Priority order (do these first)

1. **Headline** — this is what recruiters see in search results
2. **About** — 3 short paragraphs + a skills line
3. **Photo + banner** — clear headshot; simple banner (code editor, ACC, or solid brand color)
4. **Featured** — pin GitHub repos (Discord bot + this job-search repo if you want it public)
5. **Experience / Projects** — rewrite bullets with tools + outcomes
6. **Skills** — add the exact keywords employers search
7. **Open to Work** — green banner for recruiters only if you prefer privacy
8. **Custom URL** — keep `giovanny-garcia-482376243` or request a cleaner vanity if available (`/in/giovanny-garcia-dev`)

---

## Headline options (pick one)

LinkedIn headlines that only say "Student at Austin Community College" or use emoji stacks get skipped. Lead with the role you want, then proof.

**Option A — software / full-stack lean**  
`CS Student at ACC | TypeScript, Node.js, React | Building Discord bots & web apps | Open to internships`

**Option B — backend / APIs lean**  
`Aspiring Software Developer | TypeScript · Node.js · SQLite · APIs | ACC Computer Science | Open to internships`

**Option C — game-curious (only if that is a real target)**  
`Computer Science @ ACC | C++ · C# · TypeScript | Game & Discord tooling projects | Seeking internships`

**Avoid:** emoji walls, "Passionate about coding", "Seeking opportunities" with no skills, "Hard worker / team player".

---

## About section (copy-paste, then edit)

```
Computer Science student at Austin Community College building real projects with TypeScript, Node.js, and web technologies.

I recently shipped a CS2 Discord bot that pulls match data from a public API, caches it in SQLite to stay within rate limits, and announces upcoming matches with slash commands. I care about practical engineering: caching, quota awareness, and clean command UX, not just tutorials.

I am looking for software engineering internships or junior roles where I can contribute to product features, APIs, or tooling. Based in the Austin / Texas area and open to remote.

Tech I use: TypeScript, Node.js, discord.js, SQLite, Git/GitHub. Growing skills in React, C++, and C#.

Open to connecting with recruiters, ACC alumni, and engineers hiring interns.
```

Shorter variant if you want less length:

```
ACC Computer Science student. I build with TypeScript and Node.js — including a CS2 Discord bot with SQLite caching, slash commands, and API quota management.

Seeking software engineering internships (Austin / remote). Happy to share my GitHub: github.com/giovanny-garcia
```

---

## Featured section

Add these as Featured links (order matters; put the strongest first):

| Item | URL | Why |
|------|-----|-----|
| CS2 Discord bot | https://github.com/giovanny-garcia/hltv-discord-bot | Shows shipped TypeScript + APIs + SQLite |
| AI job search framework (fork) | https://github.com/giovanny-garcia/ai-job-search | Shows you use modern AI tooling intentionally |
| Optional: a React or C++ class project | (add when ready) | Round out the stack |

For each Featured item, write a 1-line caption, e.g.  
`TypeScript Discord bot: GGScore API + SQLite cache + slash commands for CS2 match alerts`

---

## Experience / Projects section

If you do not have formal SWE jobs yet, add a **Projects** or **Independent projects** entry (LinkedIn Experience with company = "Personal Projects" or the GitHub org/repo name is fine).

### Project: CS2 Discord Bot | Personal Project | [dates you worked on it]

```
- Built a TypeScript/Node.js Discord bot that announces upcoming Counter-Strike 2 matches using the GGScore API and discord.js
- Designed a cache-first architecture with SQLite so announcements and slash commands stay within a 3-request/day free API tier
- Implemented guild settings, match deduplication, quota tracking, and slash commands (/sync, /matches, /results, /events, /subscribe)
- Documented setup, environment variables, and free-tier usage so others can run the bot locally
```

### Education: Austin Community College

Make sure the education entry includes:

- Degree program (e.g. Associate of Science, Computer Science — use your exact program name)
- Expected graduation or attendance years
- Bullet ideas (only if true): relevant coursework (data structures, OOP, web programming), GPA if strong (3.5+), clubs, hackathons

Example education bullets:

```
- Coursework: data structures and algorithms, object-oriented programming, web development
- Building portfolio projects in TypeScript, React, C++, and C#
```

### Jobs outside tech (keep them)

If you have retail, SEO, tutoring, or other work: keep it. Reframe transferable skills in 2–3 bullets (reliability, client communication, deadlines, tools). Do not invent engineering work into non-engineering roles.

---

## Skills to add (recruiters search these)

Add skills you can defend in an interview. Order by confidence:

**Core (add first)**  
TypeScript · JavaScript · Node.js · Git · GitHub · SQLite · REST APIs · Discord.js · Problem Solving

**Add if you have coursework or projects**  
React · C++ · C# · HTML · CSS · Object-Oriented Programming · Data Structures · Linux

**Skip for now** unless you have proof: Docker, Kubernetes, AWS, Machine Learning, "Full Stack Engineer" as a skill title.

Ask classmates and teammates to endorse your top 3–5 skills after you update.

---

## Photo, banner, and Open to Work

| Item | Guidance |
|------|----------|
| Photo | Face clearly visible, plain background, good lighting. No group crop, no party photo, no logo-only avatar. |
| Banner | Simple: code screenshot, ACC skyline, or solid dark/blue banner with "Software Engineering Intern · Austin, TX" text (Canva works). |
| Open to Work | Turn on. Prefer **recruiters only** if you do not want classmates to see the green banner. Titles: Software Engineering Intern, Junior Software Developer, Backend Developer Intern. Locations: Austin, TX + Remote. |

---

## Activity that actually helps (15 min / week)

1. Comment thoughtfully on 2–3 posts from Austin tech people or ACC CS alumni (not "Great post!").
2. Once a month, post a short build note: "Shipped X. Learned Y. Next Z." with a GitHub link.
3. Connect with a short note, not blank invites:

```
Hi [Name] — I'm a CS student at ACC building TypeScript projects (including a Discord bot with API caching). I'd love to connect as I look toward software internships in Austin.
```

---

## Checklist before you call it done

- [ ] Headline has target role + 2–4 concrete skills + ACC
- [ ] About mentions one shipped project with tools
- [ ] Featured pins at least one GitHub repo
- [ ] Experience/Projects bullets start with verbs and name technologies
- [ ] Skills list matches keywords in junior/intern job posts you want
- [ ] GitHub link in Contact info / About / Featured
- [ ] Open to Work configured for intern + junior titles
- [ ] No emoji spam; no empty sections left as LinkedIn defaults
- [ ] Export PDF (`More → Save to PDF`) into `documents/linkedin/` so this repo can tailor CVs against the same content

---

## Next step in this repo

1. Update LinkedIn using the copy above.
2. Save to PDF → drop it in `documents/linkedin/`.
3. Run `/setup` (or ask the agent again) to sync your candidate profile, then we can tailor applications to real job posts.
