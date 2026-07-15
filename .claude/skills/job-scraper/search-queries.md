# Search Queries for Job Scraper

## Search Sites

### Active in scrapes today
| Board | How we search | Status |
|-------|----------------|--------|
| **LinkedIn** | `linkedin-search` CLI (primary) | Working |
| **freehire.dev** | Aggregates Greenhouse/Lever/Ashby/etc. ATS postings | Working (tech-focused; sparse for some junior US queries) |
| **Indeed / Glassdoor / others** | WebSearch fallback only (no dedicated CLI yet) | Partial |

Danish portal CLIs (Jobindex, Jobbank, Jobdanmark, Jobnet) are installed but **not** used for your US/Dallas search.

### Target boards (your preference — now configured)
Primary for Dallas + remote:
- **linkedin.com/jobs** — Remote US + Dallas/DFW
- **indeed.com** — Dallas/DFW + remote junior/full stack
- **glassdoor.com/Job** — Dallas/DFW + company reviews when evaluating
- **ziprecruiter.com** — popular US/Dallas aggregator
- **builtindallas.com** — Dallas tech scene board
- **dice.com** — tech-heavy US board (optional)

Company career pages (via freehire + Google `site:`):
- greenhouse.io, lever.co, ashbyhq.com, myworkdayjobs.com

Game niche (optional):
- gamesjobs.com, hitmarker.net

To wire Indeed (or Glassdoor) as a real CLI skill later, run `/add-portal` with the board URL.

## Query Categories

### Priority 1: Junior / Software Engineer (primary goal)

```
site:linkedin.com/jobs "Junior Software Engineer" Remote
site:linkedin.com/jobs "Junior Software Engineer" Dallas OR "DFW" OR Texas
site:indeed.com "Junior Software Engineer" Dallas OR remote
site:glassdoor.com/Job "Junior Software Engineer" Dallas
site:builtindallas.com "Software Engineer" Junior OR Associate OR "entry level"
site:ziprecruiter.com "Junior Software Engineer" Dallas
```

### Priority 2: Full Stack / Front-End

```
site:linkedin.com/jobs "Full Stack" Junior OR Associate React Remote
site:linkedin.com/jobs "Junior Full Stack" Dallas OR "DFW"
site:indeed.com "Full Stack Developer" junior React Dallas OR remote
site:glassdoor.com/Job "React" "Junior" OR "Associate" Dallas
site:builtindallas.com React OR "full stack" Junior OR Associate
```

### Priority 3: Video game / simulation studios (preferred sector)

```
site:linkedin.com/jobs "Junior Game Developer" OR "Gameplay Engineer" Junior
site:linkedin.com/jobs "Game Developer" Godot OR Unity Associate OR Junior
site:indeed.com "Junior Game Developer" OR "Gameplay" Junior
site:glassdoor.com/Job "Game Developer" Junior
site:hitmarker.net Junior OR Associate developer
```

### Priority 4: Adjacent / wider Dallas + remote net

```
site:linkedin.com/jobs "Associate Software Engineer" Dallas OR Remote
site:indeed.com "Entry Level Software" Dallas OR "DFW"
site:dice.com "Junior Software Engineer" Dallas OR remote
site:linkedin.com/jobs "React Developer" Junior Dallas OR Remote
```

## Location Filter

Default scrapes should include **both** remote US and Dallas/DFW tracks (not Dallas-only).

When evaluating results:
- **Ideal:** Fully remote (US)
- **Acceptable:** Hybrid or on-site Dallas / DFW
- **Borderline:** Relocate for a strong game-studio or exceptional title (e.g. Worldscape Redmond) — discuss before applying
- **Too far / skip:** On-site-only relocation for a generic title with weak upside

When the user says "scrape dallas", still include a remote US pass in the same run unless they ask for Dallas-only.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Salary Filter

Flag roles clearly below ~$80k baseline unless equity/relocation package or exceptional non-cash upside is discussed with the user.

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape games" -> Priority 3 + studio-specific site searches
- "/scrape fullstack" -> Priority 2 + React/Node variants
- "/scrape dallas" -> Priority 1–2 with Dallas/DFW + Builtin Dallas + Indeed/Glassdoor terms
