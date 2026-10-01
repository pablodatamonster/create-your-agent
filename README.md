<!-- Copyright 2026 Anthropic PBC -->
<!-- Modified 2026 by DataMonster -->
<!-- SPDX-License-Identifier: Apache-2.0 -->

# create-your-agent — by DataMonster

A DataMonster skill for [Claude Code](https://code.claude.com) that helps a technical founder build whatever they want on **Claude Managed Agents (CMA)** — an internal worker, a piece of their product, a customer-facing agent. It interviews you about what you want to build, scopes a v0, launches it in your own account, grades it against your own definition of done, iterates, and (if it should run on a clock) puts it on a scheduled deployment — with everything bigger laid out as an explicit v1/v2 plan.

> Maintained by [DataMonster](https://data.monster). Adapted from Anthropic's [launch-your-agent](https://github.com/anthropics/launch-your-agent) reference implementation — see [NOTICE](./NOTICE). Licensed under [Apache 2.0](./LICENSE).
>
> This is an educational skill that walks you through composing managed-agent primitives to solve your problem. Because it explains each step, it's more token-intensive than a purpose-built agent would be.

## Quickstart — Claude desktop app (starting from zero)

No terminal needed. If you've never used Claude Code before, start here.

**1. Install the Claude desktop app and sign in**
Download it from [claude.ai/download](https://claude.ai/download) (Mac or Windows) and sign in. Claude Code needs a paid plan (Pro, Max, Team or Enterprise).

**2. Download this project**
On this GitHub page, click the green **Code** button → **Download ZIP**, then unzip it somewhere easy to find (e.g. `Documents`). The folder will be called `create-your-agent-main`. That's fine, keep the name.
*(Already use git? You can clone it instead with the command in the terminal Quickstart below.)*

**3. Open the folder in Claude Code**
In the desktop app, open the **Code** tab and start a new session. When it asks for a folder, choose the `create-your-agent-main` folder you just unzipped. Choose that folder itself, not its parent and not a subfolder inside it.

**4. Start the skill**
In the chat box, type:

```
/create-your-agent
```

Claude will interview you about what you want to build, then scope it, launch it, grade it and iterate. Answer in plain language.

**5. Add your API key when asked**
Partway through, the skill asks for an Anthropic API key from **your own** account. Create one at [platform.claude.com](https://platform.claude.com) → **API keys**. Claude creates a `my-agent/.env` file for you. Open it from the app's file pane, paste the key after `ANTHROPIC_API_KEY=`, save, and tell Claude you're done. **Never paste the key into the chat.** Runs cost cents.

**6. Wrap up**
When you're finished, or any time later, type `/wrap-up` to get the overview page, a recap of everything you built and suggested next steps. Your agent lives in your Anthropic Console, and its files are in the `my-agent/` folder.

**Troubleshooting**
- *`/create-your-agent` isn't recognised:* the session is open on the wrong folder. Start a new session and choose the folder that directly contains `README.md` and the (hidden) `.claude` folder.
- *Windows:* Claude Code needs Git for Windows. If the app prompts you to install it, do that first, then start a new session.

## Quickstart — terminal

```bash
git clone https://github.com/pablodatamonster/create-your-agent.git
cd create-your-agent
claude
```

Then type:

```
/create-your-agent
```

The skills in `.claude/skills/` are picked up automatically when you run Claude Code inside this folder — nothing to install.

When you're done (or any time later), `/wrap-up` refreshes the overview page, recaps every primitive you now own, and suggests the next 1–2 upgrades.

## What you need

- Claude Code installed and signed in.
- An Anthropic API key for **your own** account (you'll create it during the flow at platform.claude.com → API keys; it goes into a local `.env` file, never into the chat). Runs cost cents.

## What you walk away with

- A live managed agent in your Console (agent + environment + graded run, plus a scheduled deployment if your task recurs).
- A `my-agent/` folder: the build sheet, the exact API payloads, a resumable launch script, an eval scaffold, an overview page, and a NEXT-DIRECTIONS.md laying out v1/v2.

## Repo layout

| Path | What it is |
|---|---|
| `.claude/skills/create-your-agent/` | The main skill: 4 phases (interview → stage & launch → grade & iterate → run without you) + references (interview mapping, verified API call shapes, examples bank, overview template) |
| `.claude/skills/wrap-up/` | Companion skill: explicit close-out / status check for a built agent |
| `cma-primitives.md` | Inventory of CMA primitives and limits, from the public docs |
| `interview-to-config.md` | Background: how interview answers map to CMA primitives |
| `examples-bank.md` | Sourced example agents and production proof points |
| `ui/` | Example overview page + build sheet |
| `NOTICE` | Attribution and summary of DataMonster's changes |

The CMA documentation is the source of truth for the API: https://platform.claude.com/docs/en/managed-agents/overview

## Attribution

create-your-agent is a DataMonster adaptation of [anthropics/launch-your-agent](https://github.com/anthropics/launch-your-agent) (© 2026 Anthropic PBC, Apache 2.0). DataMonster is not affiliated with or endorsed by Anthropic; "Claude", "Claude Code" and "Claude Managed Agents" are Anthropic products this skill runs on.
