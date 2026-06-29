# Set Up Your Workspace

Your workspace is the `grant-writing-starter` repo: a folder of markdown that holds your profile, your skills, and your grants. This page gets it onto your machine, open in your tool, and ready to meet Sage. It is the short version. The repo's [SETUP.md](https://github.com/ashleyscruse/grant-writing-starter/blob/main/SETUP.md) has the full detail, including Windows and Mac differences and how to keep your copy updated all week.

Three moves: make your own copy, get it onto your computer, open it and say hi.

## Step 1: Make your own copy

The starter lives at `github.com/ashleyscruse/grant-writing-starter`. You need your own copy so you can save your work. You have two ways to make one, and either way your copy is yours while the original stays safe.

| | **Fork** | **Use this template** |
|---|---|---|
| What it makes | Your own copy, linked to the original | Your own copy, independent |
| Pull updates during the week? | Yes, one click | Not automatically |
| Best for | This accelerator | A standalone project later |

**For this week, choose Fork.** When shared materials get added during the workshop, a fork lets you pull them in with one command.

To fork on the web: open the repo page, click **Fork** (top right), then **Create fork**. Your copy appears at `your-username/grant-writing-starter`.

If you want help when you get stuck, go to your fork's **Settings → Collaborators** and add `ashleyscruse`. Your work stays yours; this just lets Ashley look when you need a hand.

## Step 2: Get it onto your computer

Pick whatever you are comfortable with. All three give you the full folder.

| Option | How | Can you pull updates later? |
|---|---|---|
| **Download ZIP** | Green **Code** button → **Download ZIP**, then unzip | No (re-download for updates) |
| **GitHub Desktop** | Green **Code** button → **Open with GitHub Desktop → Clone** | Yes (click **Pull origin**) |
| **Command line (git)** | Authenticate once, then clone (below) | Yes (`git pull`) |

For the command line, authenticate once with the GitHub CLI:

```
gh auth login
```

Choose **GitHub.com → HTTPS → Login with a web browser** and follow the prompts. Then clone your own fork (use your username, not Ashley's):

```
git clone https://github.com/YOUR-USERNAME/grant-writing-starter.git
cd grant-writing-starter
```

One shortcut: if you have the GitHub CLI, you can fork and clone in a single command and skip the web steps entirely:

```
gh repo fork ashleyscruse/grant-writing-starter --clone
```

## Step 3: Open it in your tool and meet Sage

This is just a folder of markdown, so it opens in any AI tool. The `CLAUDE.md` file and the `.claude/skills/` folder tell the AI how to behave; the `.claude/profile/` folder tells it who you are.

The **universal move** in any tool: open the folder, then paste this one line to the AI:

> "Read CLAUDE.md and .claude/skills/setup-guide/SKILL.md, then be Sage and guide me."

That points the AI at Sage, your setup guide, who walks you through your profile one file at a time.

| Tool | How to open the folder | How to start Sage |
|---|---|---|
| **Claude Code** (the CLI) | `cd` into the folder, run `claude` | Just say **hi**. It reads `CLAUDE.md` on its own and Sage introduces the process. |
| **Cursor** | File → Open Folder → your repo | Open chat (Cmd/Ctrl + L), paste the universal line |
| **VS Code + Copilot** | File → Open Folder → your repo | Open Copilot Chat, paste the universal line |
| **Claude on the web** (claude.ai) | No folder to mount. **Upload** `CLAUDE.md`, `.claude/skills/setup-guide/SKILL.md`, and the profile file you are filling (start with `identity.md`) into a Project | Paste the universal line |

Claude Code is the only tool that reads `CLAUDE.md` automatically, so "hi" is enough there. Everywhere else, the universal line does the pointing. If you are on Claude on the web, keep the downloaded folder on your computer so you can upload files in and save your work back out.

## A note on saving your work

Your project lives in two places: GitHub (online) and your computer (offline). If you use git or GitHub Desktop, send your changes up as you go:

```
git add .
git commit -m "what I changed"
git push
```

And bring down anything that changed online:

```
git pull
```

One thing that trips people up: if you edit a profile file in the GitHub web interface and click **Commit changes**, those edits are on GitHub but not yet on your laptop. Run `git pull` on your computer so your AI tools can read them. The repo's [SETUP.md](https://github.com/ashleyscruse/grant-writing-starter/blob/main/SETUP.md) covers this and updates in full.

## You are set up when

You have your own fork, the folder is on your computer and open in your tool, and Sage has said hello. That is the entire setup. Next, you fill in your profile (Sage helps), which is the subject of the next page.
