<div align="center">

<img src="assets/optimizer-logo.svg" alt="Optimizer Skill logo" width="144">

# Optimizer Skill

### The simplest and safest path to better software with AI.

A professional **Claude Code** skill that finds real improvements in performance,
clarity, and organization — without speculative rewrites.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-plugin-D97757?logo=anthropic&logoColor=white)](https://docs.anthropic.com/en/docs/claude-code)
[![Version](https://img.shields.io/badge/version-1.0.0-6E56CF)](https://github.com/HenriqueMirandaa/optimizer-skill/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-2ea44f)](LICENSE)

</div>

## Why use it?

AI assistants can “optimize” code by adding abstractions, dependencies, and
complexity without proving that anything improved. **Optimizer Skill** enforces
a more reliable process:

> **Understand → measure → make the smallest change → verify → explain the evidence**

It is useful for refactoring, code reviews, performance bottlenecks, module
organization, and technical cleanup.

## Installation

### Recommended: install from this repository's marketplace

In Claude Code:

```text
/plugin marketplace add HenriqueMirandaa/optimizer-skill
/plugin install optimizer-skill@optimizer-skill-marketplace
```

Or from your system terminal:

```bash
claude plugin marketplace add HenriqueMirandaa/optimizer-skill
claude plugin install optimizer-skill@optimizer-skill-marketplace
```

Choose the scope that fits your workflow:

| Scope | Availability |
| --- | --- |
| `user` | All your projects on this machine |
| `project` | Everyone working in this repository |
| `local` | Only you, in this repository |

### Test without installing

Clone the repository and run:

```bash
claude plugin validate .
claude --plugin-dir .
```

To test a release ZIP for a single session:

```bash
claude --plugin-url https://github.com/HenriqueMirandaa/optimizer-skill/releases/download/v1.0.0/optimizer-skill.zip
```

## How to use

After installation, invoke the skill with:

```text
/optimizer-skill:optimizer-skill
```

Or ask Claude naturally:

```text
Use optimizer-skill on this module. Find the biggest real improvement,
measure it first, and make the smallest safe change.
```

Claude should return:

1. **Finding** — the problem discovered;
2. **Change** — the smallest effective change;
3. **Evidence** — tests and measurements;
4. **Tradeoffs** — impacts and limitations;
5. **Skipped** — work intentionally left out.

## Principles

- Measure before optimizing.
- Remove unnecessary work before adding mechanisms.
- Prefer standard-library solutions, existing helpers, and native features.
- Fix shared root causes instead of patching individual symptoms.
- Preserve security, validation, accessibility, and error handling.
- Do not add a cache, dependency, or abstraction without justification.
- Never claim a performance improvement without evidence.

## Project structure

```text
.
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── skills/
│   └── optimizer-skill/
│       ├── SKILL.md
│       └── examples/
├── assets/
│   └── optimizer-logo.svg
├── LICENSE
└── README.md
```

## Development

Requirements:

- Claude Code installed and authenticated;
- Git;
- GitHub access if you want to publish changes.

Validate the plugin before creating a release:

```bash
claude plugin validate .
```

This project does not execute custom code, install dependencies, or require an
MCP server. The skill consists of Markdown instructions that are loaded when
invoked.

## License

Distributed under the [MIT License](LICENSE).
