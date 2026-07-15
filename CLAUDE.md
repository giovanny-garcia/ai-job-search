# Job Application Assistant for Giovanny Garcia

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

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
- **Location:** Dallas, TX, USA (prefers remote; open to relocate for an exceptional title, especially at a video game company)
- **Languages:** English (fluent), Spanish (fluent)
- **Status:** Computer Science student at Austin Community College; Search Quality Rater at Welocalize; seeking entry-level Software Engineer / Junior / Full Stack roles
- **LinkedIn headline:** "CS Student | Software & Game Development | Seeking Junior / Full Stack Roles"

### Education
- **Associate of Science in Computer Science** (In Progress, expected December 2026) - Austin Community College
  - Topics: software development, programming fundamentals, systems
  - Note: Considering remaining at ACC rather than transferring; bachelor plans undecided — do not list a BS as a current program

### Professional Experience
- **Search Quality Rater** (2024 - Present) - **Welocalize** (Remote)
  - Evaluated search engine results for relevance, accuracy, and quality across diverse topics
  - Conducted in-depth research and analysis to maintain high evaluation standards
- **Repair Technician / Shift Lead** (2022 - 2024) - **Micro Center** (Dallas, TX)
  - Diagnosed and repaired complex hardware and software issues for customers
  - Trained and mentored new technicians while supporting daily store operations
  - Led shift teams to ensure excellent customer service and efficient workflow
- **Repair Technician** (2018 - 2022) - **Garland Computers** (Garland, TX)
  - Built, repaired, and tested custom PCs, laptops, and servers
  - Performed hardware diagnostics, component replacement, and system optimization
  - Delivered reliable technical solutions for individual and business clients

### Independent Projects
- **Game Development (Godot)** — Indie games with GDScript; published on itch.io (cry0smith.itch.io)
- **Multiplayer Server Administration** — Plugins, config, backups, networking, security, uptime
- **Freelance Web Development** — React / JS / HTML / CSS; client site petalgear.com
- **Discord Automation Bots** — Moderation and workflow bots via Discord API

### Technical Skills
- **Primary:** JavaScript, React, HTML, CSS, Git/GitHub, GDScript/Godot
- **Secondary:** C#, C++, Discord API, AWS, MongoDB
- **Domain:** Game development, web apps, bot automation, IT hardware/software support, server administration
- **Software:** Godot, React, Git, GitHub, Discord API, AWS, MongoDB, Windows, Linux

### Certifications
- None listed

### Publications
- None

### Awards
- None listed

### Behavioral Profile
<!-- Provisional, inferred from experience — refine with /setup --section behavioral -->
- **Hands-on problem solver** - Years diagnosing and fixing hardware/software under customer pressure
- **Builder / maker** - Ships games, bots, and client websites outside formal employment
- **Mentorship & leadership** - Shift lead who trained technicians at Micro Center
- **Strengths:** Practical troubleshooting, shipping projects, bilingual communication, customer-facing composure
- **Growth areas:** Formal software engineering experience in industry teams; depth in a single stack vs. breadth
- **Thrives in:** Remote-friendly, product/build-focused environments (especially games); clear ownership of features

### What Excites You
- Building software and games people actually use
- Working at a video game company
- Full stack / junior software engineering work with room to grow

### Target Sectors
- Video game industry: studios and publishers hiring junior/gameplay/tools/web roles
- Software / product companies: Junior Software Engineer, Full Stack Developer (remote-first preferred)
- Adjacent: React/web development, Discord/community tooling, IT-to-SWE transition roles

### Deal-breakers
- Salary below $80k baseline (unless exceptional non-cash upside clearly discussed)
- On-site-only roles that require relocation without a strong title/company fit (especially non-game)
- Roles with no software-building component (pure hardware bench work as a long-term destination)

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
