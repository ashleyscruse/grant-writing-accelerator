# AI to Accelerate Grant Writing — Demo Run of Show

**When:** Thursday · **Format:** live, screen-share · **Lead:** Dr. Scruse
**Audience:** grant writers (mixed AI experience)

## The one thing they should leave with

> It is not the AI. It is the context. Once your profile is set up, the same five-step workflow (set up, evaluate, strategize, draft, review) gives you grounded, honest help on every proposal you ever write. You are leaving with a system, not a one-time trick.

This demo is not "look what AI can do." It is "here is a workflow you will still be using in six months, and here are the files that make it work." You hand them the `grant-writing-starter` and teach the loop.

## What you hand them (do this before or at the start)

- The starter repo: **github.com/ashleyscruse/grant-writing-starter** (fork or "Use this template").
- The workbook (keep-after): the Grant Writing Accelerator GitHub Pages site.
- Tell them: "Everything I do today is written down in the workbook and lives in this repo. You are not taking notes to remember steps. You are learning a workflow."

## Setup checklist (before you screen-share)

- [ ] A tool open and pointed at a **copy of the starter** (Claude Code in the repo is cleanest, since "hi" triggers Sage; Cursor or Claude desktop also fine).
- [ ] A **partially filled profile** ready as your demo identity. Two options:
  - **Use a fictional PI (recommended):** the worked example uses "Maria Chen." Have her profile filled in so analysis and drafting look real, OR
  - **Use yourself:** your own profile, which is the most authentic but shows your real record on screen.
- [ ] One **real-ish solicitation** to evaluate (e.g. the NSF HBCU-EiR program page, or any RFP/NOFO PDF). Have the text or URL ready to paste.
- [ ] The worked example folder visible: `grants/EXAMPLE-NSF-HBCU-EiR/` (solicitation, evaluation, team).
- [ ] Decide in advance which ONE section you will draft live (Statement of Need or Specific Aims is best for impact).
- [ ] Font size up; a second clean chat ready in case one gets messy.

## The frame (say this first, 2 min)

- "Most people use AI for grants by pasting into a chat box and getting generic help, because the AI does not know who they are. We are going to fix the root cause."
- "The biggest difference between a small AI boost and a huge one is whether your context is organized. So step one is always: set up your context. Then the same loop works on every grant."
- Show the five steps on screen (the framework): **Foundation, Opportunity, Strategy, Drafting, Review.** "I will run all five live."

---

## The live workflow (the spine of the demo)

### Step 1 · Foundation: meet Sage, set up context (4-5 min)

- Open the starter in your tool. In Claude Code, just say **hi**. (In other tools, paste: "Read CLAUDE.md and .claude/skills/setup-guide/SKILL.md, then be Sage and guide me.")
- Sage introduces herself and offers to fill in your profile. Show **one** profile file being filled (e.g. `identity.md` or part of `research.md`) so they see the interview style: Sage asks, you answer, it writes the file, reads it back.
- Make the point out loud: "I only do this once. This profile now grounds every grant I ever evaluate or draft. That is the whole trick."
- Don't fill the whole profile live. Show the pattern, then say "imagine this is done" and switch to the pre-filled profile.

> Teaching beat: open `.claude/profile/research.md` filled in. "This file is the difference between generic and grounded. Watch what it does next."

### Step 2 · Opportunity: evaluate fit honestly (4-5 min)

- Paste your solicitation and type:
  > "Evaluate this grant opportunity against my profile: [paste URL or text]"
- The grant-analyzer skill reads the profile + solicitation and produces a fit evaluation: eligibility, research alignment, track record, strategic value, team readiness, the gaps a reviewer would flag, and a recommendation (Strong / Moderate / Weak / Not eligible). It saves to `grants/{name}/evaluation.md`.
- Land the honesty point: scroll to the **gaps** section. "Notice it is not flattering me. It tells me what a reviewer would mark down. That honesty is what saves you three months on a grant you cannot win."
- Reference the worked example `grants/EXAMPLE-NSF-HBCU-EiR/evaluation.md` so they see a complete one.
- State the hard line: "I do not write a single section until fit is real and I have decided to go. Here, it is a go."

