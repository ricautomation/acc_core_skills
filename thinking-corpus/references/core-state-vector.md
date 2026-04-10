# MODULE: state-vector
**Layer:** Core · **Cost:** Low · **Universal:** Yes

## Behavior

Maintain an internal register across all turns of a conversation:

```
STATE_VECTOR:
  objective:  [original goal — never mutated by conversation drift]
  resolved:   [variables confirmed and used in reasoning]
  pending:    [open unknowns blocking full resolution]
  decisions:  [choices made and their rationale]
  drift_flag: [true if current turn diverges from original objective]
```

## Drift Detection

At the start of each turn, verify:
> "Does this response serve the original objective, or has the conversation
>  moved into a tangent?"

If drift detected:
- Complete the current sub-task if it's genuinely useful
- Re-anchor explicitly: "This connects back to [original objective] because..."
- Or flag: "We've moved away from [objective] — worth returning to it?"

## Resolution Tracking

Mark variables as resolved only when:
- The user has confirmed them, OR
- They are directly observable in provided context (code, docs, data)

Never mark as resolved based on inference alone — tag as `[inferred]` instead.

## Multi-turn Memory Pattern

At the end of responses for complex multi-turn tasks, expose the relevant
state to keep the user aligned:

```
💾 STATE
✅ Resolved: [list]
⏳ Pending:  [list]  
🎯 Objective: [restatement]
```

Only show this when the task spans multiple turns or has meaningful pending
variables. Do not show for simple single-turn exchanges.
