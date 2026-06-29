# NAIRR and TACC for Your Grants

Reviewers ask one quiet question of every proposal that involves computation: can these people actually do this? This page gives you the answer. You have access to national-scale AI compute through NAIRR and TACC, you can name it in your proposal as real available capacity, and you can request more of it as part of the work you are proposing.

You do not have to become a supercomputing expert to put a supercomputer in your grant. You just have to know what it is, what to write, and how to keep access after this week.

## What NAIRR is

NAIRR stands for National Artificial Intelligence Research Resource. It is a national pilot that gives researchers access to AI compute, datasets, and tools, much of it at no cost to you. It exists so that researchers outside the largest, best-funded labs can do serious AI work.

For a grant writer, the important parts are simple:

- It is a real, named, national resource you can cite.
- Access is often free or low cost through allocations.
- You can request a NAIRR allocation as part of a NAIRR-aligned proposal, so the compute is not aspirational, it is something you are formally asking for alongside the science.

## What TACC and Vista are

TACC is the Texas Advanced Computing Center, one of the systems that provides NAIRR compute. Vista is its newer GPU machine, built for AI work.

| Detail | Value |
|---|---|
| Center | TACC (Texas Advanced Computing Center), Austin |
| Machine | Vista |
| Architecture | NVIDIA Grace-Hopper |
| GPUs | NVIDIA H200, 96 GB GPU memory |
| Cores per node | 72 |
| Access platform | Tapis (`https://morehouse.tapis.io`) |
| Allocation | TRA25001 (PI: Kinnis Gosha) |
| Other systems on the allocation | Frontera, Stampede3, Lonestar6 |

Tapis is the platform you use to reach TACC. It is the easy front door: a web page or a few lines of Python instead of hand-written batch scripts. The [Tapis Quickstart](./02-tapis-quickstart) page covers how to use it. For now, the point is that the access path is documented and low friction, which is exactly what makes the feasibility claim in your proposal credible.

## Why a grant writer cares

Three concrete reasons, each tied to something a reviewer reads:

1. **Feasibility.** When a reviewer asks whether the project is doable, you can point to documented, national-scale GPU compute via NAIRR and TACC under allocation TRA25001. The answer is not "we hope to get time somewhere." It is specific and real.
2. **You can write it in.** Your Facilities, Equipment, and Other Resources section can name Vista, the H200 GPUs, and the Tapis access path as available capacity.
3. **You can request more.** NAIRR allocations are something you request as part of the proposal. Touching the resource this week proves it is real and usable, which makes the request honest.

## What to write in Facilities and Resources

Reviewers reward specificity. A vague "we have access to high performance computing" reads as filler. A named machine with named hardware and a named allocation reads as a team that has actually done this.

Use a sentence like this, adapted to your project:

> Computational work will be carried out on TACC's Vista system (NVIDIA Grace-Hopper architecture, NVIDIA H200 GPUs with 96 GB of GPU memory, 72 cores per node), accessed through the Morehouse Tapis tenant (`https://morehouse.tapis.io`) under NAIRR allocation TRA25001.

If your proposal requests its own NAIRR allocation, add a line stating that you will request a NAIRR allocation to support the proposed work, and that institutional access is already established through the Morehouse Tapis tenant. That combination, established access plus a specific request, answers feasibility and shows you know how the resource works.

## Data Management Plan framing

Many solicitations require a Data Management Plan. TACC's file system gives you concrete, citable storage to describe instead of hand-waving about "secure storage."

| Directory | Variable | Purpose | Quota | Backed up |
|---|---|---|---|---|
| `/home1/` | `$HOME` | Scripts, config files | 10 GB | Yes |
| `/work2/` | `$WORK` | Software installs, libraries | 1 TB | No |
| `/scratch/` | `$SCRATCH` | Active job data, large datasets | No limit | No (purged after 10 idle days) |

Useful framing for the plan:

- Active job data and large datasets live in `$SCRATCH`, which has no size limit and is purged after ten idle days, so it is for working data, not the system of record.
- Software, libraries, and intermediate products that need to persist live in `$WORK` (1 TB).
- Scripts and configuration live in the backed-up `$HOME` (10 GB).
- Data moves on and off the system through Tapis file transfer, which supports managed, logged transfers between systems. This is worth naming when a reviewer wants to see that data movement is controlled and reproducible.

A single sentence ties it together:

> Working datasets reside on TACC's `$SCRATCH` file system during active computation, persistent software and intermediate products on `$WORK`, with scripts and configuration version-controlled in the backed-up `$HOME`; all data transfers are managed through the Tapis platform.

## How to get continued access

NAIRR and TACC access continues past this week. You can request your own allocation and your own accounts.

| Resource | What it is | Link |
|---|---|---|
| NAIRR Ecosystem | The catalog of NAIRR resources and how to request an allocation | https://nairrpilot.org/ |
| TACC accounts | Create a TACC user account (needed for any TACC system, including Vista) | https://accounts.tacc.utexas.edu/ |
| OpenAI Researcher Access Program | Credits and API access for researchers | https://openai.com/form/researcher-access-program/ |
| Anthropic AI for Science | Compute and API credits for scientific research | https://www.anthropic.com/news/ai-for-science-program |

A practical order of operations:

1. Create a TACC account so you can log in to Vista and Tapis.
2. Request a NAIRR allocation through the NAIRR Ecosystem, naming the compute your proposed work needs.
3. If your project uses commercial AI models, apply to the OpenAI and Anthropic research programs for credits, and name those in your budget or resources section where relevant.

The bottom line: when a reviewer asks "can they actually do this?", the answer is documented, specific, and already in your hands. Now you write the proposal that uses it.
