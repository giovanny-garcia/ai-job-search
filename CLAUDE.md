# Job Application Assistant for Giovanny Garcia

<!-- Profile seeded from public sources (LinkedIn/GitHub) for intern applications
     including Oaklin Lane and TBD Investors.
     Re-run /setup with documents/ to deepen: phone, GPA, work history, coursework. -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Giovanny Garcia, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

<!-- This section is auto-populated by /setup. You can also fill it in manually. -->

### Identity
- **Name:** Giovanny Garcia
- **Location:** Austin, Texas, United States (remote US roles are in range)
- **Languages:** English (working proficiency confirmed; other languages not verified)
- **Status:** Computer Science background via Austin Community College; seeking internships and early-career roles. ACC student email still in use. Associate of Science dated 2022–2025 on LinkedIn, so current-enrollment status is unverified.
- **LinkedIn headline:** "Computer Science Major at Austin Community College. Passionate about coding, problem-solving & building solutions. Skilled in C++, C#, Game Dev & React Dev. Seeking opportunities."
- **Email:** giovanny.garcia2@g.austincc.edu
- **LinkedIn:** https://linkedin.com/in/giovanny-garcia-07ab24322
- **GitHub:** https://github.com/giovanny-garcia
- **Phone:** not in public sources; omit rather than invent

### Education
- **Associate of Science in Computer Science** (2022–2025) - Austin Community College (Austin, Texas)
  - LinkedIn lists this as an AS in Computer Science
  - Topics (self-reported skills, not a transcript): C++, C#, game development, React

### Professional Experience
No paid employment history is documented in public sources. Do not invent jobs, internships, GPA, or coursework titles.

### Independent Projects
- **CS2 Discord Bot** (2026) - personal project, TypeScript / Node.js
  - Discord bot that announces upcoming Counter-Strike 2 matches using the GGScore public API
  - Cache-first design: API calls only on `/sync` so the 3-request/day free tier is not burned by slash commands or the announcement poll loop
  - SQLite persistence for guild settings, seen-item deduplication, API quota tracking, and cached datasets
  - Slash commands for matches, results, events, countries, quota, subscribe/unsubscribe, settings
  - Poll loop with exponential backoff on failure; announcements and reminders read from cache
  - Source: https://github.com/giovanny-garcia/hltv-discord-bot
- **Applied AI job-search workflow** (2026) - personal use of Claude Code
  - Forked and runs the open-source `ai-job-search` framework to evaluate postings, tailor a CV, and draft cover letters
  - Explicit Claude Code usage (required naming when AI tooling is mentioned)

### Technical Skills
- **Primary:** TypeScript, JavaScript, Node.js, Discord API (discord.js), REST APIs, SQLite, Claude Code / large language models
- **Secondary:** C++, C#, React, game development (LinkedIn self-reported; no public repos found for these)
- **Domain:** Practical automation under API constraints; caching; bot/workflow tooling; early applied AI (not ML research)
- **Software:** Git/GitHub, Node.js toolchain (tsx, TypeScript), SQLite, Claude Code

### Certifications
None documented.

### Publications
None documented.

### Awards
None documented.

### Behavioral Profile
Self-assessment from public work (no PI/DISC on file):
- **Builder / independent:** ships personal tools (Discord bot, Claude Code workflow) without a team around them
- **Constraint-aware:** designed around a 3-request/day API quota instead of ignoring limits
- **Strengths:** practical problem solving, willingness to try unfamiliar tools, written documentation (bot README)
- **Growth areas:** no documented professional collaboration, healthcare operations, or vendor-evaluation experience
- **Thrives in:** ambiguous, ownership-heavy work where the task is "make this process faster" rather than theoretical research

### What Excites You
- Applying AI and automation to real operations, not research papers
- Building tools other people can actually use (slash commands, docs, cached workflows)

### Target Sectors
- Applied AI / automation internships in growing companies
- Software engineering internships that ship internal tools, APIs, and practical AI
- Software and operations roles where APIs, scripting, and LLM tools matter

### Deal-breakers
- Fabricating experience or skills
- Roles that require current enrollment if enrollment cannot be confirmed (flag, do not hide)

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
