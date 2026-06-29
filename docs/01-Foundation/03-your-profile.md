# Your Profile

Your profile is the knowledge base the AI uses for everything else. It is five short documents about who you are as a researcher, and once they exist, every grant evaluation and every proposal draft reads from them instead of inventing filler. You fill them in once and reuse them on every proposal for years.

You do not fill them in alone. When you say hi, Sage interviews you, drafts your answers into the actual files, and reads them back so you can correct them. Sage works one file at a time and does not rush. You can stop partway and pick up later by saying hi again.

The files live in `.claude/profile/`. Here is what each one captures and why it matters for grants.

## The five files

| File | What it captures | Why it matters |
|---|---|---|
| `identity.md` | Name, positions, education, research areas, technical skills | The basic frame: who you are and what you work on |
| `research.md` | Core contribution, active agenda, publications | The most important file for fit analysis |
| `teaching-mentoring.md` | Programs, courses, mentoring counts, outreach | Drives broader-impacts narratives, especially for NSF |
| `grant-history.md` | Grants received, active work, strengths, honest gaps | The gaps keep you from wasting months on proposals you cannot win |
| `institutions/{name}.md` | Your institution and its designations | Sets eligibility (HBCU, MSI, PUI, R1, and more) |

You fill them in this order. Start with identity, the quickest and most concrete, and build from there.

### 1. identity.md

Your name, credentials, current appointments (with department, institution, and start year), education, three to five research areas, and the technical skills you actually use. This is fast and concrete. It gives the AI the frame for everything else.

### 2. research.md

This is the file that matters most for fit analysis, so spend the most time here. It captures your core research contribution in a few sentences (the problem, your approach, what makes it different), your active research agenda as specific aims, and your publications as full citations. The more specific this file is, the better the AI can match you to the right opportunities and the better its drafts will sound like your work. A vague research file produces vague analysis.

### 3. teaching-mentoring.md

Programs you have led, courses you teach, how many students you have mentored, and your outreach. This file is what powers broader-impacts narratives, which carry real weight in NSF proposals and many others. When the AI drafts a broadening-participation section, it pulls from here. Exact counts make it credible: "mentored 14 undergraduate researchers, 9 of them women in computing" is a narrative; "I mentor students" is filler.

### 4. grant-history.md

This is where honesty matters most. It lists the grants and fellowships you have received (with role, funder, title, amount, and years), any proposals you are currently developing, your grant-writing strengths, and your known gaps.

The gaps section is the most important part of the whole profile. An analyzer that does not know your weaknesses gives you false encouragement and sends you down a path you cannot win. Be honest here: no preliminary data for an aim yet, no clinical collaborator for patient data, limited experience with large budgets, only one first-author paper, no prior PI experience. Sage will press gently on this section, kindly, because naming a gap early is what protects your most expensive resource, your writing time.

If you have not received grants yet, that is not a weakness for many programs. Write "Early-career researcher, no prior PI grants." NSF CAREER, NIH K awards, and many foundation grants expect exactly that.

### 5. institutions/

Copy `_TEMPLATE.md` to a file named for your institution (for example, `morehouse.md`) and fill it in. One file per institution. This sets your eligibility, which determines which funding pools you can even access: HBCU, MSI, PUI, R1, private non-profit, and so on. A grant you are not eligible for is a non-starter, and the AI needs this to flag that before you write a word.

The `collaborators/` files are optional and come later, when a specific grant needs expertise you do not have. Sage will mention them but not fill them now.

## Two rules that make the difference

**Be specific.** Exact student counts. Full publication citations. Real dollar amounts. Specific aims, not vague directions. The profile is only as good as the detail in it, and the analysis and drafts you get later are only as good as the profile. This is the one place where more concrete is always better.

**Be honest in the gaps.** The point of the gaps section is not to look good. It is to get the truth from the AI when you ask whether an opportunity is worth pursuing. A profile that hides its weaknesses produces analysis that flatters you into wasting months. Name the gaps, and the AI can tell you the honest no that saves your time.

## You are done with Foundation when

`identity.md`, `research.md`, `teaching-mentoring.md`, `grant-history.md`, and at least one institution file are filled in. When they are, Sage hands off: from there you can paste any solicitation and ask for an honest fit analysis (that is the `grant-analyzer` skill, covered next stage), and when you decide to pursue one, start drafting (the `grant-writing` skill).

Your deliverable is a complete profile in `.claude/profile/`, reusable on every proposal for years. You are set up to move fast now.
