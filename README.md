# Minimal Maintainable Code — Agent Skill for Clean, Focused AI Coding

A lightweight **Agent Skill for AI coding agents** that reduces unnecessary code, abstractions, dependencies, configuration, and unrelated refactoring—without sacrificing correctness, readability, security, accessibility, validation, tests, or output quality.

> **In one sentence:** Minimal Maintainable Code helps a coding agent solve the real problem with the fewest necessary concepts, not the fewest possible lines.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](SKILL.md)

## What problem does this solve?

AI coding assistants can produce working code that is unnecessarily large, over-engineered, highly configurable, or difficult to maintain. Common symptoms include:

- new layers and abstractions for one small task;
- duplicate helpers or business logic;
- speculative future-proofing;
- unnecessary packages and configuration;
- broad refactoring unrelated to the request;
- compressed code that is short but hard to understand;
- claims that tests or builds passed when they were not run.

This skill guides the agent to inspect the existing project first, make the smallest complete change, verify it proportionately, and simplify only the code affected by the task.

## Core principles

1. **Understand before changing** — inspect relevant code, tests, configuration, and nearby conventions.
2. **Prefer the simplest complete solution** — reuse existing code and platform capabilities before adding anything new.
3. **Protect output quality** — never trade correctness or readability for fewer lines.
4. **Make surgical changes** — avoid unrelated formatting, renaming, dependency updates, or refactoring.
5. **Verify proportionately** — run relevant tests and available lint, type-check, and build commands.
6. **Simplify after it works** — review only the changed area for unnecessary concepts.

The governing principle is:

> **Solve the real problem with the fewest necessary concepts, not the fewest possible lines.**

## Quick start

### Install globally

Copy this repository into your agent's global skills directory:

```text
~/.agents/skills/minimal-maintainable-code/
```

### Install in one project

Copy it into the repository:

```text
<repository>/.agents/skills/minimal-maintainable-code/
```

### Invoke the skill

```text
$minimal-maintainable-code

Fix the calculator rounding issue and add a regression test.
```

The agent should then inspect the relevant project files, implement the smallest complete solution, run the available checks, and report what changed.

See [`INSTALL.md`](INSTALL.md) for concise installation instructions.

## When should I use it?

Use this skill when asking an AI coding agent to:

- build a feature;
- fix a bug;
- modify an existing application;
- refactor a focused area;
- review recently changed code;
- reduce AI-generated code bloat;
- avoid over-engineering in a small or growing project;
- preserve an existing architecture while making a targeted change.

It is language- and framework-neutral. It works with coding agents that support the `SKILL.md` Agent Skills format.

## What it prevents

- unnecessary dependencies;
- single-use abstractions that do not improve clarity;
- speculative configurability;
- wrappers that only rename another function;
- duplicated formulas or business rules;
- unrelated cleanup disguised as implementation;
- clever one-liners that reduce readability;
- tests that only mirror implementation details;
- unverified completion claims.

## What it protects

- required behaviour and output quality;
- established project conventions;
- readable control flow and descriptive names;
- security and privacy boundaries;
- accessibility and validation;
- useful error handling;
- meaningful tests;
- focused, reviewable diffs.

## Minimal code does not mean fewer lines at any cost

This is not a code-golfing skill. It does **not** tell the agent to compress everything into one line or remove useful structure.

A slightly longer solution is preferred when it is clearer, safer, easier to test, or more maintainable. The target is lower conceptual complexity—not artificially low line count.

## Example tasks

### Bug fix

```text
$minimal-maintainable-code

Fix the incorrect monthly cost calculation. Reuse the existing calculation library and add a focused regression test.
```

### Feature addition

```text
$minimal-maintainable-code

Add CSV export to the existing results table. Use current project patterns and avoid adding a dependency unless it is genuinely necessary.
```

### Focused refactor

```text
$minimal-maintainable-code

Remove duplication introduced in the current diff while preserving behaviour. Do not refactor unrelated files.
```

## How is this different from a generic clean-code prompt?

Generic prompts often contain broad or absolute rules that can encourage excessive interfaces, layers, classes, or rewrites. Minimal Maintainable Code focuses on the current repository and the current task:

- it follows existing conventions instead of imposing a new architecture;
- it permits abstractions only when they solve a present problem;
- it treats verification as part of completion;
- it limits cleanup to the changed area;
- it protects quality rather than optimizing blindly for fewer lines.

## Frequently asked questions

### Does this skill automatically modify my code?

The skill guides the coding agent while it performs the task you give it. Review the resulting diff and verification results before merging, as you would with any AI-generated change.

### Can it guarantee perfect or bug-free code?

No. It improves the agent's decision process, scope control, and verification discipline, but it cannot guarantee correctness. Tests, review, and project-specific safeguards still matter.

### Will it reduce token usage?

It may reduce wasted implementation and review effort by discouraging unnecessary code and scope expansion. It does not promise lower model reasoning-token usage for every task.

### Is it only for small projects?

No. It is especially useful for solo and small-team projects, but the principles also apply to larger repositories where focused diffs and architectural consistency matter.

### Does it replace project-specific instructions?

No. Repository instructions, coding standards, architecture decisions, and security requirements should take priority. This skill complements them by encouraging focused, proportionate implementation.

### Is it inspired by Karpathy-style coding guidelines?

Yes. It adapts the principles of thinking before coding, making minimal changes, avoiding speculative complexity, and verifying success—while adding safeguards against harmful over-simplification.

## Repository contents

- [`SKILL.md`](SKILL.md) — complete Agent Skill instructions.
- [`INSTALL.md`](INSTALL.md) — installation and invocation guide.
- [`llms.txt`](llms.txt) — concise machine-readable project summary.
- [`LICENSE`](LICENSE) — MIT License.

## Contributing

Issues and pull requests are welcome. Keep proposed changes focused, explain the problem they solve, and avoid adding rules that are language-specific, highly subjective, or unnecessarily absolute.

## License

Released under the [MIT License](LICENSE).