### Step 3 · Strategy: the team for THIS grant (2-3 min)

- Show `grants/EXAMPLE-NSF-HBCU-EiR/.claude/team.md` (PI, Co-PI, senior personnel).
- "Each grant gets its own team file. The drafting step reads my profile plus this team, so personnel and roles are right without me re-explaining them."
- Optionally: "Draft three specific aims for this project that map to the solicitation's review criteria, using my research profile." Show the aims it returns; note YOU choose the aims.

### Step 4 · Drafting: write a section, mapped to the rubric (5-6 min)

- This is the payoff. Type something like:
  > "Using my profile and this grant's team, draft the Statement of Need for this proposal. Map it to the solicitation's review criteria and mirror the funder's language."
- Let it draft. While it writes, narrate what the grant-writing skill is enforcing: evidence-based claims, SMART objectives, outputs vs outcomes, asset-based community framing, every claim supported, no fabricated data, no em dashes.
- Read a few lines aloud. Point out it used **their real record** from the profile, not invented filler.
- Make the division of labor explicit: "It drafted in minutes what takes me a week. But I own the argument and the evidence. I review every claim. The AI does not win the grant. I do, faster."

### Step 5 · Review: read it as a reviewer (3-4 min)

- Type:
  > "Now act as a skeptical reviewer. Score this draft against the solicitation's review criteria and tell me what you would mark down."
- Show it flipping from author to critic: flagging unsupported claims, missing criteria, scanability problems.
- "This is the reviewer-perspective pass. And before submission there is a compliance pass: page limits, font, required components. A great proposal that breaks a formatting rule gets returned unread."

---

## Close (2 min): the system they keep

- Recap the loop on screen: **set up context once → evaluate → strategize → draft → review.**
- "Three things you are leaving with: this repo with your profile in it, two skills that do the analysis and drafting, and a workflow you will still use next year."
- Point them to: the workbook (every step is written up), the starter's `SETUP.md`, and `git pull` to get anything I add this week.
- Last line: "Go set up your profile today. That one hour is what makes everything else fast."

---

## Timing summary (~25 min + Q&A)

| Step | Minutes |
|---|---|
| Frame | 2 |
| 1 · Foundation (Sage) | 4-5 |
| 2 · Opportunity (analyzer) | 4-5 |
| 3 · Strategy (team) | 2-3 |
| 4 · Drafting (the payoff) | 5-6 |
| 5 · Review (skeptical reviewer) | 3-4 |
| Close | 2 |

## If something breaks (live-demo insurance)

| Problem | Move |
|---|---|
| Sage doesn't trigger in a non-Claude-Code tool | Paste the universal line from SETUP.md. |
| Profile filling runs long | Show one field, then switch to the pre-filled profile. |
| Analyzer / draft is slow | Keep narrating the framework; or show the pre-generated EXAMPLE files. |
| A draft looks thin | That is the teaching moment: "thin profile gives thin output, this is why context matters." |
| Out of time | Protect Steps 2 and 4 (evaluate + draft). Compress 1, 3, 5. |

## What this teaches them to keep doing

The durable workflow, written so they can repeat it without you:
1. Fill in `.claude/profile/` once (Sage helps).
2. For each opportunity: paste it, get an honest evaluation, decide go / no-go.
3. If go: make a `grants/{name}/` folder, add a `team.md`.
4. Draft each section against the rubric with the grant-writing skill.
5. Review as a skeptical reviewer, then run a compliance pass before submitting.

All of it is in the workbook and the starter, so the cohort keeps the system after the week ends.

## Source material
- Starter repo: `grant-writing-starter/` (README, SETUP, CLAUDE.md, skills, profile, grants/EXAMPLE)
- Framework: `grant-writing-accelerator/framework.md`
- Workbook pages: `grant-writing-accelerator/docs/` (Stages 1-5, AI Tools, Compute)
