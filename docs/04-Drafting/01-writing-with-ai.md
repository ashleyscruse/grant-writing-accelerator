# Writing Sections with AI

Stage 4 is where the proposal gets written. By now you have a confirmed-eligible opportunity, a real fit, defined aims, and a team document. The drafting skill turns that foundation into first drafts of the required sections, mapped directly to the funder's review rubric.

The principle that governs this whole stage is simple: the AI drafts, analyzes, and checks. You own the argument, supply the evidence, and make every claim defensible. The AI does not win you the grant. You win the grant, faster.

## The Drafting Loop

Drafting is a loop you run once per section, not a single pass over the whole proposal.

1. Point the grant-writing skill at one section.
2. It reads your profile (`.claude/profile/`), the grant's `team.md`, and the solicitation, then drafts that section mapped to the relevant scoring criteria.
3. You review the draft against your real record: is every claim supported, is the evidence yours, does the logic hold.
4. You correct, add evidence, and decide what to emphasize.
5. You move to the next section and keep the terminology and numbers consistent with what came before.

Work section by section. The statement of need, the project description, the evaluation plan, and the budget narrative each have their own structure and their own common mistakes. Drafting them one at a time lets you keep each one tight before the next one builds on it.

## The Division of Labor

The fastest way to misuse the AI is to ask it to do your job, and the slowest way to write is to do its job by hand. Keep the line clear.

| The AI does | You do |
|---|---|
| Drafts each section from your profile, team, and decisions | Own the argument and the central claim |
| Aligns sections to the scoring rubric and mirrors funder language | Supply the evidence, preliminary results, and citations |
| Keeps terminology, numbers, and dates consistent across sections | Decide what to emphasize and what scope you can defend |
| Checks that every narrative activity has a budget line | Confirm the activity and the cost are both real |
| Flags gaps a reviewer would notice | Make the judgment call on how to fill them |
| Distinguishes outputs from outcomes, structures SMART objectives | Set the targets you can actually hit |

The AI is good at structure, consistency, and rubric alignment. You are the only source of evidence and the only one who can decide what is true about your project. That boundary never moves.

## How to Give a Good Drafting Prompt

A weak prompt produces generic filler. A strong prompt names three things: the section, the funder, and the criteria the section will be scored against.

Tell the AI:

- **Which section** you want drafted (statement of need, project description, evaluation plan, and so on).
- **Who the funder is** and what type they are (federal, foundation, corporate, congressional). Type changes tone, length, and evidence standards.
- **Which criteria** the section maps to, in the funder's own words. Paste the rubric language if you have it.
- **What evidence is available**: the data, prior results, citations, and community input you can stand behind.
- **Any constraints**: page limit, word count, required headers, formatting rules.

The more of your real record the AI can see, the less it has to guess. If it has to guess, it will produce something that reads fine and says nothing.

## Every Claim Needs Evidence

This is the hard rule of the drafting stage. The skill enforces it, and you enforce it harder.

- Support every claim with data, a citation, a prior result, or documented community input.
- Frame the need with data from the last three to five years from reputable sources, cited with source and year.
- Distinguish what you do (outputs) from what changes (outcomes). Do not let an output masquerade as an outcome.
- Use SMART objectives: specific, measurable, achievable, relevant, time-bound.

Never let the AI invent data, statistics, or citations. If the AI produces a number or a reference you did not give it, treat it as fabricated until you verify it against a real source. A made-up statistic is not a placeholder. It is a liability that a reviewer or a program officer can catch, and it can sink the proposal and your credibility with it.

When you do not have the evidence yet, leave a clearly marked placeholder (for example, `[CITE: enrollment data, last 3 years]`) and fill it before submission. A visible gap is honest. An invented fact is not.

## Example Prompts

### Statement of Need (federal)

```
Draft the Statement of Need for our NSF proposal.

Funder: NSF, federal, scored rubric.
This section supports Factor 1 (Importance of the Research).
Center the community we serve, not our organization.
Use this local data only: [paste your real figures with source and year].
National context: [paste citations you have verified].
Do not add any statistic I have not given you. Mark gaps as [CITE: ...].
Page limit for this section: 2 pages.
```

### Goals and Objectives

```
Draft Goals, Objectives, and Outcomes for the Department of Education grant.

Use SMART objectives. Separate outputs from outcomes explicitly.
Tie every objective to the need and to the funder's stated priorities.
Our aims: [paste the aims from Stage 3].
Targets I can defend: [paste real numbers and dates].
Each objective must be measurable with the methods in our evaluation plan.
```

### Budget Narrative

```
Draft the Budget Narrative for the foundation proposal.

Every narrative activity in our project description must have a matching
budget line, and every line must connect back to an activity.
Personnel, roles, and percent effort: [paste].
Use GSA rates for travel. Flag any line that has no narrative activity.
Keep the math consistent with the budget total: [paste total].
```

Run the section, read it as the person who has to defend it, then move to the next. When all required sections have a complete draft, you are ready for Stage 5: reading the proposal as a reviewer and checking compliance.
