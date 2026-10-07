# Job Application Assistant for Giovanny Garcia

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Giovanny Garcia, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt the markdown master resume and LaTeX templates to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Giovanny Garcia
- **Location:** Dallas, TX, USA (ACC student; Austin onsite only if commute/relocation works)
- **Languages:** English (fluent), Spanish (fluent)
- **Status:** CS student (AS expected Spring 2027); Search Quality Rater at Welocalize (2024–Present)
- **Website:** https://giovannygarcia.com
- **LinkedIn headline:** CS student | React & API projects | Junior Software Engineer

### Education
- **AS in Computer Science** (Expected Spring 2027) - Austin Community College
  - Coursework: software development and programming fundamentals

### Professional Experience
- **Search Quality Rater** (2024 – Present) - **Welocalize** (Remote)
  - Search quality evaluation, research, remote documentation
- **Repair Technician / Shift Lead** (2022 – 2024) - **Micro Center** (Dallas, TX)
  - Hardware/software repair; mentor technicians; lead shifts
- **Repair Technician** (2018 – 2022) - **Garland Computers** (Garland, TX)
  - Build/repair PCs, laptops, servers; diagnostics and optimization

### Technical Skills
- **Primary:** JavaScript, React, HTML, CSS, Git/GitHub, Discord API
- **Secondary:** Godot/GDScript, Windows/Linux, networking, server admin, AWS exposure, MongoDB exposure
- **Domain:** Client web delivery, automation bots, game shipping, IT support/mentoring
- **Software:** React, GitHub, Godot, Discord API

### Certifications
- None listed yet

### Publications
- None

### Awards
- None listed yet

### Behavioral Profile
- **Hands-on builder** - Ships complete projects (web, bots, games, servers)
- **Mentor / shift lead** - Trains others and owns customer-facing fixes
- **Strengths:** Troubleshooting, finishing projects, bilingual communication
- **Growth areas:** Deeper cloud/backend production experience beyond exposure-level AWS/MongoDB
- **Thrives in:** Mentored teams shipping real product features

### What Excites You
- Shipping software people actually use
- Contributing on a mentored team to real product features

### Target Sectors
- Junior Software Engineer / entry-level SWE
- SWE internships as a bridge into full-time
- Web / product / tooling teams with strong mentorship

### Deal-breakers
- Roles that require skills you cannot truthfully claim
- Austin onsite 3–5 days/week without a workable housing/commute plan from Dallas
- Full-time terms that conflict with required classes before Spring 2027 graduation

## Repo Structure
- `cv/resume.md` - **Master resume (simple markdown). Edit this first.** (copy also kept under `documents/cv/` locally)
- `cv/` - LaTeX CV variants (moderncv template, banking style) for tailored applications
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: update/tailor from `cv/resume.md`, create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`) when needed
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
- [ ] CV follows the chosen format (simple markdown master, or moderncv/banking when LaTeX is used)
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands) when LaTeX is used
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY for LaTeX - never skip)
Both LaTeX documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3 (when using moderncv banking template)
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
