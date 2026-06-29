# Explore the compute on your own

We have a Vista GPU reservation for each day of the week. After a demo, you can keep exploring on your own using that day's reservation. Each reservation is 15 GPU nodes on the `gh` partition under allocation `TRA25001`, available 8:45 AM to 5:15 PM Central.

| Day | Date | Reservation name |
|-----|------|------------------|
| Mon | June 29 | `NAIRR+Accel_Mon` |
| Tue | June 30 | `NAIRR+Accel_Tue` |
| Wed | July 1 | `NAIRR+Accel_Wed` |
| Thu | July 2 | `NAIRR+Accel_Thu` |
| Fri | July 3 | `NAIRR+Accel_Fri` |

Use the reservation name that matches the day you are working. A reservation only works during its own day and time window.

## Launch a Jupyter notebook through Tapis (easiest)

This is the simplest way in, no command line needed. You launch a JupyterLab session on a real Vista GPU node from the Tapis web app.

1. Go to **[morehouse.tapis.io](https://morehouse.tapis.io)** and sign in with your TACC username, password, and MFA.
2. In the left menu, open **Jobs**, then submit a new job using the JSON form. Paste the full job request below.
3. Submit, then watch the status move through `STAGING_INPUTS → SUBMITTING_JOB → QUEUED → RUNNING`.
4. Once it reads **RUNNING**, wait one to two minutes, then open the job's output file **`tapisjob.out`**. Near the top is a line like `TACC: JUPYTER_URL is https://vista.tacc.utexas.edu:60707/?token=...`. Copy that full URL (including `?token=...`) into your browser. That is your notebook, running on a Vista GPU node.

**Full job request, with this week's reservation:**

```json
{
  "name": "jupyter",
  "appId": "jupyter-hpc-native",
  "appVersion": "vista",
  "maxMinutes": 120,
  "parameterSet": {
    "schedulerOptions": [
      { "name": "partition", "arg": "--partition=gh" },
      { "name": "reservation", "arg": "--reservation=NAIRR+Accel_Mon" }
    ]
  }
}
```

- Change `NAIRR+Accel_Mon` to the day you are working (see the table above).
- The app already knows the system and the allocation (`TRA25001`), so you do not set those.
- `maxMinutes` caps the session. Save your work to `$WORK` before it ends.

**If you are not using the reservation** (for example, outside the reserved window), submit the short version instead and it runs on the app's default queue:

```json
{ "name": "jupyter", "appId": "jupyter-hpc-native", "appVersion": "vista", "maxMinutes": 120 }
```

> Tip: if the job sticks in `STAGING_INPUTS`, your TMS keys for the `cloud.data` system are not verified yet. In the **Files** browser, confirm you can open `cloud.data` once; then resubmit. If you see `required key [name] not found`, your JSON is missing the `name` field.

## Prefer the terminal?

If you are comfortable at a command line, SSH into Vista (`ssh your_username@vista.tacc.utexas.edu`) and attach the reservation directly.

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

For the full Jupyter-on-Vista walkthrough, see the MSCF guide: [Launching Jupyter on Vista](https://morehouse-supercomputing.github.io/jupyter-on-tapis/).
