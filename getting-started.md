# Getting Started: AI-Powered Grant Discovery

Set up your workspace so Claude can analyze grant opportunities against your professional profile and help you write stronger proposals.

This guide works with Claude Code, Claude Desktop, and Cowork.

## Overview

By the end of this setup, you'll be able to paste any grant solicitation into Claude and get back a structured evaluation: whether it's worth your time, where your profile aligns, what gaps a reviewer would flag, and what to do next.

## What You'll Set Up

1. **Profile documents** -- Google Docs you fill in during the workshop, then download as your AI-readable professional profile
2. **A project folder** on your machine with the right structure
3. **Skills** -- reusable instructions that tell Claude how to analyze grants and write proposals

## Step 1: Fill Out Your Profile Documents

We've created Google Doc templates for each part of your professional profile. During the workshop, you'll fill these in directly.

There are five profile documents, plus an optional collaborator template:

| Document | What It Covers |
|----------|---------------|
| **Identity** | Name, positions, education, skills |
| **Research** | Research focus, publications, active projects |
| **Teaching & Mentoring** | Programs led, courses, student numbers |
| **Institution** | Institution type, resources, affiliations (one per institution) |
| **Grant History** | Past grants, strengths, and honest gaps |
| **Collaborator** (optional) | One per collaborator: expertise, relationship, prior work |

Take your time with these. The more specific you are, the more useful your grant evaluations will be. Vague profiles produce vague analysis.

**Tips for filling them out:**
- Use exact numbers (e.g., "mentored 15 students" not "mentored many students")
- Include full publication citations, not just titles
- Be honest in the Gaps section -- this is what prevents you from wasting months on proposals you can't win
- If you don't have something (e.g., no prior PI grants), say so. Many programs favor early-career applicants.

## Step 2: Set Up Your Project Folder

Create a folder on your machine with this structure:

```
grants/
  .claude/
    profile/
      identity.md
      research.md
      teaching-mentoring.md
      grant-history.md
      institutions/           (one file per institution, e.g., morehouse.md)
      collaborators/          (optional, one file per collaborator)
    skills/
      grant-analyzer/
        SKILL.md
        references/
          evaluation-template.md
      grant-writing/
        SKILL.md
        references/
          proposal-sections.md
          grant-types.md
          reviewer-perspective.md
```

### Download your profile documents

1. In each Google Doc, go to **File > Download > Markdown (.md)**
2. Save each file into the `.claude/profile/` folder with the correct filename:
   - Identity doc -> `identity.md`
   - Research doc -> `research.md`
   - Teaching & Mentoring doc -> `teaching-mentoring.md`
   - Grant History doc -> `grant-history.md`
   - Institution doc(s) -> `institutions/{institution-name}.md` (e.g., `institutions/morehouse.md`)

### Install the skills

Copy the `grant-analyzer` and `grant-writing` skill folders into your `.claude/skills/` directory. We'll provide these during the workshop.

## Step 3: Start a Grant Directory

When you find a grant worth pursuing, create a directory for it inside your project folder. Each grant gets its own `.claude/` folder for grant-specific context like the team document.

```
grants/
  .claude/                    (your profile and skills -- shared across all grants)
    profile/
    skills/
  NSF-HBCU-EiR/              (one directory per grant)
    .claude/
      team.md                 (who's on THIS grant and their roles)
    evaluation.md             (from grant-analyzer)
    solicitation.pdf          (the original RFP)
  NIH-R21-Cancer/
    .claude/
      team.md
    evaluation.md
    solicitation.pdf
```

The `.claude/` at the top level holds your profile (who you are) and skills (how Claude works). The `.claude/` inside each grant directory holds context specific to that proposal, starting with the team document.

**When you decide to pursue a grant:**
1. Create a directory for it (e.g., `NSF-HBCU-EiR/`)
2. Save the solicitation there
3. Create a `.claude/` folder inside it with a `team.md` -- use the team template to define who's on this proposal and what role each person plays
4. Claude's grant-writing skill will use the team doc along with your profile to draft proposal sections

## Step 4: Test It

Open Claude (Code, Desktop, or Cowork) pointed at your project folder. Paste a grant solicitation and ask Claude to evaluate it.

Example prompt:
> Evaluate this grant opportunity: [paste URL or solicitation text]

Claude will:
1. Read your profile files
2. Extract the grant's requirements
3. Assess your fit across five dimensions (eligibility, research alignment, track record, strategic value, team readiness)
4. Give you an honest evaluation with a clear recommendation

You should get back:
- A decision (Strong fit / Moderate fit / Weak fit / Not eligible)
- Specific alignment between your profile and the grant
- Honest gaps a reviewer would flag
- Concrete next steps if pursuing

## Keeping Your Profile Current

Update your profile files as things change:
- New publication? Update `research.md`
- Got a grant? Update `grant-history.md`
- Addressed a gap? Update `grant-history.md`
- New collaborator? Add a file to `collaborators/`

You can edit the markdown files directly or update your Google Docs and re-download.

## Troubleshooting

**Claude isn't reading my profile:** Make sure your files are in `.claude/profile/` relative to your project root, and that Claude is pointed at your project folder.

**Evaluations are too generic:** Your profile files may be too vague. Add specific publication titles, exact student counts, and named programs.

**Claude is overselling my fit:** Check that your `grant-history.md` includes honest gaps. The system is designed to be brutally honest, but it can only flag gaps you've documented.
