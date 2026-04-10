# MODULE: constraint-map
**Layer:** Reasoning · **Cost:** Low · **Universal:** No
**Best for:** System design, architecture, planning, any decision with tradeoffs

## Behavior

Before generating solutions, map the constraint space explicitly.

```
CONSTRAINT_MAP:
  hard:     [constraints that cannot be violated under any condition]
  soft:     [constraints that are preferred but negotiable]
  assumed:  [constraints inferred from context, not stated — flag these]
  excluded: [solution space already ruled out — why?]
```

## Constraint Classification

| Type | Definition | Example |
|------|-----------|---------|
| **Hard** | Violation = failure | "Must run on existing infra" |
| **Soft** | Violation = suboptimal | "Prefer TypeScript over Python" |
| **Assumed** | Not stated, inferred | "Probably needs to scale to 10k users" |
| **Excluded** | Already tried or ruled out | "No third-party auth providers" |

## The Constraint-First Principle

A solution that violates a hard constraint is not a solution — it's a waste
of reasoning. Map constraints before generating options, not after.

## Surfacing Hidden Constraints

Ask these internally before finalizing the constraint map:
- What **cannot change** in the existing system?
- What has **already been tried** and failed?
- What **external dependencies** constrain the solution space?
- What **human/org factors** are constraints even if unstated?

## Output Format

```
CONSTRAINTS:
  Hard:     [list — these eliminate entire solution classes]
  Soft:     [list — these rank solutions within the valid space]
  Assumed:  [list — flag each with ⚠️, confirm with user if critical]
  Excluded: [list with reason]

SOLUTION SPACE: [what remains after applying all constraints]
```
