# y - Claude Code Configuration Repo

Repository: `mo666-med/y`
License: MIT (Masayuki Otawara, 2025)

## What this repo is

A Claude Code project configuration repo. It contains agent definitions,
slash commands, MCP server scripts, GitHub Actions workflows, and a hook.
There is **no application source code** -- no `package.json`, no `src/`,
no `tsconfig.json`, no `tests/`.

## File structure

```
y/
├── CLAUDE.md
├── README.md
├── LICENSE                         # MIT
├── .gitignore                      # Node/JS template (aspirational)
├── .Rhistory                       # empty
├── assets/
│   └── 2026-04-05-ai-confirms-you-thumb.png
├── .claude/
│   ├── settings.example.json       # example config (no settings.json)
│   ├── mcp.json                    # 6 MCP server definitions
│   ├── agents/                     # 6 agent definition markdown files
│   ├── commands/                   # 12 slash command markdown files
│   ├── hooks/log-commands.sh       # LDD-style prompt logger
│   └── mcp-servers/                # 4 JS MCP server scripts
└── .github/workflows/              # 14 GitHub Actions workflow files
```

## Slash commands (.claude/commands/)

| Command           | File               | Purpose                        |
|--------------------|--------------------|--------------------------------|
| `/test`            | test.md            | Run tests                      |
| `/verify`          | verify.md          | System health check            |
| `/deploy`          | deploy.md          | Deployment                     |
| `/agent-run`       | agent-run.md       | Autonomous agent pipeline      |
| `/create-issue`    | create-issue.md    | Interactive issue creation      |
| `/generate-docs`   | generate-docs.md   | Auto-generate documentation    |
| `/security-scan`   | security-scan.md   | Security vulnerability scan    |
| `/miyabi-agent`    | miyabi-agent.md    | Miyabi agent execution         |
| `/miyabi-auto`     | miyabi-auto.md     | Miyabi automation              |
| `/miyabi-init`     | miyabi-init.md     | Miyabi project initialization  |
| `/miyabi-status`   | miyabi-status.md   | Miyabi status check            |
| `/miyabi-todos`    | miyabi-todos.md    | Miyabi TODO management         |

## MCP servers (.claude/mcp-servers/)

- **github-enhanced.js** -- GitHub Issue/PR operations (requires `GITHUB_TOKEN`)
- **ide-integration.js** -- VS Code diagnostics / Jupyter integration
- **miyabi-integration.js** -- Miyabi CLI wrapper
- **project-context.js** -- Project dependency and context info

## GitHub Actions (.github/workflows/)

14 workflows including: `autonomous-agent.yml`, `economic-circuit-breaker.yml`,
`state-machine.yml`, `webhook-handler.yml`, `issue-opened.yml`, `pr-opened.yml`,
`deploy-pages.yml`, `label-sync.yml`, `weekly-kpi-report.yml`, `weekly-report.yml`.

## Constraints

- No runtime code exists. Commands and agents are prompt-only (markdown).
- The `.gitignore` is a generic Node template; it does not reflect actual content.
- `settings.example.json` references paths like `agents/coordinator/coordinator-agent.ts`
  that do not exist. It is a template, not a working config.
- The hook `log-commands.sh` writes to `.ai/logs/` (not committed).
