# PR Workflows

A skills-only plugin for building reviewable pull request stacks and writing descriptions that
tell reviewers what changed, where to look, and what they need to decide.

It works with Codex and Claude Code from the same private repository.

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

Start a new conversation after installation so the skills are discovered.

## Update

```sh
codex plugin marketplace upgrade pr-workflows
codex plugin add pr-workflows@pr-workflows

claude plugin marketplace update pr-workflows
claude plugin update pr-workflows@pr-workflows
```

## Layout

The repository is both a Codex and Claude Code marketplace. The installable package lives at
`plugins/pr-workflows`, with portable, Codex, and Claude manifests alongside the shared `skills/`
directory.

## Licence

MIT — see [LICENSE](./LICENSE).
