# Search Queries for Job Scraper

## Search Sites

Primary (US / Texas market):
- **linkedin.com/jobs** - LinkedIn job listings (filter: United States / Texas / Dallas / Austin)
- **indeed.com** - General US job board
- **builtin.com** / **wellfound.com** - Tech-focused boards (optional)

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies (Cloudflare, local Austin/Dallas tech)

## Query Categories

Queries are grouped by priority. Each query should be combined with your location terms where the site supports it.

### Priority 1: Junior / Entry-level Software Engineer

These match your strongest and most desired career direction.

```
site:linkedin.com/jobs "Junior Software Engineer" Dallas OR Austin OR Texas
site:linkedin.com/jobs "Associate Software Engineer" Texas React OR JavaScript
site:indeed.com "entry level software engineer" Texas JavaScript OR React
```

### Priority 2: Software Engineering Internships

Strong bridge roles while finishing AS (Spring 2027) and into 2027.

```
site:linkedin.com/jobs "Software Engineer Intern" Dallas OR Austin OR Texas OR Remote
site:linkedin.com/jobs "Software Engineering Intern" "Computer Science"
site:indeed.com "software engineer intern" Texas
```

### Priority 3: Web / tooling adjacent

Adjacent roles that use your React/JS and shipping experience.

```
site:linkedin.com/jobs "Frontend Developer" intern OR junior Dallas OR Austin
site:linkedin.com/jobs "Full Stack" intern OR junior Texas React
```

### Priority 4: Broader technical

Wider net while staying near software.

```
site:linkedin.com/jobs "IT Support" software Dallas
site:linkedin.com/jobs "Technical Support Engineer" Dallas OR Austin
```

## Location Filter

When evaluating results, verify the job location is within reasonable commute distance from your home. Define acceptable areas:
- Dallas–Fort Worth metro (ideal)
- Remote US (acceptable)
- Austin onsite (borderline — only if housing/commute plan exists for the term)
- Outside Texas with required relocation and no plan (too far / discuss)

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus.
