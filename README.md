# repeated-path-cost

A lightweight skill for examining recurring compute and resource costs across an actual processing path.

## Core idea

Repeated work scales with invocation count, input growth, accumulated state, and concurrency. Evaluate the full recurring path instead of optimizing one isolated step.

## When to use

Activate when designing, implementing, refactoring, or reviewing processing whose runtime or memory use grows with repetitions, workload size, or simultaneous workers.

## Responsibility

Trace the repeated path; estimate time and peak retained-memory growth; include transformations, validation, logging, replay, and other ancillary work; account for resources multiplied by concurrency; and ground material performance decisions in representative end-to-end measurements.

Data-path directness belongs to [direct-data-flow](https://github.com/supersovaa/direct-data-flow). CI execution belongs to [ci-execution-efficiency](https://github.com/supersovaa/ci-efficiency); costly complete-trial selection belongs to [test-execution-budget](https://github.com/supersovaa/requirement-driven-testing/blob/main/skills/execution/SKILL.md). The relevant planning workflow owns plan dependencies.

Detailed operating rules live in [SKILL.md](SKILL.md).

## Installation

Install this repository as a skill directory in an AI-agent environment supporting `SKILL.md`. Keep `SKILL.md` at the skill directory root and register it at the applicable design, implementation, refactoring, and review task entry points.
