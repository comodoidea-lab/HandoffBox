# Implementation Workflow

English | [日本語](./implementation-flow.ja.md)

This workflow is a standard procedure for builder agents. It is inspired by
implementation-first workflows, but it does not try to reproduce any specific
model's private reasoning.

Use it when an AI agent is asked to implement a feature, fix a bug, build a
prototype, or change UI behavior.

## Position in HandoffBox Relay

| Layer | Role |
|-------|------|
| HandoffBox Issue | Source of truth for facts, decisions, evidence, and approval state |
| HandoffBox Relay | Coordination model for Hermes, agmsg, and worker agents |
| Implementation Workflow | Standard work procedure for builder agents |

The workflow is not evidence by itself. Evidence must be recorded as commits,
pull requests, test output, logs, screenshots, deployments, or Issue comments.

## Before Implementation

Do this before editing files.

1. Read the local context.
   - relevant source files
   - README / AGENTS / project docs
   - package, build, test, or framework configuration
   - existing naming, layout, and style conventions

2. Frame the task.
   - goal
   - non-goals
   - assumptions
   - constraints
   - affected files or components
   - approval boundary

3. Identify edge cases.
   - empty state
   - error state
   - narrow screen or small viewport
   - missing data
   - duplicate action
   - permission or authentication failure

4. Define the verification path.
   - build command
   - test command
   - lint / typecheck command
   - browser or device check
   - screenshot or visual inspection when UI is involved

## During Implementation

Keep the change small and local.

- Prefer repository conventions over new patterns.
- Change configuration first only when required.
- Implement foundation before polish.
- Keep names explicit.
- Avoid broad refactors unless they are necessary for the task.
- Do not hide failures. Preserve useful error output.
- If the task touches data, auth, billing, deployment, destructive operations,
  or existing Issue approval state, stop and ask for human approval.

## After Implementation

Verify before reporting success.

1. Run the relevant checks.
   - tests
   - build
   - lint
   - typecheck
   - preview or local app run

2. Inspect behavior.
   - replay the user flow
   - check the edge cases identified before implementation
   - inspect the actual UI when UI changed
   - compare expected and actual output

3. Fix with tight feedback loops.
   - identify the failing step
   - inspect the exact API or nearby code
   - prefer the smallest local fix
   - rerun the failing check

4. Record evidence.
   - changed files
   - commands run
   - checks passed
   - checks skipped and why
   - screenshots or logs when useful
   - residual risk

## Handoff Fields

When leaving a handoff after implementation work, include:

```md
## Implementation Plan
- Goal:
- Assumptions:
- Constraints:
- Edge cases:
- Verification path:

## Implementation Result
- Changed:
- Verified:
- Failed checks:
- Skipped checks:
- Residual risk:
- Evidence:
```

## Agent Prompt

```text
Use the HandoffBox Implementation Workflow.

Before editing, read the local context and state the goal, assumptions,
constraints, edge cases, and verification path.

Implement the smallest useful change. Follow repository conventions.

After editing, run the relevant checks, inspect behavior, record evidence, and
state any skipped checks or residual risk.

Do not update, close, or change approval state of an existing HandoffBox Issue
without explicit human approval.
```
