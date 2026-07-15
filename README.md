# Minimal Maintainable Code

A lightweight Agent Skill for building the smallest **complete, clear, and maintainable** solution—without sacrificing correctness, readability, security, accessibility, validation, or output quality.

## Why this skill exists

Coding agents can produce correct code that is unnecessarily large, abstract, configurable, or difficult to maintain. This skill guides an agent to:

- understand the existing code before changing it;
- make focused, surgical changes;
- reuse existing code and platform capabilities;
- avoid speculative abstractions and dependencies;
- verify behaviour with proportionate tests and project checks;
- simplify the changed area only after it works.

The governing principle is:

> Solve the real problem with the fewest necessary concepts, not the fewest possible lines.

## Installation

### Global installation

Copy this repository folder to your agent's global skills directory:

```text
~/.agents/skills/minimal-maintainable-code/
```

### Repository installation

Copy it into a project:

```text
<repository>/.agents/skills/minimal-maintainable-code/
```

## Usage

Invoke the skill, then provide the coding task normally:

```text
$minimal-maintainable-code

Fix the calculator rounding issue and add a regression test.
```

## What it prevents

- unnecessary dependencies;
- single-use abstractions that do not improve clarity;
- speculative future-proofing;
- unrelated refactoring;
- duplicated business logic;
- compressed, clever code that is hard to read;
- unverified claims that tests or builds passed.

## What it protects

- required behaviour and output quality;
- readability and established project conventions;
- security and privacy boundaries;
- accessibility and validation;
- useful error handling and meaningful tests.

## Files

- [`SKILL.md`](SKILL.md) — the complete Agent Skill.
- [`INSTALL.md`](INSTALL.md) — concise installation instructions.

## License

MIT
