---
name: minimal-maintainable-code
description: Build, modify, review, or refactor code using the smallest clear and maintainable solution that fully satisfies the request. Use for coding tasks where correctness, simplicity, surgical changes, reuse of existing code, verification, and avoidance of speculative abstractions, dependencies, configuration, or unrelated refactoring matter.
license: MIT
compatibility: Works with coding agents that support the Agent Skills SKILL.md format.
metadata:
  version: "1.0.0"
  inspiration: "Karpathy-style coding guidelines, adapted for balanced minimalism"
---

# Minimal Maintainable Code

Build the smallest **complete, clear, and maintainable** solution that satisfies the request.  
Do not optimize for the fewest lines. Never trade away correctness, readability, security, accessibility, validation, useful error handling, or required output quality merely to make code shorter.

## 1. Understand before changing

Before writing code:

1. Read the relevant existing files, tests, configuration, and nearby patterns.
2. Restate the intended outcome internally and identify concrete success checks.
3. For a non-trivial task, make a brief plan in the form:
   - change → verification
4. Surface any important assumption that affects behavior.

For minor, reversible ambiguity, choose the simplest reasonable interpretation, state the assumption briefly, and continue.

Ask for clarification only when the choice could cause:

- data loss;
- a security or privacy risk;
- a breaking public API or schema change;
- a major architectural commitment;
- substantial irreversible rework.

## 2. Prefer the simplest complete solution

Implement only what the task requires.

Prefer, in this order:

1. Reuse an existing function, component, pattern, or dependency.
2. Extend an existing abstraction when it remains coherent.
3. Use the language, framework, browser, or standard-library capability.
4. Add small direct code.
5. Add a new dependency or abstraction only when it clearly reduces real complexity.

Do not add:

- speculative features;
- imagined future flexibility;
- configuration for a single fixed use case;
- wrappers that only rename another call;
- interfaces, factories, services, repositories, or layers without a current need;
- a dependency for a small operation that is clearer to implement directly;
- defensive handling for impossible states unless the code boundary requires it.

A useful abstraction must have a clear present purpose. Do not create one merely because similar code might exist later.

## 3. Preserve clarity and output quality

Minimal means fewer unnecessary concepts, not compressed or clever code.

Use:

- descriptive names;
- straightforward control flow;
- existing project conventions;
- one source of truth for shared business logic;
- comments only for non-obvious reasoning, constraints, or tradeoffs.

Avoid:

- dense one-liners that reduce readability;
- duplicated formulas or business rules;
- hidden side effects;
- premature performance optimization;
- generic helpers that obscure a simple local operation;
- comments that merely repeat the code.

Keep related logic together unless separation provides a clear current benefit.

## 4. Make surgical changes

Every changed line should trace to the requested outcome or to cleanup made necessary by that change.

Do not:

- reformat unrelated files;
- rename unrelated symbols;
- update unrelated dependencies;
- refactor neighboring code that is not required;
- replace working project conventions with personal preferences.

Remove imports, variables, branches, files, or helpers that **your change** makes unused.

When pre-existing problems are noticed but are not required for the task, mention them separately instead of silently expanding the scope.

## 5. Protect behavior with proportionate verification

Choose verification that matches the risk.

When practical:

1. Reproduce the bug or define the expected behavior.
2. Add or update a focused test for meaningful logic.
3. Implement the change.
4. Run the relevant existing tests.
5. Run the project's available lint, format, type-check, and build commands.
6. Review the final diff for unnecessary code and accidental scope expansion.

Do not write tests that only mirror implementation details or add no meaningful protection.

Never claim a check passed unless it was actually run. If a check cannot run, state why and identify the remaining risk.

## 6. Simplify once, after it works

After correctness is established, inspect only the changed area and ask:

- Can existing code replace something newly added?
- Is any new abstraction used only once without improving clarity?
- Is any branch, option, wrapper, comment, or configuration unnecessary?
- Can the same behavior be expressed more directly without harming readability?
- Did the task introduce duplicate business logic?

Simplify where the answer is clearly yes. Do not perform a broad cleanup pass.

## 7. Completion standard

Before finishing, confirm:

- The requested behavior is complete.
- Existing behavior outside the task is preserved.
- The solution follows the repository's established style.
- No unnecessary dependency, file, abstraction, configuration, or feature was added.
- Important validation, security, accessibility, and error handling remain intact.
- Relevant verification was run.
- The diff is focused and understandable.

Finish with a concise report:

- what changed;
- why this approach was the simplest complete solution;
- checks run and their results;
- any unresolved risk or assumption.

## Governing principle

**Solve the real problem with the fewest necessary concepts, not the fewest possible lines.**
