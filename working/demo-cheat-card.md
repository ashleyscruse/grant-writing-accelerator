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

## THE MODEL + HUGGING FACE (say this)
- **Hugging Face** is a public library where researchers share AI models for free. Think GitHub, but for AI models. Anyone can download and use them.
- The model we use is **Stable Diffusion XL Turbo** (`sdxl-turbo`), an open image model from Stability AI. Free, no account needed.
- **"Turbo"** means it is tuned to make an image in one or two steps (about a second) instead of the usual thirty to fifty steps. That is why it is so fast.
- We **downloaded it once** into `$WORK` so the GPU node can load it without internet.
- The grant point: **open models plus free national compute means you can do real AI work without buying anything.** That is what you put in a proposal.

## PROMPT IDEAS (if the room is shy)
Change the `prompt = "..."` line and Shift+Enter. Add a style word at the end.
- a glowing mycorrhizal fungal network beneath a forest, watercolor
- a strand of DNA as stained glass, vibrant
- a coral reef drawn as a data visualization, neon
- a single neuron firing, oil painting
- a supercomputer imagined as a city at night, cinematic
- Morehouse College campus in cherry blossom season, photograph
- a galaxy made of equations, digital art
- an HBCU classroom of the future, concept art
- a cozy coffee shop at sunrise, soft illustration

Style words to tack on: `watercolor`, `oil painting`, `photograph`, `neon`, `pixel art`, `concept art`, `cinematic`.

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
