---
name: thinking-corpus
description: >
  A library of cognitive thinking modules that can be injected into any other skill
  to improve its reasoning quality. Use this skill whenever the user wants to improve
  how another skill thinks — not what it knows, but how it reasons, handles uncertainty,
  elicits context, avoids hallucination, or structures its output.

  Trigger when the user says: "mejora esta skill", "añade mejor razonamiento a X",
  "inyecta el corpus de pensamiento", "make this skill think better", "improve the
  reasoning of", "add thinking modules to", or any phrase implying they want to
  upgrade the cognitive behavior of an existing skill.

  Also trigger when reviewing a skill that produces verbose, hallucinated, over-engineered,
  or context-blind outputs — even if the user doesn't explicitly ask for thinking modules.
  When in doubt about whether this skill applies — it does.
---

# THINKING CORPUS
## Cognitive Module Injector for Skills

This skill contains a library of reusable thinking modules and a protocol for
analyzing any target skill and injecting the most relevant modules into it.

**What this changes:** Not what a skill knows — how it thinks.

---

## AVAILABLE MODULES

Read [`references/modules-index.md`](references/modules-index.md) for the full
catalog with selection criteria and recommended combinations.

Quick reference:

| Layer | Modules |
|-------|---------|
| **Core** | zero-hallucination · elicitation-minimal · ockham · state-vector |
| **Reasoning** | hypothesis-first · causal-chain · constraint-map |
| **Output** | density-max · scannable · uncertainty-map |

---

## IMPROVEMENT PROTOCOL

When asked to improve a target skill, execute these steps in order.

### STEP 1 — Read the Target Skill

```
view /path/to/target-skill/SKILL.md
```

If the skill has a `references/` directory, scan it too.

### STEP 2 — Diagnose Cognitive Gaps

Analyze the skill against these failure modes:

| Failure mode | Signal in SKILL.md | Fix |
|-------------|-------------------|-----|
| **Hallucination risk** | Makes domain claims without uncertainty markers | `zero-hallucination` |
| **Context blindness** | Executes without verifying input completeness | `elicitation-minimal` |
| **Over-engineering** | Generates maximal solutions by default | `ockham` |
| **Objective drift** | No mechanism to track goal across turns | `state-vector` |
| **Passive execution** | Asks before acting even with sufficient context | `hypothesis-first` |
| **Symptom-level fixes** | Addresses outputs, not causes | `causal-chain` |
| **Unconstrained design** | Generates solutions before mapping limits | `constraint-map` |
| **Verbose output** | No explicit density/filler rules | `density-max` |
| **Unstructured output** | No format guidance for complex responses | `scannable` |
| **Silent assumptions** | High-stakes domain without confidence signaling | `uncertainty-map` |

### STEP 3 — Select Modules

From the diagnosis, select only the modules that address real gaps.
**Do not inject all modules** — select the minimum set that eliminates
the identified failure modes.

Apply the selection criteria from `references/modules-index.md`.

### STEP 4 — Copy Module Files

Copy selected module files into the target skill's `references/` directory:

```bash
# Example: improving acc-typescript-engineer
cp /path/to/thinking-corpus/references/core-zero-hallucination.md \
   /path/to/acc-typescript-engineer/references/

cp /path/to/thinking-corpus/references/core-ockham.md \
   /path/to/acc-typescript-engineer/references/

cp /path/to/thinking-corpus/references/reasoning-causal-chain.md \
   /path/to/acc-typescript-engineer/references/
```

### STEP 5 — Inject the Activation Block

Add the following block to the target SKILL.md, immediately after the YAML
frontmatter and before the first section heading:

```markdown
## THINKING MODULES ACTIVE
<!-- These modules define how this skill reasons, not what it knows -->
<!-- Read them before executing any task in this skill -->

| Module | File | Purpose |
|--------|------|---------|
| zero-hallucination | [`references/core-zero-hallucination.md`] | No fabrication |
| ockham | [`references/core-ockham.md`] | Minimum viable solution |
| causal-chain | [`references/reasoning-causal-chain.md`] | Root cause, not symptom |
```

Adapt the table to the actual modules injected.

### STEP 6 — Produce Diagnosis Report

Present to the user:

```
TARGET SKILL: [name]

GAPS IDENTIFIED:
  [failure mode] → [module injected] — [why this gap existed]

MODULES INJECTED: [list]
MODULES SKIPPED: [list with reason]

EXPECTED IMPROVEMENT:
  [concrete behavior change 1]
  [concrete behavior change 2]

FILES MODIFIED:
  [target-skill]/SKILL.md — activation block added
  [target-skill]/references/[module].md — added (N files)
```

---

## USAGE AS STANDALONE CORPUS

This skill can also be used directly — without improving another skill —
as a cognitive layer for the current conversation.

To activate specific modules in the current session, read the relevant
reference files and apply their protocols to all subsequent responses.

**Activation command:**
> "Activa [module-name] para esta conversación"

The modules will apply to all responses until the conversation ends or
the user deactivates them.

---

## DESIGN PRINCIPLES

**Separation of concerns:** Cognitive behavior is separate from domain knowledge.
A skill that knows NestJS deeply can still hallucinate, over-engineer, or miss
context. These are orthogonal problems with orthogonal solutions.

**Minimum injection:** More modules ≠ better thinking. Each module adds
cognitive overhead. Inject only what addresses a real, observed gap.

**Composability:** Modules are designed to be non-conflicting. Any combination
is valid. They operate on different aspects of the reasoning process.

**Portability:** Modules contain no domain knowledge. They are safe to copy
into any skill — TypeScript, Rust, legal, medical, creative — without modification.
