# Grant Writing Accelerator

**NAIRR Summer Accelerator · June 29 – July 3, 2026**

Welcome. This is your home base for the week: the agenda, the curriculum, and any resources we share as we go. Check back here each day.

## Agenda for the week

| Day | Focus |
|-----|-------|
| **Mon,&nbsp;June&nbsp;29** | Introduction Day: grant, HPC, and MSCF background; why HPC for your research; identifying funding opportunities. Includes the **HPC + Tapis demo**. |
| **Tue,&nbsp;June&nbsp;30** | Grant Training: walking through the proposal and its major sections. |
| **Wed,&nbsp;July&nbsp;1** | Budgets: building and justifying a grant budget. |
| **Thu,&nbsp;July&nbsp;2** | Demo Day: the **AI demo**, using AI to accelerate your proposal workflow. |
| **Fri,&nbsp;July&nbsp;3** | Work Day: continued demo, feedback, independent work, and collaboration. |

Lunch each day: 12:30 to 1:30. Office hours follow the afternoon sessions. Evening and social plans are shared by email and in the cohort WhatsApp group.

## Before you arrive

<ul style="list-style:none; padding-left:0;">
<li><input type="checkbox"> Create a <a href="https://portal.tacc.utexas.edu/account-request">TACC account</a> and set up multi-factor authentication (for the NAIRR / TACC compute work).</li>
<li><input type="checkbox"> Bring one real funding opportunity you are considering (a URL or PDF of an RFP / NOFO).</li>
<li><input type="checkbox"> Bring your CV and a list of your publications and past grants, to make filling in your profile fast.</li>
<li><input type="checkbox"> Download <strong><a href="https://claude.com/product/claude-code">Claude Code</a></strong>, the app we use for the AI demo.</li>
<li><input type="checkbox"> Recommended for the AI demo: a <a href="https://github.com">GitHub account</a> and a Claude Pro account.</li>
</ul>

## Your workspace

Your grant work lives in the **Grant Writing Starter**, a ready-to-go workspace where AI tools and your professional context are already wired in.

- Repo: [github.com/ashleyscruse/grant-writing-starter](https://github.com/ashleyscruse/grant-writing-starter)
- It includes skills that do the heavy lifting: **grant-analyzer** (honest fit assessment), **grant-writing** (sections mapped to the review rubric), and more.
- Make your own copy ("Fork" or "Use this template"), open it in VS Code, Cursor, Claude Code, or Claude on the web, and say hi. Your guide, **Sage**, walks you through filling in your profile. Setup and updates: see the repo's **SETUP.md**.

## Explore the compute on your own

We have a Vista GPU reservation for each day of the week. After a demo, you can keep exploring on your own using that day's reservation. Each reservation is 15 GPU nodes on the `gh` partition under allocation `TRA25001`, available 8:45 AM to 5:15 PM Central.

| Day | Date | Reservation name |
|-----|------|------------------|
| Mon | June 29 | `NAIRR+Accel_Mon` |
| Tue | June 30 | `NAIRR+Accel_Tue` |
| Wed | July 1 | `NAIRR+Accel_Wed` |
| Thu | July 2 | `NAIRR+Accel_Thu` |
| Fri | July 3 | `NAIRR+Accel_Fri` |

To use a reservation, add `--reservation=<name>` (and the account and partition) to your job:

```bash
# Interactive GPU node (today is Monday)
idev -p gh -A TRA25001 --reservation=NAIRR+Accel_Mon -N 1 -n 1 -t 02:00:00
```

```bash
# In a batch script
#SBATCH -p gh
#SBATCH -A TRA25001
#SBATCH --reservation=NAIRR+Accel_Mon
```

A reservation only works during its day and time window. Use the name that matches the day you are working.

## Resources

Materials we share during the week will be added here as we go.

- [Grant Writing Starter repo](https://github.com/ashleyscruse/grant-writing-starter)
- [Morehouse Tapis Tenant](https://morehouse.tapis.io)
- [Launching Jupyter on Vista (MSCF)](https://morehouse-supercomputing.github.io/jupyter-on-tapis/)

### Credits and access for researchers

- [NAIRR Ecosystem and Credits for Researchers](https://docs.google.com/document/d/1DC0DAai4V1wJJCYC6B6GzIHQ-UT93-7vM8v5TbYp1OI/edit?usp=sharing)
- [OpenAI Researcher Access Program](https://openai.com/form/researcher-access-program/)
- [Anthropic AI for Science Program](https://www.anthropic.com/news/ai-for-science-program)

## Author

**Ashley Scruse, Ph.D.**
Deputy Director, Morehouse Supercomputing Facility
[ashley.scruse@morehouse.edu](mailto:ashley.scruse@morehouse.edu)
