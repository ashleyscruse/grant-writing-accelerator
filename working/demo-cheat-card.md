# Demo Cheat Card, Tapis / HPC (Monday, about 20 min)

**THE ONLY GOAL: make them comfortable getting on the system.** Not a CS lecture. They are impressed just seeing a supercomputer. You cannot fail at "look how easy this is."

---

## PRE-LOAD before you share your screen
- [ ] Tapis web open and logged in: **morehouse.tapis.io** (on Files, Vista)
- [ ] Terminal already SSH'd into Vista, MFA done, sitting at a prompt
- [ ] Jupyter already running on a `gh` node, **`paint.ipynb` open with the first cell already run** (model loaded, so it paints instantly)
- [ ] One image **already generated** in a backup tab, in case the live one stalls
- [ ] Font size BIG in both terminal and browser

---

## THE 5 MOVES, say the line, do the thing

**1. "This is a supercomputer."**
Do: Tapis web, Files, Vista, show your files.
Say: *"This is a real supercomputer in Texas. We're on it right now."*

**2. "Two doors."**
Do: `ls` in the terminal, then the same folder in Tapis Files.
Say: *"Same machine, two ways in. Pick whichever feels comfortable."*

**3. "Here's how you get a notebook."**
Do: Jobs, submit the JSON, open `tapisjob.out`, copy the JUPYTER_URL.
Say: *"That gives you a notebook running on a GPU."*
(Then flip to the tab you pre-loaded so you don't wait on the queue.)

**4. "Watch it paint."**
Do: in `paint.ipynb`, type a sentence, run the paint cell. An image appears in about a second.
Say: *"This machine made that from one sentence. That is the AI compute you can name and request in your grant."*

**5. "Your turn this week."**
Do: show the site and today's reservation name.
Say: *"You can do this yourself all week. Here's how."*

---

## THE JSON (paste into Jobs)
`{ "name": "jupyter", "appId": "jupyter-hpc-native", "appVersion": "vista", "execSystemLogicalQueue": "gh", "parameterSet": { "schedulerOptions": [ { "name": "TACC Allocation", "arg": "-A TRA25001" }, { "name": "TACC Reservation", "arg": "--reservation=NAIRR+Accel_Mon" } ] } }`
(Change `NAIRR+Accel_Mon` to today. `-A TRA25001` fixes the "multiple projects" error; `--reservation` puts you on the reserved nodes.)

## LOGIN (if you blank)
- Web: **morehouse.tapis.io**, TACC username and password and MFA
- Terminal: `ssh USERNAME@vista.tacc.utexas.edu`

## IF IT BREAKS
Do not debug live. Say *"this is exactly why we keep a backup"* and flip to the tab with the image already made. Everything is written on the site; read off it.

## THIS WEEK'S RESERVATION (gh queue)
Mon `NAIRR+Accel_Mon`, Tue `NAIRR+Accel_Tue`, Wed `NAIRR+Accel_Wed`, Thu `NAIRR+Accel_Thu`, Fri `NAIRR+Accel_Fri`

## CLONE THE REPO (show them, on a login node)
```
cd $WORK
git clone https://github.com/ashleyscruse/supercomputer-paints.git
cd supercomputer-paints
bash setup.sh
```
Already cloned? It says "already exists." Then either `cd $WORK/supercomputer-paints && git pull`, or clone into a new name: `git clone https://github.com/ashleyscruse/supercomputer-paints.git paints-demo`.

Then open `paint.ipynb` on a `gh` node and run the cells.

---

**Breathe. You've got this. 20 minutes. Read off this card.**
