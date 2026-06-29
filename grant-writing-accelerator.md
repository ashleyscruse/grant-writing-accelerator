---
name: NAIRR Grant Writing Accelerator (Cohort) — Punta Cana, DR
project_type: workshop
domain:
  - career
status: active
started: 2026-04-21
target: 2026-07-04
entities:
  - "[[morehouse]]"
  - "[[mscf]]"
  - "[[nairr]]"
people:
  - "[[scruse-ashley]]"
program: "[[nairr]]"
tags:
  - teaching
  - workshop
  - nairr
  - mscf
  - cohort
  - grant-writing
  - faculty-development
  - punta-cana
  - summer-2026
---
# NAIRR Grant Writing Accelerator (Cohort)

Week-long faculty cohort (Jun 28 – Jul 4, 2026) in Punta Cana focused on producing a working grant proposal draft with structured curriculum and cohort accountability.

## Quick links
- [[nairr|Back to parent NAIRR program]]
- Public URL: https://www.bpccenter.org/current-programs/nairr-accelerator
- Lead: [[scruse-ashley]] (Deputy Director, MSCF)
- GitHub repo: `morehouse-supercomputing/nairr-grant-writing`

## Tasks
- [x] Applicant intake ✅ 2026-04-21
- [ ] Finalize cohort participant list [due:: 2026-06-14]
- [ ] Travel and logistics: Punta Cana arrangements [due:: 2026-06-17]
- [ ] Develop lesson content for each session [due:: 2026-06-22]
- [ ] Build out grant-writing templates in `resources/` [due:: 2026-06-22]
- [ ] Pre-program participant communications (target funder, working proposal scope) [due:: 2026-06-21]
- [ ] Run the program (June 28 – July 4) [due:: 2026-07-04]
- [ ] Post-program: track participant submissions and outcomes [due:: 2026-10-31]

## Overview — NAIRR Grant Writing Accelerator

**Dates:** June 28 – July 4, 2026
**Location:** Punta Cana, Dominican Republic
**Public URL:** https://www.bpccenter.org/current-programs/nairr-accelerator

## Goal
Deliver the grant-writing track of the NAIRR Accelerator program, equipping participating faculty and researchers with the materials, templates, and structured guidance to prepare a competitive grant proposal during the cohort window.

## Why this matters
Grant writing is a learned skill that most early-career researchers acquire through trial and error. This track provides structured curriculum and templates, paired with cohort accountability, so participants leave with a working draft rather than just notes. Runs through MSCF, parallel to the Research and Curriculum tracks of the broader NAIRR Accelerator.

## Funding & partners
- **Host:** Morehouse Supercomputing Facility (MSCF)
- **Program source:** NAIRR Pilot
- **Lead:** [[scruse-ashley]] (Deputy Director, MSCF)
- **Venue:** Royalton Punta Cana, Dominican Republic

## Deliverables
- Session-by-session lesson materials
- Templates and reference materials (in `resources/`)
- Cohort delivery (live or async sessions)
- Working proposal drafts from each participant
- Post-program submission tracking

## Folder structure
- `lessons/` — session materials
- `resources/` — reference materials, templates
- `getting-started.md` — onboarding doc for participants
- `templates/` — proposal templates and frameworks

## Sister cohorts (separate projects)
- [[research-accelerator|NAIRR Research Accelerator]] (May 31 – Jun 6)
- [[curriculum-accelerator|NAIRR Curriculum Accelerator]] (Jul 26 – Aug 1)

## Status note
The grant-writing track is currently the lightest of the three tracks in terms of pre-built curriculum (Research track has full per-stage docs; this track has folder note + getting-started + templates only). Significant curriculum-build work needed before June cohort.


## Live dashboard

### Open tasks
```dataview
TASK
FROM "morehouse/workshops/nairr/grant-writing-accelerator"
WHERE !completed AND (
  contains(file.path, "grant-writing-accelerator.md") OR
  contains(string(tags), "#task")
)
GROUP BY file.link
SORT due ASC
```

### Due this week
```dataview
TASK
FROM "morehouse/workshops/nairr/grant-writing-accelerator"
WHERE !completed AND due AND due <= date(today) + dur(7 days) AND (
  contains(file.path, "grant-writing-accelerator.md") OR
  contains(string(tags), "#task")
)
GROUP BY file.link
SORT due ASC
```

### Recently completed
```dataview
TASK
FROM "morehouse/workshops/nairr/grant-writing-accelerator"
WHERE completed AND (
  contains(file.path, "grant-writing-accelerator.md") OR
  contains(string(tags), "#task")
)
GROUP BY file.link
SORT completion DESC
LIMIT 5
```
