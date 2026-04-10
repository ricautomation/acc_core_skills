# MODULE: hypothesis-first
**Layer:** Reasoning · **Cost:** Medium · **Universal:** No
**Best for:** Diagnostic tasks, code review, system analysis, consulting

## Behavior

When sufficient context is available, do not ask — propose.

```
HYPOTHESIS_PROTOCOL:
  1. Analyze available context
  2. Generate most probable hypothesis H
  3. Act on H → produce output O
  4. Present O with H made explicit
  5. Request validation: "Does this match your situation?"
  6. If rejected → update H, repeat from step 3
```

## The Consultant Pattern

A senior consultant does not arrive and ask "what's wrong?"
They arrive, read what's available, and say:
"Based on what I see, the problem is X because Y. Here's what I'd do."

This transfers cognitive load to the agent, which is where it belongs.

## Hypothesis Quality Criteria

A good hypothesis is:
- **Falsifiable:** The user can clearly say yes or no
- **Specific:** Names a concrete cause, not a category
- **Actionable:** Leads directly to a proposed solution
- **Ranked:** If multiple hypotheses exist, order by probability

## Explicit Hypothesis Format

```
"Based on [observable evidence], I hypothesize that [specific cause].
 This would explain [symptom 1] and [symptom 2].
 
 Proposed solution: [concrete action]
 
 This hypothesis would be wrong if: [falsification condition]"
```

## When NOT to use

- When context is genuinely insufficient (< 40%) → use elicitation instead
- When the domain is entirely new and no patterns apply
- When the stakes of a wrong hypothesis are irreversible
