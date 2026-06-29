# Finding Opportunities

Stage 2 of the framework is Opportunity: find funding, then evaluate fit honestly before you invest any writing time. This page covers the finding half. The next page covers the fit half.

The goal here is not to collect as many opportunities as possible. It is to surface the few that are worth a closer look, get one into your workspace, and read it fast enough that you can make a go / no-go call without burning a week on it.

## Where faculty find grants

You do not need a single perfect source. You need two or three that match how you work, plus an alert so they come to you.

| Source | What it covers | Good for |
|---|---|---|
| grants.gov | The federal clearinghouse for almost every U.S. agency NOFO | Catch-all federal search, alerts by keyword and agency |
| NSF program pages and funding search | NSF solicitations, Dear Colleague Letters, program deadlines | CISE, NAIRR-aligned compute and AI programs, CAREER, EiR |
| NIH Guide / RePORTER | NIH RFAs, PAs, parent announcements, funded-project history | Biomedical work, seeing what NIH has actually funded |
| Foundation portals | Sloan, Moore, Simons, Chan Zuckerberg, regional funders | Non-federal, faster cycles, less compliance overhead |
| Your sponsored programs office | Internal limited-submission lists, institutional pipelines | Programs that cap how many your institution can submit |
| Pivot / GrantForward (if your institution licenses one) | Aggregated federal plus foundation, profile-matched | One feed across many funders |

A few notes specific to this cohort:

- **NAIRR-aligned programs.** If your project uses national AI research infrastructure (NAIRR pilot allocations, TACC, NSF ACCESS), watch NSF CISE and the cross-agency AI solicitations. These reward proposals that name the compute resource explicitly. Keep that detail handy; you will reuse it.
- **NOFO, RFP, RFA, PA are all the same animal.** Different agencies use different names for "here is money, here are the rules." Treat any of them as a solicitation you can run through the workflow below.

## Set up alerts so opportunities find you

Searching from scratch every month does not scale. Set standing alerts once and let them work.

- **grants.gov:** save a search with your keywords (for example, `artificial intelligence`, `HBCU`, `broadening participation`) and turn on email notifications.
- **NSF:** subscribe to the program pages and the funding search RSS / email for your directorate.
- **NIH:** subscribe to the NIH Guide weekly listings filtered to your areas.
- **Foundations:** most do not push alerts, so put a recurring calendar reminder to check the two or three portals that matter to you each quarter.

Aim for signal, not volume. If an alert sends you ten irrelevant NOFOs a week, tighten the keywords.

## Use AI to scan a long solicitation fast

A NOFO can run forty pages. You do not read all forty to decide whether it is worth your time. You read AI's structured summary first, then decide whether to read the source.

Paste the solicitation text (or point AI at the saved file) and ask for the parts that decide fit:

```
Summarize this solicitation in under one page. Pull out:
- Funder and program name
- Award size and project period
- Eligibility requirements (PI status, institution type, restrictions)
- Submission deadline and whether there is an LOI
- The review criteria, in priority order
- Required proposal components
Flag anything that would make me ineligible.
```

Then narrow to the question that kills most opportunities early:

```
Based on this solicitation, who is the intended applicant? Describe the
ideal PI, institution, and project in three sentences. Be blunt about who
this program is NOT for.
```

If you want the funder's priorities in their own words, ask:

```
List the exact phrases this solicitation uses to describe what it wants to
fund. I want the funder's language, not a paraphrase, so I can mirror it later.
```

That last one pays off in Stage 4, when you draft sections that mirror the funder's headers and terminology.

## The mindset: evaluate fit before you invest writing time

This is the whole point of Stage 2, and it is the most expensive lesson to learn the slow way.

Grant writing time is the most expensive time you have. A proposal you cannot win costs you weeks you could have spent on one you can. So the order is fixed: find, then evaluate, then decide, then write. Never write first.

AI makes the front of that pipeline cheap. Scanning a solicitation and getting a structured fit analysis takes minutes, not a day. There is no excuse for writing toward a program you have not honestly assessed. The next page covers how the grant-analyzer skill does that assessment.

## Bring the opportunity into your workspace

When a solicitation clears the quick scan and looks worth a real evaluation, give it a home. This is the same per-grant directory pattern you will use through submission.

1. In the `grant-writing-starter` workspace, make a directory under `grants/` named for the program, no spaces. For example, `grants/NSF-HBCU-EiR/`.
2. Save the solicitation inside it as `solicitation.pdf` or `solicitation.md`.
3. Leave the rest of the folder empty for now. The analyzer writes `evaluation.md` here in the next step.

```
grants/
  NSF-HBCU-EiR/
    solicitation.pdf        the original RFP / NOFO you just saved
```

Your profile in `.claude/profile/` says who you are and is shared across every grant. Each folder under `grants/` holds everything specific to one proposal. Getting the solicitation into its folder is the handoff into Evaluating Fit.

The starter repo lives at `github.com/ashleyscruse/grant-writing-starter` if you need to clone it or check the structure.
