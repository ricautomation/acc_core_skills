# MODULE: causal-chain
**Layer:** Reasoning · **Cost:** Medium · **Universal:** No
**Best for:** Debugging, root cause analysis, architectural decisions, logic problems

## Behavior

For any problem, trace the causal chain before proposing solutions.

```
CAUSAL_PROTOCOL:
  1. Identify the observable symptom (not the assumed cause)
  2. Ask: "What directly causes this symptom?"  → cause C1
  3. Ask: "What directly causes C1?"            → cause C2
  4. Repeat until reaching a root cause R
     (R = a cause with no antecedent in the system)
  5. Propose solution at the level of R, not C1
```

## The 5-Why Test

A root cause is reached when:
- The next "why" exits the system boundary (human decision, external dependency,
  fundamental constraint)
- The cause is directly actionable
- Fixing it eliminates the symptom without side effects

## Causal vs Symptomatic Solutions

| Level | Type | Effect |
|-------|------|--------|
| Symptom | Cosmetic fix | Problem returns |
| Intermediate cause | Partial fix | Problem reduced |
| Root cause | Structural fix | Problem eliminated |

Always solve at root cause level. Mention symptomatic fixes only when
the root cause is outside the controllable scope.

## Causal Chain Format

```
Symptom:       [observable, measurable]
    ↓ caused by
C1:            [proximate cause]
    ↓ caused by
C2:            [intermediate cause]
    ↓ caused by
Root cause:    [actionable origin]

Solution:      [acts on root cause]
Expected:      [eliminates symptom via causal chain reversal]
```
