# Tapis Quickstart

This page is the keep-after reference for the live Tapis demo. If you watched Dr. Scruse drive Vista two ways at once and want to do it yourself later, start here. Everything you need to log in, browse your files, launch a notebook, and run a job is below, with code you can copy.

The one idea to hold on to: there are two doors to the same supercomputer. Use whichever you are comfortable with.

## Two doors to the same machine

TACC's Vista is a real supercomputer in Austin. You can reach it two ways, and they stay in sync because they touch the same files and the same account.

| Door | What it is | Who it suits |
|---|---|---|
| Terminal (SSH) | The classic way: `ssh your_username@vista.tacc.utexas.edu`, then command line | People comfortable at a prompt |
| Tapis | A web page (`https://morehouse.tapis.io`) or a few lines of Python | Everyone, including "I'm not a command-line person" |

Same login for both. Same files. Two front doors. "I'm not a command-line person" is no longer a reason you cannot use national compute.

## Logging in

Both doors use the same credentials: your **TACC account plus multi-factor authentication (MFA)**. No new accounts.

- **Web:** go to `https://morehouse.tapis.io` and sign in with your TACC username, password, and MFA.
- **Terminal:** `ssh your_username@vista.tacc.utexas.edu`, then approve the MFA prompt.
- **Python:** authenticate with tapipy.

```python
from tapipy.tapis import Tapis

t = Tapis(base_url='https://morehouse.tapis.io',
          username='your_tacc_username',
          password='your_tacc_password')
t.get_tokens()
```

Tokens last about 4 hours. When one expires, call `t.get_tokens()` again. The SDK stores and sends the token for you.

## Browsing systems and files

A "system" in Tapis is a compute or storage resource. On the Morehouse tenant, Vista is the main one (Frontera, Stampede3, and Lonestar6 are also on the allocation).

**Web:** the left navigation shows **Systems, Files, Apps, Jobs, Pods**. Open **Files**, pick Vista, and browse to your folder. It is point and click, like any file browser.

**Python:** the same thing in a few lines.

```python
# List the systems available to you
for s in t.systems.getSystems():
    print(s.id, s.host)

# List files in a folder on Vista
t.files.listFiles(systemId='vista-morehouse',
                  path='/home1/10539/ashleyscruse')
```

Upload, download, and move work the same way:

```python
# Upload a file
t.files.insert(systemId='vista-morehouse',
               path='/scratch/my_project/',
               file=open('data.csv', 'rb'))

# Download a file
t.files.getContents(systemId='vista-morehouse',
                    path='/scratch/results/output.csv')

# Make a directory
t.files.mkdir(systemId='vista-morehouse', path='/scratch/my_project')
```

If you create a file in the terminal and refresh the web Files view, it appears. The two doors are looking at the same disk.

## The TACC file system

Knowing where files live matters for both your work and your Data Management Plan.

| Directory | Variable | Purpose | Quota | Backed up |
|---|---|---|---|---|
| `/home1/` | `$HOME` | Scripts, config files | 10 GB | Yes |
| `/work2/` | `$WORK` | Software installs, libraries | 1 TB | No |
| `/scratch/` | `$SCRATCH` | Active job data, large datasets | No limit | No (purged after 10 idle days) |

Rule of thumb: scripts in `$HOME`, software in `$WORK`, big working data in `$SCRATCH`. Do not leave anything you cannot regenerate in `$SCRATCH`, since it is purged after ten idle days.

## Launching Jupyter

For interactive work, a notebook is usually the fastest path to a GPU. Two routes:

**Pods (fastest to show).** A pod is a long-running container with its own URL. Launch a Jupyter pod from a template:

```python
t.pods.createPod(
    pod_id='my-notebook',
    pod_template='jupyter',
    description='Research notebook'
)

# Get the URL once it is running
pod = t.pods.getPod(pod_id='my-notebook')
print(f"Jupyter available at: {pod.url}")
```

Each pod gets its own address with automatic TLS, in the form `https://<pod-id>.pods.tacc.tapis.io`. Open it and run a cell:

```python
import torch
torch.cuda.is_available()
```

**Jupyter on a real Vista GPU node.** When you want a dedicated GPU node rather than a pod, follow the Morehouse Supercomputing Facility guide: [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/).

The classic terminal equivalent of grabbing a GPU interactively is one command:

```bash
idev -p gh-dev -N 1 -n 1 -t 00:30:00
```

Terminal or browser, you are on a GPU in under a minute either way.

## Submitting and monitoring a batch job

For longer runs you submit a batch job to the queue. The classic way is a Slurm script and `sbatch train.slurm`. Through Tapis, the same run is a few lines of Python, and Tapis stages your files, runs the job, and saves the output.

```python
job_def = {
    "name": "my-training-job",
    "appId": "my-ml-app",
    "appVersion": "0.1",
    "execSystemId": "vista-morehouse",
    "execSystemLogicalQueue": "gh",
    "nodeCount": 1,
    "coresPerNode": 72,
    "maxMinutes": 60,
    "memoryMB": 256000,
    "fileInputs": [{
        "name": "input-data",
        "sourceUrl": "tapis://vista-morehouse/scratch/data/dataset.csv",
        "targetPath": "dataset.csv"
    }]
}

job = t.jobs.submitJob(**job_def)
print(job.uuid)
```

Monitor it and pull the results when it finishes:

```python
import time

status = t.jobs.getJob(jobUuid=job.uuid).status
while status not in ['FINISHED', 'FAILED', 'CANCELLED']:
    time.sleep(30)
    status = t.jobs.getJob(jobUuid=job.uuid).status
    print(f"Status: {status}")

t.jobs.getJobOutputDownload(jobUuid=job.uuid, outputPath='/results/')
```

A job moves through this lifecycle: PENDING, PROCESSING_INPUTS, STAGING_INPUTS, STAGING_JOB, SUBMITTING_JOB, QUEUED, RUNNING, ARCHIVING, FINISHED. In the web **Jobs** view you can watch the same history (QUEUED to RUNNING to FINISHED) and browse the output files.

## Vista queues

Pick the queue that matches the work. Use `gh-dev` to test (short, fast to schedule), then move to `gh` for real GPU runs.

| Queue | Nodes | Cores/node | GPU | Max walltime | Use for |
|---|---|---|---|---|---|
| `gh` | 1-64 | 72 | 1x H200 (96 GB) | 48 hrs | Real GPU jobs |
| `gh-dev` | 1-8 | 72 | 1x H200 (96 GB) | 2 hrs | Testing, quick checks |
| `gg` | 1-32 | 144 | None (CPU only) | 48 hrs | CPU-only work |

## Common errors

| Symptom | Likely cause | Fix |
|---|---|---|
| `401 Unauthorized` on an API call | Token expired (4 hr TTL) | Call `t.get_tokens()` again |
| Login or MFA hangs | MFA prompt not approved | Approve the push, retry sign-in |
| Job sits in QUEUED a long time | Normal scheduling wait | Wait, or test in `gh-dev` (short queue) |
| Notebook cell: `ModuleNotFoundError` | Environment not loaded | `module load python3`, install into your env |
| `torch.cuda.is_available()` returns False | Not on a GPU node or wrong queue | Use `gh` or `gh-dev`, not `gg` |
| File not found in Files view | Wrong system or path | Confirm `systemId` and that the path is under the system's root |

## Where to go next

- Full Tapis reference (every service, more code): your facilitator's `tapis-docs.md`.
- Jupyter on a real GPU node: [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/).
- Why this matters for your proposal: [NAIRR and TACC for Your Grants](./01-nairr-tacc).
