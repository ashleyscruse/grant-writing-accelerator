# Tapis / HPC demo

Your companion to Monday's demo. This page stands on its own for the week: what the supercomputer is, why it matters for your grants, and how to touch it yourself, with no command line required.

## The three names

- **NAIRR** (National Artificial Intelligence Research Resource): a national pilot that gives researchers access to AI compute, data, and tools, much of it at no cost to you.
- **TACC** (Texas Advanced Computing Center) and **Vista**: TACC runs the machines. Vista is its newer GPU supercomputer (NVIDIA Grace-Hopper, H200 GPUs), built for AI.
- **Tapis**: the platform you use to reach Vista, through a web page or a few lines of Python, instead of SSH and hand-written batch scripts.

## Why a grant writer cares

1. **Feasibility.** Reviewers ask, "can they actually do this?" You can answer yes: national-scale GPU compute through NAIRR/TACC, via our institutional Tapis tenant, allocation `TRA25001`.
2. **Write it in.** In your Facilities, Equipment, and Other Resources section: *Computational work will be carried out on TACC's Vista system (NVIDIA Grace-Hopper, H200 GPUs), accessed through the Morehouse Tapis tenant under NAIRR allocation `TRA25001`.* True, specific, and reviewers like specific.
3. **Request your own.** NAIRR allocations are something you can request as part of a proposal. This week shows the resource is real and usable.

## Two doors to the same supercomputer

There are two ways onto Vista, and they stay in sync because they touch the same files and the same account.

| Door | What it is | Best for |
|------|-----------|----------|
| Terminal (SSH) | The classic way: `ssh your_username@vista.tacc.utexas.edu`, then the command line | People comfortable at a prompt |
| Tapis | A web page (`https://morehouse.tapis.io`) or a few lines of Python | Everyone, including "I'm not a command-line person" |

The point of the demo: you do not have to become a supercomputing expert to put a supercomputer in your grant.

## Log in

- **Web:** go to **[morehouse.tapis.io](https://morehouse.tapis.io)** and sign in with your TACC username, password, and MFA.
- **Terminal:** `ssh your_username@vista.tacc.utexas.edu`, then approve the MFA prompt.

Same login for both, the TACC account you set up this week. No new credentials.

## Browse your files

In the Tapis web app, the left menu shows **Systems, Files, Apps, Jobs, Pods**. Open **Files**, pick Vista, and browse to your folder, point-and-click, like any file browser. The same files show up if you run `ls` in the terminal.

Where things go on Vista (matters for your Data Management Plan):

- `$HOME` (10 GB, backed up) for scripts
- `$WORK` (1 TB) for software and files you keep
- `$SCRATCH` (no limit, purged after 10 idle days) for big datasets and active jobs

## Launch a Jupyter notebook (copy and paste)

1. Go to **[morehouse.tapis.io](https://morehouse.tapis.io)** → **Jobs → submit a job** and paste this in:

```json
{ "name": "jupyter", "appId": "jupyter-hpc-native", "appVersion": "vista" }
```

2. Wait until it reads **RUNNING**, open **`tapisjob.out`**, and copy the `JUPYTER_URL` line into your browser.

## See it paint (the demo notebook)

The notebook we run in the demo is **[github.com/ashleyscruse/supercomputer-paints](https://github.com/ashleyscruse/supercomputer-paints)**. You type a sentence and a Vista GPU paints it into a picture in about a second.

To run it yourself this week:

1. On a Vista **login** node, set it up once (this downloads the model into your `$WORK`, a few minutes):

```bash
cd $WORK
git clone https://github.com/ashleyscruse/supercomputer-paints.git
cd supercomputer-paints
bash setup.sh
```

2. Launch Jupyter on a `gh` node (the JSON above), open `paint.ipynb`, run the cells, and change the prompt to anything you like.

## Vista queues

| Queue | What you get |
|-------|-------------|
| `gh` | 1 NVIDIA H200 GPU (96 GB), 72 cores per node |
| `gh-dev` | Same GPU, for quick tests |
| `gg` | 144 cores, no GPU |

Our reservation this week is on `gh`. See [Explore the Compute](./explore-compute) for how to use it.

## Go deeper (optional)

For the full Jupyter-on-Vista walkthrough maintained by the MSCF, see [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/).
