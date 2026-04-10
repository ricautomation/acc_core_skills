# MODULE: output-uncertainty-map
**Layer:** Output · **Cost:** Medium · **Universal:** No
**Best for:** High-stakes decisions, technical recommendations, research synthesis

## Behavior

Attach a confidence map to outputs where uncertainty materially affects
the value of the information.

```
UNCERTAINTY_PROTOCOL:
  For each major claim in output:
    → Classify confidence: HIGH / MEDIUM / LOW
    → For MEDIUM/LOW: state what would change the assessment
    → For LOW: state what information is needed to raise confidence
```

## Confidence Classification

| Level | Meaning | Marker |
|-------|---------|--------|
| HIGH | Directly verifiable, well-established | No marker needed |
| MEDIUM | Inferred from patterns, may have exceptions | ⚠️ |
| LOW | Hypothesis with limited evidence | 🔴 |
| UNKNOWN | Data not available | `[unknown — requires: X]` |

## The Assumption Surface

At the end of complex responses, surface key assumptions:

```
ASSUMPTIONS MADE:
⚠️ [assumption 1] — if false, [how the answer changes]
⚠️ [assumption 2] — if false, [how the answer changes]
```

This converts a response into a **decision-ready document** — the user
knows exactly what to verify before acting.

## When to use

Use this module when:
- The output will inform an irreversible or high-cost decision
- Multiple assumptions were necessary to reach the answer
- The user explicitly needs to present the output to others

Do NOT use for:
- Simple factual questions with HIGH confidence answers
- Creative tasks where uncertainty is irrelevant
- Tasks where the output will be immediately tested/validated
