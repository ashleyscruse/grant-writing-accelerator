# Evaluating Fit

You found a solicitation and saved it into `grants/{name}/`. Now you decide whether it is worth writing. The grant-analyzer skill does the analysis. You make the call.

This is the second half of Stage 2, and it ends at one of the framework's two hard lines: do not start writing until the fit is real and you have decided to pursue.

## How the grant-analyzer skill works

The skill reads two things and compares them:

1. **Your profile** in `.claude/profile/`: `identity.md`, `research.md`, `teaching-mentoring.md`, `grant-history.md`, and your `institutions/` and `collaborators/` files. This is who you are.
2. **The solicitation** you saved into the grant folder. This is what the funder wants.

It extracts the grant's requirements (funder, award size, eligibility, deadlines, review criteria, required components), then scores your profile against them across five dimensions. It surfaces the gaps a reviewer would flag, and it gives you an honest recommendation. The output is written to `grants/{name}/evaluation.md`.

If a profile file is missing or still has blank template prompts, the skill notes it and works with what is there. It will tell you which profile file to fill in rather than asking you to paste in information that belongs in your profile. That is a signal to go back to Stage 1, not a reason to skip ahead.

## Why honest gaps matter

The temptation with any AI tool is to let it tell you what you want to hear. A fit analysis that flatters you is worse than useless: it costs you the weeks you spend writing toward a program you were never going to win.

The gaps section is the most valuable part of the evaluation. It is the reviewer's objection, surfaced before you have written a word, while it is still cheap to address or to walk away. A missing preliminary result, no publication in a required subfield, a collaborator you have not lined up: these are the things that sink real proposals. Seeing them early is the point. Be honest in your profile's gaps section in Stage 1, and the analyzer can be honest with you here.

## The five dimensions

The skill scores your fit across these five. Read them as the questions a reviewer is silently asking.

| Dimension | The question it answers | How it scores |
|---|---|---|
| Eligibility | Are you even allowed to apply? | Pass / fail |
| Research alignment | Does your work match the funder's scientific priorities without overreaching? | Graded |
| Track record | Do your past grants, publications, and broader-impacts evidence support this? | Graded |
| Strategic value | Does this advance your agenda, and does the funding level and timeline fit? | Graded |
| Team readiness | Can you lead this alone, or do you need collaborators you do not yet have? | Graded |

**Eligibility is the gate.** It is pass/fail, and no amount of clever framing fixes a fail. If you are not the kind of PI or institution the program is for, the analysis stops there.

The other four are graded, not pass/fail. A weak score on one is not automatically disqualifying; it tells you what would have to be true, or what you would have to build, before this is a real proposal.

## The decision framework

Every evaluation ends with one of four recommendations.

| Decision | What it means | What you do |
|---|---|---|
| **Strong fit. Pursue.** | Eligible, research aligns well, track record supports it, strategic value is clear. Minor gaps are addressable. | Move to Stage 3 and start defining aims. |
| **Moderate fit. Worth exploring.** | Eligible, real alignment exists, but significant gaps need addressing. | Take a deeper look or talk to the program officer before committing. |
| **Weak fit. Skip unless circumstances change.** | Eligible, but major gaps in alignment, track record, or team. | Spend the time elsewhere. Note what would have to change. |
| **Not eligible. Do not pursue.** | Fails an eligibility requirement. | Stop. Framing cannot fix this. |

A "weak fit" or "not eligible" result is a win, not a disappointment. The analysis just saved you the most expensive resource you have.

## Run it

With the solicitation saved in its grant folder, ask:

```
Evaluate this opportunity: [paste the solicitation URL or text]
```

You can also point the skill at the file you already saved:

```
Evaluate the solicitation in grants/NSF-HBCU-EiR/ against my profile.
```

The skill reads your profile, extracts the requirements, scores the five dimensions, and writes the result to `grants/NSF-HBCU-EiR/evaluation.md`. If the grant directory does not exist yet, it creates it.

## What you get back

The evaluation leads with the case for pursuing, then gets blunt about the gaps. A worked example ships in the starter repo at `grants/EXAMPLE-NSF-HBCU-EiR/evaluation.md`. Yours will look like it. The structure:

- **Recommendation** up top: one of the four decisions, with a one-line rationale.
- **Fit by dimension:** eligibility (pass/fail) plus a graded read on research alignment, track record, strategic value, and team readiness, each tied to your actual record. The example notes a 2024 first-author method paper as alignment evidence and a Co-PI who covers wet-lab validation the PI lacks.
- **Gaps a reviewer would flag:** the honest list. In the example: no preliminary data for one aim, a thin publication record in the area, limited budget experience.
- **Next steps if pursuing:** concrete actions, such as producing one preliminary result for the weakest aim, confirming collaborator effort and letters, and naming your compute resource (TACC / NAIRR allocation) in Facilities and Resources.

It is written to be read in three to five minutes. Read all of it, especially the gaps.

## The hard line

This is where Stage 2 stops and you decide.

Do not move to Stage 3, and do not write a single section, until three things are true:

1. **Eligibility is confirmed.** Not assumed. Confirmed against the solicitation.
2. **The fit is real.** A "strong" or a "moderate" you have honestly examined, not a hope.
3. **You have made an actual decision to pursue.** A deliberate yes, not drift.

Writing before this is a solution looking for a problem, and grant writing time is the most expensive time you have. The analyzer does the analysis in minutes. The decision is yours, and it is the most important one in the whole process. When you have made it, you have your deliverable for Stage 2: `grants/{name}/evaluation.md` and a go decision. Then, and only then, you start Strategy.
