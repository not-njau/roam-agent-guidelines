# Setup instructions for the agent

You are an AI agent. A Roam Research user has asked you to set up these agent guidelines for them. Follow these steps in order. Talk to the user in short, plain sentences, and ask before you change anything that already exists in their graph.

## Step 0: Ask which way to install

Ask the user which they want:

- **Way 1: a page in their Roam graph.** Choose this when you can write to their graph through the Roam MCP connector. Roam loads the page `roam/agent guidelines` automatically for every agent that works in the graph, so the rules apply without being asked.
- **Way 2: a skill.** Choose this when the user wants the rules as a skill they call by name, or when you cannot write to their graph.

If they are unsure, recommend Way 1 when you have the Roam MCP connector, and Way 2 otherwise.

## What the user needs

- **Roam Research**, with the **Color Highlighter** extension from Roam Depot. Colour rules depend on it.
- **For Way 1:** the **Roam MCP** connector, connected to the graph. Boxes (`#.box-ch-...`), cards (`#.card-grid`), callouts and tables are native to Roam and need nothing else.

Check these first. If one is missing, tell the user what to install, and wait.

---

## Way 1: install as a page in the user's graph

### 1. Check for an existing page

Look for a page titled exactly `roam/agent guidelines`. If it exists and is not empty, tell the user what is there and ask whether to replace it, add these rules below it, or stop. Never delete their content without a clear yes.

### 2. Write the page

Create the page `roam/agent guidelines` from [`guidelines.md`](guidelines.md). Keep every block, its nesting, its order and its exact text. Skip the first line (`# roam/agent guidelines`), which is the title.

Links inside the page are written as `[alias](((LINK: words)))`. **Write them exactly as they are for now.** You will rebuild them in step 3, once every block exists and has its own UID in this graph.

### 3. Rebuild the links in the user's graph

The page links to 25 of its own rules, through 30 links. In the original graph these were block references. They must now point to the new blocks in **this** graph, never to the original graph.

1. Read the new page back, with every block's UID.
2. For each target in the table below, find the one block that matches the description, and note its UID.
3. Replace every `((LINK: words))` with `((that UID))`, keeping the alias text in square brackets. Use `update_block` on each block that holds a link.
4. Search the page for `LINK:`. None may be left. If one is left, fix it before going on.

| Marker | The block it points to |
|---|---|
| `LINK: 2. Direct attention` | The heading block **2. Direct attention** under Writing rules |
| `LINK: 3. Thread ideas` | The heading block **3. Thread ideas** under Writing rules |
| `LINK: Decision table example` | The `{{[[table]]}}` block directly under the rule starting **Every other set of options goes in a decision table.** |
| `LINK: Use a card grid` | The block starting **Use a card grid** |
| `LINK: Hue table` | The `{{[[table]]}}` block under **Colour** whose first row is **Hue** / **Meaning** |
| `LINK: Weight table` | The `{{[[table]]}}` block under **Heaviness** whose first row is **Weight** |
| `LINK: Nesting asserts a relationship.` | The block starting **Nesting asserts a relationship.** under Relate |
| `LINK: Link the most specific block` | The block starting **Link the most specific block**: under Point (not the Never skip item) |
| `LINK: Thread every chain the reader must follow:` | The block starting **Thread every chain the reader must follow:** under Thread a chain (not the Never skip item) |
| `LINK: Close the loop.` | The block starting **Close the loop.** After substantive work, under 4. Separate thinking from doing |
| `LINK: Verification` | The callout block **Verification: run it on everything you write, before you report done** |
| `LINK: Choose the weight that best shows the point.` | The block starting **Choose the weight that best shows the point.** |
| `LINK: Spend weight at the payoff.` | The block starting **Spend weight at the payoff.** |
| `LINK: Add weight when the user is still unclear.` | The block **Add weight when the user is still unclear.** under Heaviness |
| `LINK: Mark the fewest words that carry the point.` | The block **Mark the fewest words that carry the point.** |
| `LINK: Thread a chain:` | The block starting **Thread a chain:** |
| `LINK: Exception: parallel threads.` | The block starting **Exception: parallel threads.** |
| `LINK: Exception: inside a fraction, root or exponent,` | The block starting **Exception: inside a fraction, root or exponent,** |
| `LINK: Example: find x in 2x + 3 = 11.` | The block starting **Example: find x in 2x + 3 = 11.** |
| `LINK: Example: a workflow that combines forms.` | The block starting **Example: a workflow that combines forms.** |
| `LINK: Pair a visual signal with a text one,` | The block starting **Pair a visual signal with a text one,** |
| `LINK: A box takes its header's hue.` | The block starting with the orange header **A box takes its header's hue.** |
| `LINK: Reply slot:` | The block starting **Reply slot:** under Point |
| `LINK: Reply marker:` | The block starting **Reply marker:** under Graph rules |
| `LINK: Never put a code span inside an alias label.` | The block starting **Never put a code span inside an alias label.** under Point |

### 4. Set the views and collapse

- Set these blocks' children to **numbered** view: the **Never skip** callout, the **Verification** callout, every **Steps** block in the examples, and **1. Draft** in the workflow example.
- Set these blocks' children to **document** view: **Option A** and **Option B** in the card grid; **you approve the draft.** and the `{{or:}}` block under it in the workflow example; **Prepare the article** and **Prepare the thread** and the `{{or:}}` block under each.
- Collapse every table: first each of its rows, then the table block itself.
- Collapse every boxed header (a block ending in `#.box-ch-...`), except examples, solutions and boxes with an open choice.

### 5. Check, then tell the user

Read the whole page back and check:

- Every block from `guidelines.md` is there, in the same order and nesting.
- No `LINK:` is left, and every `((uid))` points to a block on this page.
- Every `$$` pairs up, and no `{{` appears inside LaTeX.

Then tell the user, in a few short sentences:

1. The page is set up, and Roam will load it for every agent in this graph.
2. **The Graph rules section holds five general rules.** Name them: Reply marker, page titles over UIDs, navigating instead of sweeping, no new pages without approval, and plain-text alias labels. Ask if they want to change or delete any, and remind them they can add their own rules there.
3. **Section 4 names two headings,** `notetoself` for reasoning and `next` for actions. Ask if they want different names, and if so, change both the rule and the matching lines in Order in time and Verification.

---

## Way 2: install as a skill

1. Copy the folder [`skill/roam-agent-guidelines`](skill/roam-agent-guidelines) into the place where the user's agent keeps skills. For example, `~/.claude/skills/` for Claude Code, the Skills settings in the Claude app, or `~/.codex/skills/` for Codex.
2. Keep the name `roam-agent-guidelines` unless the user wants another. **Tell the user its name and how to call it,** for example: "use my Roam agent guidelines". Unlike the Roam page, a skill is not always loaded, so the user may need to call it.
3. Tell the user the same three things as step 5 of Way 1: what the Graph rules hold, that they can add their own, and that the `notetoself` and `next` headings can be renamed in the skill file.
