# Install Minimal Maintainable Code

Minimal Maintainable Code is a lightweight `SKILL.md` package for coding agents that support the Agent Skills format.

## Option 1: Install globally

Clone or copy the repository into your global skills directory:

```bash
git clone https://github.com/sharpscroll/minimal-maintainable-code.git ~/.agents/skills/minimal-maintainable-code
```

Expected location:

```text
~/.agents/skills/minimal-maintainable-code/SKILL.md
```

Use this option when you want the skill available across projects.

## Option 2: Install in one repository

From the project root:

```bash
git clone https://github.com/sharpscroll/minimal-maintainable-code.git .agents/skills/minimal-maintainable-code
```

Expected location:

```text
<repository>/.agents/skills/minimal-maintainable-code/SKILL.md
```

Use this option when you want the skill scoped to one project or committed with the repository.

## Invoke the skill

Select or mention:

```text
$minimal-maintainable-code
```

Then provide the development task normally:

```text
$minimal-maintainable-code

Fix the calculator rounding issue and add a focused regression test.
```

## Recommended task pattern

```text
$minimal-maintainable-code

Implement the requested change using the existing project architecture.
Preserve required behaviour and output quality.
Run the relevant tests and available lint, type-check, and build commands.
Report what changed, checks run, and any remaining risk.
```

## Updating

For a Git installation:

```bash
cd ~/.agents/skills/minimal-maintainable-code
git pull
```

Adjust the path when installed inside a repository.

## Before using a third-party skill

Read [`SKILL.md`](SKILL.md) before installation. Agent Skills influence coding-agent behaviour, so review updates before pulling them into sensitive projects.
