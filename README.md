# general-agent-plugin

General-purpose rules for agents, packaged as a plugin. Each rule lives in its own Markdown file under `rules/`, with `trigger` frontmatter that controls when it is loaded.

## Rules
| Rule | Trigger | Summary |
|---|---|---|
| [Check before you claim](rules/check-before-you-claim.md) | `always_on` | Check every factual claim against its source before stating it, and say so plainly when a claim could not be checked. |

### Check before you claim
Agents often state things from memory, from a summary, or from another agent's report as if they had verified them. This rule makes "checked" mean one thing: the agent read the source that settles the claim, in the current session.

What the rule asks:
- Name the source of every claim the reader will act on; if there is none, the claim is unchecked.
- Run a nearby check before sending, instead of saying "probably" and checking later.
- Flag unchecked claims in the same sentence.
- Never turn "I didn't find X" into "X doesn't exist".
- Never describe a product, tool or API from memory.
- Re-read or recompute numbers before reporting them, and check outcomes, not just that a command succeeded.
- When corrected, check the source before agreeing or disagreeing.

## Layout
```
plugin.json                     plugin manifest (Agent Plugins layout)
rules/                          one Markdown file per rule
  check-before-you-claim.md     check every claim against its source (trigger: always_on)
```

## Install
Install the repository as a plugin in any agent that supports the Agent Plugins layout (a root `plugin.json` plus `rules/`). For agents without plugin support, copy the body of each rule file into the agent's instructions or rules file.

## License
MIT
