# Roam agent guidelines

One page of rules that makes every AI agent in your Roam Research graph write so you can understand it: callouts, tables, side-by-side cards, decision tables that wait for your reply, and colour that threads ideas together.

These are the guidelines from the Roam 'n' Around newsletter article *Intelligence at the Level of Thought (IV): Getting Your Agent to Write for Understanding*.

## Get them in one step

Paste this sentence into your AI agent (Claude, ChatGPT, Codex or any agent that can read a web page):

> Set up the Roam agent guidelines from https://github.com/not-njau/roam-agent-guidelines for me. Follow SETUP.md.

Your agent reads [`SETUP.md`](SETUP.md) and asks you which of two ways you want.

| Way | What you get | What you need |
|---|---|---|
| **1. A page in your graph** (recommended) | The page `roam/agent guidelines` in your own graph. Roam loads it for every agent that works there, so you never have to ask. All links inside it point to blocks in your graph. | The **Roam MCP** connector, so your agent can write to your graph |
| **2. A skill** | A skill named `roam-agent-guidelines` that you call, for example by saying "use my Roam agent guidelines". | An agent that supports skills, such as Claude or Codex |

Both ways need the **Color Highlighter** extension from Roam Depot. Boxes, cards, callouts and tables are native to Roam.

## Make them yours

- **Graph rules** at the bottom of the page are where you add your own rules for your graph. Five general ones are there to start, and your agent will ask if you want to change or delete any.
- **Section 4** names two headings, `notetoself` for reasoning and `next` for actions. Rename them to fit your graph.

## What is in this repository

| File | For | What it holds |
|---|---|---|
| `README.md` | You | This page |
| `SETUP.md` | Your agent | Step-by-step setup for both ways, and a check at the end |
| `guidelines.md` | Your agent | The page itself, in Roam markup |
| `skill/roam-agent-guidelines/SKILL.md` | Your agent | The same rules as a skill |

## Licence

MIT. Use, change and share them freely. See [`LICENSE`](LICENSE).
