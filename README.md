# Manware's AI Learning Toolkit for Codex

A set of instructions that turns Codex into a programming learning companion. You try, predict, implement, and explain; Codex asks questions, offers small hints, and helps you verify your reasoning.

This is the `codex` version of the toolkit. The repository also has branches for Copilot, Cursor, Claude Code, OpenCode, and Antigravity.

## Install in a project

For an existing coding project, copy `AGENTS.md`, `workflows/`, and optionally `learning/` from this branch into the **top-level folder of that project**, beside its own README or source folders. Open that project folder in Codex. The instructions then apply to Codex work in that project, across chats that use the folder. They do not change Codex in unrelated projects.

For a new project based on this toolkit, clone the `codex` branch and work inside the cloned folder:

```sh
git clone --branch codex https://github.com/thekipje-boop/Manware-s-AI-Learning-Toolkit.git my-learning-project
```

`AGENTS.md` in a separate clone of this toolkit will not affect a different coding project. Copy it into that project's top-level folder if that is where you want the learning behavior.

## Use a learning mode

Tell Codex which mode you want in ordinary text, for example: **"Use hint mode for this problem"** or **"Use debug mode with this error."** You can also say **"Help me learn this"** and let Codex select a mode. The names below are modes described in `workflows/`; they are not native Codex slash commands.

| Mode | What it does |
| --- | --- |
| `learn` | Pick a useful learning workflow. |
| `hint` | Give incremental hints after your attempt and prediction. |
| `debug` | Diagnose a bug by testing your hypothesis. |
| `autopsy` | Reflect on a bug you have already fixed. |
| `read` | Reconstruct how unfamiliar code works. |
| `code-review` | Review your code while teaching the reasoning behind findings. |
| `test` | Derive test cases before implementation. |
| `explore` | Compare designs and test them against new constraints. |
| `arch` | Work through an architecture interview. |
| `explain` | Test your understanding by teaching a concept back. |
| `retrieve` | Practice recalling material from your learning logs. |
| `api` | Investigate an API's purpose, tradeoffs, and failure modes. |

The usual loop is: **attempt → predict → hint → implement → test → explain → review → retrieve**. Codex asks one focused question at a time and helps you verify ideas. You remain the author of your practice code.

## Direct implementation

When you need a completed change, ask Codex to **"implement this"**, **"give me the full answer"**, or **"ship this"**. `AGENTS.md` tells Codex to switch to normal engineering assistance for that request. You do not need to remove the toolkit first.

## Learning logs

The optional `learning/` folder has files for mistakes, concepts, questions, and review topics. Codex uses them for `retrieve` mode when they contain entries. Ask Codex to record a meaningful lesson when you want one saved; the toolkit does not require a log after every interaction.

## Files

```text
AGENTS.md           Shared instructions and workflow routing for this project
workflows/           The 12 learning modes
learning/            Optional learning logs
```

This toolkit is prompt-based. It needs no API key, scripts, or dependencies. See the [official Codex guidance on `AGENTS.md`](https://learn.chatgpt.com/docs/agent-configuration/agents-md) for how project instructions are loaded.
