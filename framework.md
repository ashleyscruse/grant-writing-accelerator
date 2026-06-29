# AI-Accelerated Grant Writing Framework

A repeatable, five-stage process for producing a competitive grant proposal using AI. AI accelerates each stage. The researcher makes every decision between stages.

> The AI does not win you the grant. You win the grant, faster. The AI drafts, analyzes, and checks; you decide.

## The Framework

### Stage 1: Foundation

Set up the context that makes everything else fast: a profile of who you are as a researcher.

The biggest difference between people who get large speedups from AI and those who do not is rarely the AI. It is whether their context is organized so the AI can use it. Five short documents (identity, research, teaching and mentoring, grant history, institution) become the knowledge base that grounds every evaluation and every draft in your real record instead of generic filler.

**What happens:**
- Fill in your profile in the `grant-writing-starter` workspace (your guide, Sage, walks you through it).
- Be specific: exact student counts, full citations, real dollar amounts.
- Be honest in the gaps section. The gaps are what keep you from wasting months on a proposal you cannot win.

**AI role:** Interview you, draft your answers into the profile files, read them back for correction.

**Researcher role:** Provide the real record. Decide what to emphasize. Own the honest gaps.

**You move to Stage 2 when:** `identity`, `research`, `teaching-mentoring`, `grant-history`, and at least one institution file are filled in.

**Deliverable:** A complete profile in `.claude/profile/`, reusable on every proposal for years.

---

### Stage 2: Opportunity

Find funding opportunities and evaluate fit honestly before you invest any writing time.

**What happens:**
- Bring in a solicitation (RFP, RFA, NOFO, or program page).
- The AI extracts the requirements and scores your fit across five dimensions: eligibility, research alignment, track record, strategic value, team readiness.
- You get an honest recommendation: strong fit, moderate fit, weak fit, or not eligible.

**AI role:** Extract requirements, assess fit against your profile, surface the gaps a reviewer would flag, write the evaluation.

**Researcher role:** Decide whether the fit is real and whether this advances your agenda. Make the go / no-go call.

**You move to Stage 3 when:** You have a confirmed-eligible opportunity, a real fit, and an actual decision to pursue it.

**Deliverable:** `grants/{name}/evaluation.md` and a go decision.

---

### Stage 3: Strategy

Define the project and the team for the grant you chose.

**What happens:**
- Shape the project concept into specific aims or objectives that map to the funder's priorities.
- Define who is on the proposal and what each person contributes (`team.md`).
- Identify expertise gaps and which collaborators fill them.

**AI role:** Structure the aims, pressure-test scope and feasibility, draft the team framing.

**Researcher role:** Choose the aims. Decide the scope you can defend. Confirm the team.

**You move to Stage 4 when:** You have a clear project concept, defined aims, and a team document.

**Deliverable:** A project concept with aims, and `grants/{name}/.claude/team.md`.

---

### Stage 4: Drafting

Write the proposal sections, mapped directly to the funder's review rubric.

**What happens:**
- Draft each required section: statement of need, project description, goals and objectives, evaluation plan, budget narrative, sustainability, broader impacts.
- Mirror the funder's language and section headers.
- Keep the narrative, budget, and evaluation internally consistent.

**AI role:** Draft sections from your profile, team, and decisions; align them to the scoring criteria; keep terminology and numbers consistent.

**Researcher role:** Own the argument. Supply the evidence and preliminary results. Make every claim defensible.

**You move to Stage 5 when:** You have a complete draft of the required sections.

**Deliverable:** Drafted proposal sections in `grants/{name}/`.

---

### Stage 5: Review and Submission

See the proposal the way a reviewer will, fix what they would flag, and confirm compliance.

**What happens:**
- Run a reviewer-perspective pass: does every evaluation criterion get addressed, can a scanning reviewer grasp the point from headers and first sentences, are claims supported?
- Check compliance: page limits, font, margins, required components, formatting rules from the solicitation.
- Build a submission checklist and timeline.

**AI role:** Critique against the rubric, flag red flags and gaps, check formatting and consistency.

**Researcher role:** Make the final calls. Decide what to cut, strengthen, or reframe. Submit.

**Done when:** The proposal is submission-ready and compliant.

**Deliverable:** A review-ready, compliant draft and a submission plan.

---

## The Hard Lines

Two points where you stop and verify before proceeding:

**Between Stage 2 and Stage 3:** Do not start writing until eligibility is confirmed, the fit is real, and you have made an actual decision to pursue. Writing before this is a solution looking for a problem, and grant writing time is the most expensive time you have.

**Between Stage 4 and Stage 5:** Do not submit until you have read the proposal as a reviewer and checked it against the solicitation's compliance rules. A strong proposal that violates a formatting requirement gets returned without review.

## How AI Fits

| Stage | Without AI | With AI |
|---|---|---|
| Foundation | Re-explaining yourself in every proposal | A profile written once, reused everywhere |
| Opportunity | Reading a 40-page NOFO to guess at fit | A structured fit analysis in minutes |
| Strategy | Staring at a blank specific-aims page | Aims structured against the funder's priorities |
| Drafting | Weeks per section from scratch | First drafts in hours, mapped to the rubric |
| Review | Hoping you caught the compliance issues | A reviewer-perspective and compliance pass |

The time savings are real. The judgment calls, the evidence, and the argument are still yours.
