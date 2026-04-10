# THINKING CORPUS — MODULE INDEX

Complete catalog of available thinking modules with selection criteria.

---

## CORE MODULES
*Universal applicability. Low cognitive overhead. Include by default in most skills.*

| Module | File | When to include |
|--------|------|----------------|
| **zero-hallucination** | `core-zero-hallucination.md` | Any skill that makes factual claims, technical recommendations, or domain-specific assertions |
| **elicitation-minimal** | `core-elicitation.md` | Any skill that receives under-specified inputs or must clarify intent before executing |
| **ockham** | `core-ockham.md` | Any skill that generates solutions, architectures, code, or plans |
| **state-vector** | `core-state-vector.md` | Any skill used in multi-turn conversations with complex, evolving context |

---

## REASONING MODULES
*Domain-specific reasoning patterns. Include when the skill's primary task matches.*

| Module | File | When to include |
|--------|------|----------------|
| **hypothesis-first** | `reasoning-hypothesis-first.md` | Diagnostic skills, code review, system analysis, consulting — where acting beats asking |
| **causal-chain** | `reasoning-causal-chain.md` | Debugging, root cause analysis, architectural decisions — where symptom ≠ cause |
| **constraint-map** | `reasoning-constraint-map.md` | System design, planning, architecture — where solution space must be bounded first |

---

## OUTPUT MODULES
*Control how results are formatted and communicated.*

| Module | File | When to include |
|--------|------|----------------|
| **density-max** | `output-density-max.md` | Any skill where verbosity is a risk — technical skills, expert users, high-frequency use |
| **scannable** | `output-scannable.md` | Skills producing comparisons, multi-step guides, technical documentation |
| **uncertainty-map** | `output-uncertainty-map.md` | Skills informing high-stakes decisions, financial/legal/medical adjacent domains |

---

## RECOMMENDED COMBINATIONS BY SKILL TYPE

| Skill type | Recommended modules |
|-----------|-------------------|
| **Code generation / review** | zero-hallucination + ockham + causal-chain + density-max |
| **System architecture** | zero-hallucination + ockham + constraint-map + state-vector + scannable |
| **Consulting / analysis** | hypothesis-first + causal-chain + state-vector + uncertainty-map |
| **Domain assistant (HIDROS, solar, etc.)** | zero-hallucination + elicitation-minimal + constraint-map + density-max |
| **Multi-agent orchestration** | state-vector + hypothesis-first + zero-hallucination + causal-chain |
| **Creative / generative** | ockham + density-max |
| **High-stakes decisions** | zero-hallucination + constraint-map + uncertainty-map + state-vector |

---

## INJECTION PATTERN

Add to target SKILL.md after the YAML frontmatter, before domain content:

```markdown
## THINKING MODULES ACTIVE
<!-- Read these reference files before executing any task -->
- [`zero-hallucination`](references/core-zero-hallucination.md)
- [`elicitation-minimal`](references/core-elicitation.md)
- [`ockham`](references/core-ockham.md)
```

Then copy the relevant `.md` files into the target skill's `references/` folder.
