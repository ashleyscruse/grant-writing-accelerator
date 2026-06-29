# Demo Cheat Card — Tapis / HPC (Monday, ~20 min)

**THE ONLY GOAL: make them comfortable getting on the system.** Not a CS lecture. They are impressed just seeing a supercomputer. You cannot fail at "look how easy this is."

---

## PRE-LOAD before you share your screen
- [ ] Tapis web open + logged in: **morehouse.tapis.io** (on Files → Vista)
- [ ] Terminal already SSH'd into Vista, MFA done, sitting at a prompt
- [ ] A Jupyter notebook **already running** in a backup tab
- [ ] `nyc_taxi_demo.ipynb` open
- [ ] Font size BIG in both terminal and browser

---

## THE 5 MOVES — say the line, do the thing

**1. "This is a supercomputer."**
Do: Tapis web → Files → Vista, show your files.
Say: *"This is a real supercomputer in Texas. We're on it right now."*

**2. "Two doors."**
Do: `ls` in the terminal, then the same folder in Tapis Files.
Say: *"Same machine, two ways in. Pick whichever feels comfortable."*

**3. "Let's get a notebook."**
Do: Jobs → submit the JSON → open `tapisjob.out` → copy the JUPYTER_URL.
Say: *"Let's grab a notebook running on a GPU."*
(If slow: *"while that schedules…"* → flip to the backup tab.)

**4. "Real data."**
Do: run the chart cell in `nyc_taxi_demo.ipynb`.
Say: *"20 million taxi trips, queried on the supercomputer."*

**5. "Your turn this week."**
Do: show the site + today's reservation name.
Say: *"You can do this yourself all week. Here's how."*

---

## THE JSON (paste into Jobs)
`{ "name": "jupyter", "appId": "jupyter-hpc-native", "appVersion": "vista", "maxMinutes": 120 }`

## LOGIN (if you blank)
- Web: **morehouse.tapis.io** — TACC username + password + MFA
- Terminal: `ssh USERNAME@vista.tacc.utexas.edu`

## IF IT BREAKS
Do not debug live. Say *"this is exactly why we keep a backup"* → flip to the pre-run tab. Everything is written on the site; read off it.

## THIS WEEK'S RESERVATION (gh queue)
Mon `NAIRR+Accel_Mon` · Tue `NAIRR+Accel_Tue` · Wed `NAIRR+Accel_Wed` · Thu `NAIRR+Accel_Thu` · Fri `NAIRR+Accel_Fri`

---

**Breathe. You've got this. 20 minutes. Read off this card.**
