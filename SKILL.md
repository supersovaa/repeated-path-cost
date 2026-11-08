---
name: repeated-path-cost
description: Evaluate recurring runtime and resource cost when designing, implementing, refactoring, or reviewing paths repeated by workload size, iteration count, or concurrency.
---

# Repeated Path Cost

Use this skill when designing, implementing, refactoring, or reviewing a processing path whose work repeats with input size, iteration count, accumulated state, or concurrent execution.

This skill targets a single-user AI-agent development workflow.

## Examine the whole repeated path

1. Identify the actual entry point, one unit of useful work, the expected workload, and the factors that multiply repetitions.
2. Trace work performed on every repetition, including computation, conversions, serialization, allocation, copying, retained history, validation, replay, logging, and diagnostics.
3. Estimate how total work and peak retained memory scale with the number and size of inputs. Check whether repeatedly traversing or retaining a growing prefix creates quadratic or greater growth.
4. Account for concurrency across all layers. Relate the number of independent workers to per-worker threads, temporary allocations, retained memory, and shared resource contention.
5. Compare the frequency and cost of ancillary work with the guarantee it supports. Select a lower-frequency or lighter path when it establishes the same required guarantee.
6. Compare the affected full path with direct alternatives. Reassess provisional connection or proof-of-concept mechanisms against the recurring production workload before selecting them for that path.

## Choose correction or measurement

Estimate material costs from plausible workloads. Distinguish code-established problems, predicted scaling, and measured performance.

When code inspection establishes an actionable defect or avoidable recurring cost and its correction preserves settled behavior and scope, proceed directly to correction in the owning implementation workflow. Verify the corrected behavior with focused checks. Treat the code finding as sufficient evidence to begin correction.

Use measurement for questions that remain after acting on established code findings: choosing between viable implementations, locating an unresolved cause, or verifying a settled quantitative performance guarantee. Compare representative inputs and equivalent work through the affected end-to-end path, including relevant concurrency. Use stage measurements where they help determine the next change; consider throughput, latency, memory, and contention as applicable. Reuse comparable evidence and keep measurement effort proportional to the unresolved question.

Report code-grounded findings and focused verification separately from measured outcomes. Describe the conditions, uncertainty, and resource tradeoff for measurements used in the decision. Keep performance work within the current settled requirements and implementation boundary.

## Responsibility boundary

This skill owns the cost of repeated processing across the affected runtime path.

[direct-data-flow](https://github.com/supersovaa/direct-data-flow/blob/main/SKILL.md) owns whether conversions and forwarding stages are necessary. [ci-execution-efficiency](https://github.com/supersovaa/ci-efficiency/blob/main/skills/execution/SKILL.md) owns CI execution cost; [test-execution-budget](https://github.com/supersovaa/requirement-driven-testing/blob/main/skills/execution/SKILL.md) owns the need and execution budget for complete trials.

Use the owning planning workflow for work boundaries and real prerequisite dependencies. Measurement convenience alone does not establish a prerequisite result. Requirements and design own new performance guarantees; implementation and review workflows own changes, verification, and acceptance.
