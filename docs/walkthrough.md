# Do it yourself: get on the supercomputer

The same steps we did together. Take them slowly, one at a time.

## Part 1: set up the demo files (do this once)

This part downloads the painting model. It has to run on a **login node** (those have internet), so use a terminal, not Jupyter.

1. Open a terminal and log in:

```bash
ssh your_username@vista.tacc.utexas.edu
```

2. Get the files and run the one time setup:

```bash
cd $WORK
git clone https://github.com/ashleyscruse/supercomputer-paints.git
cd supercomputer-paints
bash setup.sh
```

`setup.sh` downloads the model into your `$WORK` (a few minutes). You only do this once.

## Part 2: launch your notebook

1. Go to **[morehouse.tapis.io](https://morehouse.tapis.io)** and sign in with your TACC username, password, and MFA.
2. In the left menu, open **Jobs**, choose to submit a job, and paste this in:

```json
{
  "name": "jupyter",
  "appId": "jupyter-hpc-native",
  "appVersion": "vista",
  "parameterSet": {
    "schedulerOptions": [
      { "name": "TACC Allocation", "arg": "-A TRA25001" }
    ]
  }
}
```

3. Submit it, then watch the status. After about two to three minutes it reads **RUNNING**.
4. Open the job's output file **`tapisjob.out`**, find the line that begins with `JUPYTER_URL`, and copy that whole link (including the part after `token=`) into your browser. That is JupyterLab, running on a GPU.

## Part 3: paint something

1. In JupyterLab's file browser, open `supercomputer-paints` and then `paint.ipynb`.
2. Run the first cell (it loads the model), then run the paint cell. An image appears in about a second.
3. Change the prompt to anything you like and run it again.

## If you get stuck

- **"You have multiple projects to charge to."** The JSON above already fixes this with the `-A TRA25001` line. Make sure you pasted the whole thing.
- **The job sits in QUEUED for a long time.** During our class hours the reserved nodes are ready, so this is quick. Outside those hours it can wait for a free node.
- **`import torch` fails, or no image.** Tell us. It is a one time setup issue we can fix with you.
