# Tapis / TACC Demo — Run of Show

**When:** Monday · **Length:** ~20 minutes · **Format:** live, screen-share
**Lead:** Dr. Scruse
**Audience:** grant writers (mixed HPC experience — assume little to none)

## The one thing they should leave with

> NAIRR and TACC give you national-scale AI compute. There are two doors to the same supercomputer — the terminal (the traditional way) and Tapis (the easy, point-and-click way) — and you can name this infrastructure in your proposals as real, available capacity.

This is a grant-writing cohort, so the demo is not "learn HPC." It is "here is the compute you can request, cite, and use, and here is how little friction there is to touch it." Keep tying every screen back to *what a reviewer wants to see* and *what you can write in a Facilities / Resources section.*

## Demo format: split screen, two doors to the same machine

The whole demo runs **split screen** so they see you on the **same supercomputer two ways at once**:

- **Left half — Terminal:** you are SSH'd into Vista (a real login session at TACC). This is the "classic" way researchers use HPC.
- **Right half — Tapis** ([morehouse.tapis.io](https://morehouse.tapis.io)): the same Vista system, through a web page.

The recurring beat: do a thing on the **left in the terminal**, then show the **exact same thing on the right in Tapis**. Same files, same machine, two front doors. The message lands without you having to over-explain it: *you can use whichever you're comfortable with, and Tapis means "I'm not a command-line person" is no longer a reason you can't put a supercomputer in your grant.*

---

## Before you start (setup checklist)

- [ ] **Split screen arranged**: terminal on the left, browser on the right, both large and legible. Practice the window layout before you share.
- [ ] **Terminal already SSH'd into Vista** (`ssh your_username@vista.tacc.utexas.edu`), MFA done, sitting at a prompt in a folder that has a file or two. Do **not** log in live (MFA on screen is slow and risky).
- [ ] **Browser already logged into** [morehouse.tapis.io](https://morehouse.tapis.io), on the **Files** view for Vista, pointed at the *same folder* you're sitting in on the terminal (so the left/right match is obvious).
- [ ] One Jupyter pod/session **already running** in a third tab as a fallback, in case launching one live is slow.
- [ ] `python` + `tapipy` available in the terminal with `t` already authenticated, for the optional SDK beat.
- [ ] The [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/) guide open as backup.
- [ ] Font size bumped up in **both** terminal and browser; screen-share confirmed visible.

**Key facts to have on screen / memorized:**

| Detail | Value |
|---|---|
| Morehouse Tapis tenant | `https://morehouse.tapis.io` |
| Allocation | TRA25001 (PI: Kinnis Gosha) |
| Systems on the allocation | Vista, Frontera, Stampede3, Lonestar6 |
| Vista GPU queue | `gh` — 1× NVIDIA H200 (96 GB) per node, 72 cores, 48 hr max |
| Vista dev/test queue | `gh-dev` — same GPU, 2 hr max (use for testing) |
| Vista CPU queue | `gg` — 144 cores, no GPU, 48 hr max |

---

## Timed script

### 0:00–2:00 — Frame: NAIRR, TACC, Tapis (no screen yet, or title slide)

Say, in plain terms:

- **NAIRR** (National Artificial Intelligence Research Resource) is a national pilot that gives researchers access to AI compute, data, and tools — much of it at no cost to you. It exists so researchers outside the big well-funded labs can do serious AI work.
- **TACC** (Texas Advanced Computing Center) is one of the systems that provides that compute. **Vista** is its newer GPU machine — NVIDIA Grace-Hopper / H200 GPUs, built for AI.
- **Tapis** is the platform we use to *reach* TACC: submit jobs, move files, launch notebooks — through a web page or a few lines of Python, instead of SSH and hand-written batch scripts.

**Why a grant writer cares (say this explicitly):**
1. Reviewers ask "is this feasible — do they have the compute?" You can answer: *yes, through NAIRR/TACC via our institutional Tapis tenant (allocation TRA25001).*
2. You can write this infrastructure into your **Facilities, Equipment & Other Resources** section as real, available capacity — not aspirational.
3. NAIRR allocations are something you can *request as part of your proposal*. This demo shows the resource is real and usable.

> Line to use: "You don't have to become a supercomputing expert to put a supercomputer in your grant. Let me show you the front door."

### 2:00–4:00 — "Here are the two doors" (orient both halves)

- **Left (terminal):** "I'm logged into Vista right now — a real supercomputer at TACC in Austin. Run `hostname` and `pwd`." Let them see the machine name and that you're really *on* it.
- **Right (Tapis):** "Same machine, same account, through a web page." Point out the left nav: **Systems, Files, Apps, Jobs, Pods**.
- Say: "Same login for both — your **TACC account + MFA**, the one you're setting up this week. No new credentials. Watch how these two stay in sync."

### 4:00–7:00 — Same machine, same files (the core split-screen beat)

- **Left (terminal):** `ls` in your working folder. "Here are my files, the command-line way."
- **Right (Tapis):** open **Files** → Vista → the *same* folder. "Same files, point-and-click."
- **Prove they're live in sync:** on the **left**, `echo "hello from the terminal" > demo.txt`. On the **right**, hit refresh — `demo.txt` appears. (Or reverse it: drag-drop upload on the right, `ls` on the left to show it landed.)
- Land it: "Two doors, one supercomputer. Use whichever you like. 'I'm not a command-line person' is no longer a reason you can't use national compute."
- While here, name the TACC file layout (matters for the Data Management Plan): `$HOME` (10 GB, backed up, scripts) · `$WORK` (1 TB, software) · `$SCRATCH` (no limit, purged after 10 idle days, big datasets / active jobs).

### 7:00–10:00 — Systems: "this is the compute you can name in a proposal"

- **Right (Tapis):** open **Systems**. Show Vista (and that Frontera / Stampede3 / Lonestar6 are on the allocation).
- Surface Vista's specs out loud: **H200 GPUs, 96 GB GPU memory, 72 cores/node.**
- **Left (terminal):** optionally `sinfo` or `module avail` to show the real environment behind the web view.
- Tie to grants: "In your Facilities section you'd write: *Computational work will be carried out on TACC's Vista system (NVIDIA Grace-Hopper, H200 GPUs) accessed through the Morehouse Tapis tenant under NAIRR allocation TRA25001.* That sentence is now true and specific — reviewers love specific."

### 10:00–15:00 — The payoff: get a GPU, both ways

Show that interactive compute is one move on either side.

- **Left (terminal):** kick off an interactive GPU session: `idev -p gh-dev -N 1 -n 1 -t 00:30:00`. "This is the classic way to grab a GPU node — a couple of letters." (If `idev` is slow to schedule, narrate it and move to the right; don't wait on the queue live.)
- **Right (Tapis):** launch a **Jupyter** environment for the same machine:
  - **Option A — Pods (fastest to show):** **Pods** → templates → **Jupyter** (or open the one you pre-started). It gets its own TLS URL: `https://<pod-id>.pods.tacc.tapis.io`. Open it, run one cell, e.g. `import torch; torch.cuda.is_available()`.
  - **Option B — Jupyter on Vista (real GPU node):** use the MSCF guide, [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/).
- Land it: "Terminal or browser — under a minute to a GPU either way. *This* is why feasibility is not a worry: the barrier to national compute is now this low."

### 15:00–18:00 — Batch jobs, both ways (brief)

- **Left (terminal):** show a Slurm batch script and `sbatch train.slurm` (or a finished job's output). "The classic way: write a script, submit it to the queue."
- **Right (Tapis):** open **Jobs** and show a finished job's status history (QUEUED → RUNNING → FINISHED) and output files. "Same batch run, managed from the web — Tapis stages your files, runs it, saves the output."
- **Optional 20-sec SDK beat** (if time / audience is technical): in the terminal, show it's also just Python:
  ```python
  from tapipy.tapis import Tapis
  t = Tapis(base_url='https://morehouse.tapis.io',
            username='your_tacc_username', password='...')
  t.get_tokens()
  for s in t.systems.getSystems():
      print(s.id, s.host)
  ```
  "Terminal, web, or a few lines of Python — same supercomputer, pick your door."

### 18:00–20:00 — Bring it home to the grant

Land the three takeaways:
1. **Feasibility is covered.** You have documented, national-scale GPU compute via NAIRR/TACC, allocation TRA25001.
2. **Write it in.** Facilities & Resources: name Vista, the H200 GPUs, and the Tapis access path. Data Management Plan: `$SCRATCH`/`$WORK` storage and Tapis file transfer.
3. **Continued access.** NAIRR and TACC allocations continue past this week — you can request your own. (Point them to the workbook's NAIRR & TACC page and the credits links.)

> Closing line: "When a reviewer asks 'can they actually do this?' — the answer is on the screen. Now let's go write the proposal that uses it."

---

## If something breaks (live-demo insurance)

| Problem | Move |
|---|---|
| Login / MFA hangs | You're already logged in on both sides from the checklist. Never log in live. |
| `idev` won't schedule | Narrate it ("the queue assigns me a node"), don't wait; pivot to the Tapis/Jupyter side. |
| Pod is slow to launch | Switch to the pre-started Jupyter tab. |
| Notebook cell errors | Don't debug live; say "you'd `module load python3` here" and move on. |
| TapisUI is down | Run the whole demo from the terminal side; show the SDK beat to prove the same API is there. |
| Terminal SSH drops | Keep going on the Tapis side; reconnect off-screen during a talking beat. |
| Out of time | Cut the SDK beat and batch-jobs (15:00–18:00); protect the framing (0:00), the synced-files beat (4:00), and the close (18:00). |

## Source material
- Full Tapis reference: `research-accelerator/tapis-docs.md`
- Workbook pages (keep-after): `docs/06-Compute/01-nairr-tacc.md`, `docs/06-Compute/02-tapis-quickstart.md`
- MSCF Jupyter guide: https://morehouse-supercomputing.github.io/jupyter-on-tapis/
