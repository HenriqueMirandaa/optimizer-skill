---
name: optimizer-skill
description: Improve software by finding the smallest safe change that makes it faster, simpler, cleaner, or better organized. Use for performance work, refactoring, code cleanup, architecture improvements, and reviews where optimization is requested.
---

# Optimizer Skill

Optimize for **correctness first, measurable performance second, and simplicity always**.
Do not rewrite code merely to make it look different.

## Required workflow

1. **Understand the boundary**
   - Inspect the relevant files, callers, data flow, dependencies, and existing tests.
   - Identify the actual bottleneck, duplication, defect, or organizational problem.
   - Preserve public behavior unless the user explicitly requests a behavior change.

2. **Measure or establish a baseline**
   - Prefer existing benchmarks, profilers, logs, query plans, bundle reports, or test timings.
   - If no measurement exists, state the assumption and add the smallest useful check.
   - Never claim a performance improvement without evidence.

3. **Choose the smallest effective change**
   - Prefer deletion, a standard-library solution, an existing helper, or a native platform feature.
   - Avoid speculative abstractions, premature caching, unnecessary dependencies, and broad rewrites.
   - Keep validation, error handling, security, accessibility, and type safety intact.

4. **Implement surgically**
   - Follow the repository's existing conventions.
   - Fix the shared root cause rather than patching individual callers.
   - Keep unrelated behavior and files unchanged.

5. **Verify**
   - Run the narrowest relevant tests, linter, formatter, type checker, and benchmark.
   - Check edge cases introduced by the change: empty input, large input, failure paths, concurrency, and resource cleanup when applicable.
   - Compare the result with the baseline and report tradeoffs honestly.

## Optimization priorities

Use this order unless evidence justifies another:

1. Remove unnecessary work.
2. Choose the correct algorithm or data structure.
3. Reduce I/O, network calls, database round trips, and serialization.
4. Reuse existing computation safely.
5. Improve memory use without harming clarity.
6. Only then consider micro-optimizations.

## Clean-code rules

- One clear responsibility per function or module.
- Names should explain intent; comments should explain only non-obvious constraints.
- Prefer straightforward control flow over clever compression.
- Do not create an abstraction with only one meaningful consumer.
- Do not split small, cohesive logic into files just for organization.
- Keep configuration for values that genuinely vary.
- Remove dead code and unused dependencies only when their scope is clear.

## Safety rules

- Do not remove input validation, authorization, escaping, rate limits, retries, or error handling to gain speed.
- Do not introduce global mutable state or unbounded caches.
- Do not optimize database code without checking indexes, query plans, transaction behavior, and result cardinality.
- Do not trade correctness for speed without explicit approval.
- Flag changes that need production profiling, load testing, migration, or monitoring.

## Response format

Return:

1. **Finding** — the bottleneck, complexity, duplication, or organization issue.
2. **Change** — what was changed and why this is the smallest effective fix.
3. **Evidence** — tests, measurements, or the assumption used.
4. **Tradeoffs** — behavior, memory, compatibility, or operational impact.
5. **Skipped** — tempting work that was intentionally not added and when it would be justified.

If no meaningful optimization is supported by evidence, say so and leave the code unchanged.
