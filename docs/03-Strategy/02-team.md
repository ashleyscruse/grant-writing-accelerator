# Building Your Team

You have a project concept and a set of aims. The second half of Stage 3 answers a question reviewers always ask: can these people actually do this work? A strong idea with the wrong team reads as a risk. The right team turns the same idea into a credible plan.

This page covers who goes on the proposal, where to record it so the AI can use it, and when to add collaborator profiles to cover expertise you lack.

> Team is not a formality. It is part of feasibility. Reviewers score whether the people, skills, and resources on the proposal can deliver the aims you wrote. Get the team right and the rest of the proposal becomes easier to defend.

## Why the team doc exists

The grant-writing skill reads two things when it drafts personnel and capacity language: your profile (`.claude/profile/`) and the per-grant team doc. The profile is reusable across every proposal. The team doc is specific to this grant, because the right team changes with the opportunity.

Each grant gets its own team document at:

```
grants/{name}/.claude/team.md
```

You create it once you decide to pursue the grant. Start from the template at `templates/team.md` and look at the worked example at `grants/EXAMPLE-NSF-HBCU-EiR/.claude/team.md` for a filled-in version.

## What goes in team.md

The document is short. For each person, you record who they are, their role, and what they contribute. Specificity matters: "leads the wet lab validation and provides access to patient-derived organoids" tells a reviewer something; "helps with the project" does not.

| Section | Who goes here | What to capture |
|---|---|---|
| PI | The lead investigator | Name, role, what they lead and oversee |
| Co-PI(s) | Co-leads, often at partner institutions | Name, institution, role, contribution |
| Senior Personnel | Key contributors who are not PIs | Name, institution, role, contribution (e.g., manages HPC or NAIRR allocations) |
| Consultants | Outside experts on partial effort | Name, institution, effort percentage, contribution |
| Additional Personnel | Postdocs, students, staff the grant supports | Role, field, effort or hours |

A useful contribution line names a deliverable or a resource, not a vague intention. Compare:

| Weak | Strong |
|---|---|
| Helps with computation | Manages HPC resources and ACCESS/NAIRR allocations for large-scale analyses |
| Supports students | Co-mentors one graduate student and two undergraduate research assistants |
| Advises on the science | Provides clinical oncology expertise; advises on clinical relevance of findings (5 percent effort) |

The example team doc shows this in practice: a PI leading method development, a Co-PI at a partner institution leading validation and providing data access, senior personnel managing computing allocations, and named additional personnel with effort levels.

## When to add a collaborator profile

Sometimes a grant needs expertise, methods, or resources you do not have. If your fit analysis in Stage 2 surfaced a gap (wet lab validation, a specific instrument, a clinical population, a domain you do not work in), the answer is usually a collaborator, not a stretch.

For each key collaborator, create a profile at:

```
.claude/profile/collaborators/{lastname}.md
```

Start from `templates/collaborator.md`. The profile captures what the team doc cannot hold in one line:

| Field | Why it matters |
|---|---|
| Name and credentials | Establishes authority |
| Position | Shows institutional standing |
| Expertise | The specific thing they bring that you do not have |
| Key publications | Evidence the expertise is real |
| Relationship | How you know them, whether you have worked together |
| Prior collaboration | Joint grants or papers that prove the partnership is real |

The relationship and prior-collaboration fields matter more than they look. A collaborator you have published with reads as a real, low-risk partnership. A name you added last week reads as a partnership of convenience, and reviewers can tell.

Collaborator profiles live in the profile folder, not the per-grant folder, because a good collaborator often appears on more than one proposal. Write the profile once, reuse it across grants.

## How AI uses the team

Once `team.md` and any collaborator profiles are in place, the grant-writing skill can:

| AI does | You do |
|---|---|
| Drafts the personnel and team-qualifications framing from the team doc and profiles | Confirm every role and contribution is accurate |
| Connects each person's contribution to a specific aim | Verify the person actually does that work |
| Identifies expertise gaps between your aims and your team | Decide whether to add a collaborator or rescope |
| Suggests which collaborator fills a named gap (from `collaborators/`) | Confirm the collaboration is real and committed |
| Keeps team language consistent with the budget and effort levels | Own the effort numbers and commitments |

The AI cannot recruit a collaborator or commit their effort. It can tell you that Aim 2 needs wet lab capacity your profile does not show, and point to a collaborator profile that covers it. The decision and the relationship are yours.

## Example prompts

```
Read my team.md and profile. Draft the team-qualifications paragraph for this
proposal, connecting each person's contribution to a specific aim.
```

```
Compare my aims against my team.md and profile. What expertise gaps would a
reviewer flag, and which aims are most exposed?
```

```
This grant needs experimental validation I cannot do in-house. Based on my
collaborator profiles, who fills that gap, and is the collaboration strong
enough to convince a reviewer?
```

```
Check that the roles and effort levels in team.md are consistent with the
project scope. Where is the team too thin for the aims as written?
```

## What "done" looks like

You finish Stage 3 when you have:

- A confirmed PI and any Co-PIs, senior personnel, and consultants
- A completed `grants/{name}/.claude/team.md` with specific contributions
- A collaborator profile in `.claude/profile/collaborators/` for every gap-filling partner
- Confidence that the team can deliver the aims you wrote

With the concept, the aims, and the team set, you have everything you need to start drafting. That is Stage 4.
