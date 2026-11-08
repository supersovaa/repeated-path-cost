# repeated-path-cost

A lightweight skill for examining recurring compute and resource costs across an actual processing path.

## Core idea

Repeated work scales with invocation count, input growth, accumulated state, and concurrency. Evaluate the full recurring path instead of optimizing one isolated step.

## When to use

Activate when designing, implementing, refactoring, or reviewing processing whose runtime or memory use grows with repetitions, workload size, or simultaneous workers.

## Responsibility

Trace repeated work, including conversions, validation, logging, and replay; estimate runtime, peak retained-memory growth, and concurrency cost. Correct code-established problems directly; use representative end-to-end measurements for unresolved decisions or settled quantitative guarantees.

Data-path directness belongs to [direct-data-flow](https://github.com/supersovaa/direct-data-flow). CI execution belongs to [ci-execution-efficiency](https://github.com/supersovaa/ci-efficiency); costly complete-trial selection belongs to [test-execution-budget](https://github.com/supersovaa/requirement-driven-testing/blob/main/skills/execution/SKILL.md). The relevant planning workflow owns plan dependencies.

Detailed operating rules live in [SKILL.md](SKILL.md).

## Installation

Install this repository as a skill directory in an AI-agent environment supporting `SKILL.md`. Keep `SKILL.md` at the skill directory root and register it at the applicable design, implementation, refactoring, and review task entry points.
