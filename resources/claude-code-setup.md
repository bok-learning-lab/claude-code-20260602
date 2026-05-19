# Claude Code Setup Guide

**Claude Code** is Claude in your terminal — an agentic coding assistant that can read, write, and run code in your local environment.

---

## Installation

Claude Code requires Node.js 18+.

```bash
npm install -g @anthropic-ai/claude-code
```

Verify the install:
```bash
claude --version
```

---

## Authentication

Claude Code uses your Anthropic API key.

```bash
claude
```

On first launch, it will prompt you to authenticate. You can either:
- Log in with your Anthropic account (browser-based)
- Set `ANTHROPIC_API_KEY` in your environment

---

## Basic usage

Open a terminal in any project directory and run:

```bash
claude
```

This starts an interactive session. Claude can see your files and run commands with your permission.

### Example tasks

```
> explain how this codebase is structured
> add error handling to the fetchData function
> write a test for the login flow
> what does this SQL query actually do?
```

---

## Key concepts

### Permissions
Claude Code asks before running commands or modifying files. You can:
- **Allow once** — approve for this action only
- **Allow always** — add to the permanent allowlist
- **Deny** — block the action

### /slash commands
Inside a Claude Code session:
- `/help` — see all available commands
- `/clear` — start a new conversation
- `/compact` — summarize and compress conversation history (frees up context)
- `/review` — review the current branch's changes as a PR

### Working on a specific task
Be explicit about scope:
```
> only modify files in src/components/
> don't touch package.json
> run tests after every change
```

---

## For today's workshop

The `projects/` folder in this repo was built entirely using Claude Code. To explore:

```bash
cd /path/to/this/repo
claude
> how is the projects/ folder organized?
> what do the tool prompts in projects/close-reading/tools/ do?
```

Claude Code is especially powerful when you want Claude to not just generate content but also move files, run scripts, and build on existing project structure.

---

## Docs and resources

- Full documentation: [docs.anthropic.com/claude-code](https://docs.anthropic.com/claude-code)
- GitHub issues and feedback: [github.com/anthropics/claude-code](https://github.com/anthropics/claude-code)
