# PR Workflows

A skills-only plugin for building reviewable pull request stacks and writing descriptions that
tell reviewers what changed, where to look, and what they need to decide.

It works with Codex and Claude Code as a plugin. OpenCode can load the same skills directly.

## Skills

- `writing-pr-descriptions` writes or tightens concise, current pull request descriptions while
  preserving the repository's own template.
- `building-pr-stacks` splits large changes into independently green pull requests, documents the
  complete stack in every PR, and handles restacking when a base moves.

## Install

You need GitHub access to `will-not-hx/pr-workflows` and working Git credentials.

### Codex

```sh
codex plugin marketplace add will-not-hx/pr-workflows --ref main
codex plugin add pr-workflows@pr-workflows
```

### Claude Code

```sh
claude plugin marketplace add will-not-hx/pr-workflows
claude plugin install pr-workflows@pr-workflows
```

### OpenCode V2

OpenCode loads the skills directly; its plugin system does not use the Codex or Claude Code
marketplace manifests. If you have installed the Claude Code marketplace above, add its Git-backed
skills directory to the `skills` array in `~/.config/opencode/opencode.json` (merge this entry with
any existing configuration):

```json
{
  "$schema": "https://opencode.ai/config.json",
  "skills": [
    "~/.claude/plugins/marketplaces/pr-workflows/plugins/pr-workflows/skills"
  ]
}
```

If you use OpenCode without Claude Code, clone this repository with your Git credentials and point
the `skills` entry at `<checkout>/plugins/pr-workflows/skills` instead. Update that checkout with
`git pull --ff-only` when the skills change. OpenCode V2 reads the existing `SKILL.md` files; no
OpenCode plugin package is needed.

Start a new conversation after installation so the skills are discovered.

## Update

```sh
codex plugin marketplace upgrade pr-workflows
codex plugin add pr-workflows@pr-workflows

claude plugin marketplace update pr-workflows
claude plugin update pr-workflows@pr-workflows
```

OpenCode reads the directory configured above. If it points at the Claude Code marketplace checkout,
Claude Code's marketplace updates supply the new skill files; start a new OpenCode session to pick
them up.

## Layout

The repository is both a Codex and Claude Code marketplace. The installable package lives at
`plugins/pr-workflows`, with portable, Codex, and Claude manifests alongside the shared `skills/`
directory.

## Licence

MIT — see [LICENSE](./LICENSE).
