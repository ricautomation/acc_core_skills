# ACC Core Skills

A collection of advanced cognitive architecture skills designed to enhance reasoning quality, logic synthesis, and output fidelity. These skills focus on **how** AI systems think—not what they know—enabling precise, verifiable, and high-fidelity analytical capabilities.

---

## 📋 Overview

`acc_core_skills` is a modular library containing two complementary skills:

1. **[Thinking Corpus](#thinking-corpus)** — A reusable library of cognitive modules that can be injected into any skill to improve its reasoning quality.
2. **[ACC-Thinker](#acc-thinker)** — A high-fidelity logic synthesizer with dual-layer architecture for formal problem decomposition and system design.

Both skills are language-agnostic and domain-agnostic, designed for maximum portability across different problem spaces (technical, analytical, creative, domain-specific).

---

## 🧠 Skills Included

### Thinking Corpus

A **cognitive module injector** that improves how other skills reason, not what they know.

**Use this skill when you want to:**
- Enhance the reasoning quality of existing skills
- Reduce hallucination and improve accuracy
- Add formal constraint mapping to solutions
- Improve output structure and density
- Better handle uncertainty and assumptions

**Core Modules:**
| Category | Modules |
|----------|---------|
| **Core** | zero-hallucination · elicitation-minimal · ockham · state-vector |
| **Reasoning** | hypothesis-first · causal-chain · constraint-map |
| **Output** | density-max · scannable · uncertainty-map |

**How it works:**
1. Analyze a target skill for cognitive gaps
2. Select and copy relevant thinking modules
3. Inject them into the target skill's architecture
4. Transform how the skill reasons without changing its domain knowledge

📖 **[Read the Thinking Corpus SKILL.md](thinking-corpus/SKILL.md)** for detailed improvement protocols and module descriptions.

---

### ACC-Thinker (V.3.0)

A **high-fidelity logic synthesizer** that operates through a dual-layer cognitive architecture:
- **Layer I — ACC-Runtime V.2.0**: Internal formal verification, K-CORE mapping, execution protocols
- **Layer II — Human Interface**: Maximum-density output with uncertainty signaling

**Use this skill when you need:**
- Deep analytical reasoning and formal problem decomposition
- System architecture and design decisions
- Complex multi-step logic verification
- Root-cause analysis (not symptom treatment)
- Zero-hallucination responses with explicit assumptions

**Active Thinking Modules (9 total):**
- `zero-hallucination` — Source-checked factual claims
- `elicitation-minimal` — Progressive entropy reduction
- `ockham` — Minimum viable solutions
- `state-vector` — Drift detection across turns
- `hypothesis-first` — Act on 40%+ context
- `causal-chain` — Solve at root cause, not symptom
- `constraint-map` — Hard/soft/assumed/excluded classification
- `density-max` — Front-loaded, filler-free output
- `uncertainty-map` — Explicit assumption signaling

**Architecture:**
```
INPUT → ACC-RUNTIME (K-CORE MAP, Execution Protocol, State Vector) 
      → HUMAN INTERFACE (Density-Max, Uncertainty Signaling) → OUTPUT
```

📖 **[Read the ACC-Thinker SKILL.md](acc-thinker/SKILL.md)** for the complete specification.

---

## 🚀 Quick Start

### For Individual Use

```bash
# Clone or navigate to this repository
cd acc_core_skills

# View available skills
ls -la
# acc-thinker/     <- High-fidelity logic synthesizer
# thinking-corpus/ <- Cognitive module library
```

### Activating Thinking-Corpus

To improve an existing skill:

1. **Read the target skill's SKILL.md**
2. **Diagnose cognitive gaps** using the failure-mode table in [thinking-corpus/SKILL.md](thinking-corpus/SKILL.md)
3. **Select modules** from `references/modules-index.md`
4. **Copy modules** into target skill's `references/` directory
5. **Inject activation block** into target SKILL.md
6. **Generate diagnosis report** documenting what improved and why

### Activating ACC-Thinker

Use ACC-Thinker when:
- You need verified, zero-hallucination reasoning
- Your problem requires formal constraint analysis
- You're doing root-cause analysis or system design
- Precision matters more than speed
- You need explicit uncertainty and assumption signaling

Simply invoke: "Activate ACC-Thinker" or reference it directly in your query.

---

## 📁 Directory Structure

```
acc_core_skills/
├── thinking-corpus/
│   ├── SKILL.md                          # Cognitive module injector spec
│   └── references/                       # Reusable thinking modules
│       ├── core-*.md                     # Core cognitive modules
│       ├── reasoning-*.md                # Logic & reasoning modules
│       ├── output-*.md                   # Output formatting modules
│       └── modules-index.md              # Complete module catalog
│
├── acc-thinker/
│   ├── SKILL.md                          # High-fidelity logic synthesizer spec
│   └── references/                       # Injected thinking modules (9 total)
│       ├── core-*.md
│       ├── reasoning-*.md
│       └── output-*.md
│
└── README.md                             # This file
```

---

## 🎯 Core Principles

### 1. **Separation of Concerns**
Cognitive behavior is orthogonal to domain knowledge. A skill can be an expert in TypeScript yet still hallucinate, over-engineer, or miss context. These problems have separate solutions.

### 2. **Minimum Injection**
More modules ≠ better thinking. Each module adds cognitive overhead. Inject only what addresses real, observed gaps.

### 3. **Composability**
All modules are designed to be non-conflicting and can be combined in any valid arrangement. They operate on different aspects of the reasoning process.

### 4. **Portability**
Modules contain no domain knowledge. They're safe to copy into any skill—technical, analytical, legal, medical, creative—without modification.

### 5. **Fidelity-First**
Output is a direct projection of internal analysis. No new claims or filler introduced at output time.

---

## 🔍 When to Use Each Skill

| Scenario | Use Thinking-Corpus | Use ACC-Thinker |
|----------|-------------------|-----------------|
| Improve another skill's reasoning | ✓ | |
| Need formal problem decomposition | | ✓ |
| Reduce hallucination in domain-specific work | ✓ | ✓ |
| System architecture or design decisions | | ✓ |
| Root-cause analysis | | ✓ |
| Complex multi-turn reasoning | | ✓ |
| Want zero-hallucination output | | ✓ |
| Need explicit uncertainty signaling | | ✓ |

---


---

## 📚 Module Reference

### Core Modules
- **zero-hallucination** — SOURCE_CHECK every factual claim; never fill gaps with averages
- **elicitation-minimal** — Progressive entropy reduction; ask one high-entropy question
- **ockham** — Simplest solution meeting constraints; complexity only when justified
- **state-vector** — Track objective, resolved/pending variables, decisions, drift

### Reasoning Modules
- **hypothesis-first** — Propose solutions when context ≥40%; flag assumptions
- **causal-chain** — Trace observable symptoms to root cause; solve there, not at symptom level
- **constraint-map** — Classify constraints as hard/soft/assumed/excluded before designing

### Output Modules
- **density-max** — Front-load answers, zero filler, calibrated length
- **scannable** — Structured, discoverable output; no nested complexity
- **uncertainty-map** — Surface assumptions and confidence levels explicitly

For detailed specs: see [thinking-corpus/references/modules-index.md](thinking-corpus/references/modules-index.md)

---

## 🔄 Workflow Examples

### Example 1: Improving a TypeScript Engineering Skill

```markdown
1. Read target-skill/SKILL.md
2. Identify gaps: verbose output, context-blind execution, no constraint analysis
3. Select modules: density-max, elicitation-minimal, constraint-map
4. Copy modules to target-skill/references/
5. Add activation block to target-skill/SKILL.md
6. Document: "Added 3 modules → [improvements]"
```

### Example 2: Using ACC-Thinker for Architecture Review

```markdown
ACTIVATE ACC-THINKER
Q: Design a caching strategy for a high-traffic API

→ K-CORE MAP: Domain, Logic (causal-chain), Constraints
→ Constraint classification: Hard (sub-100ms latency), Soft (cost), Assumed (traffic pattern)
→ Hypothesis-first: Propose solution with falsification conditions
→ Uncertainty-map: Surface assumptions (traffic pattern inference, framework choice)
```

---

## 🛠 Integration & Sharing

### As a Library
- Copy individual modules from `references/` into your skills
- Reference modules by path in your SKILL.md files
- Use the improvement protocol from thinking-corpus/SKILL.md

### As a Complete Package
- Fork or clone this repository
- Reference it as a dependency in your skill library
- Use both thinking-corpus and acc-thinker as foundational skills

### Documentation
- Each skill has a complete SKILL.md specification
- Each module has detailed implementation guidance
- The modules-index.md provides selection criteria and combinations

---

## 📖 Documentation

- **[thinking-corpus/SKILL.md](thinking-corpus/SKILL.md)** — Cognitive module injector specification and protocols
- **[thinking-corpus/references/modules-index.md](thinking-corpus/references/modules-index.md)** — Complete module catalog with selection criteria
- **[acc-thinker/SKILL.md](acc-thinker/SKILL.md)** — High-fidelity logic synthesizer specification and architecture

Each referenced module includes detailed implementation guidance, use cases, and examples.

---

## 🤖 Language Models

These skills were developed and tested with:
- **Claude** (Anthropic) — Primary development and testing
- **Gemini** (Google) — Compatibility and performance testing
- **MiniMax** — Cross-platform validation

The skills are model-agnostic and work with any capable LLM that supports:
- Extended reasoning and multi-step logic
- Constraint-based problem solving
- Formal specification adherence

---

## 🎓 Key Concepts

### K-CORE MAP
A three-axis framework for formal problem analysis:
- **D (Domain)** — Semantic context and actors
- **L (Logic)** — Functional operators and causal chains
- **C (Constraints)** — System boundaries (hard/soft/assumed/excluded)

### Hypothesis-First Protocol
When context ≥40%, propose solutions rather than ask. Format:
```
"Based on [evidence], I hypothesize [cause].
 This explains [symptom]. Solution: [action].
 This hypothesis fails if: [falsification condition]."
```

### SOURCE_CHECK Protocol
Every factual claim must have a source:
- Present in input → [input]
- Verified knowledge → [verified]
- Inferred from context → [inferred] + warning flag
- None of the above → SYSTEM_HALT and declare missing variable

### Constraint Classification
Before designing solutions, map constraints:
- **Hard** — Non-negotiable, eliminate solution classes
- **Soft** — Rank solutions within valid space
- **Assumed** — Inferred, not stated; flag with warning
- **Excluded** — Already tried or ruled out with reason

---

## 🚀 Best Practices

1. **Diagnose before injecting** — Analyze target skill's actual gaps; don't inject all modules
2. **Document your selections** — Explain why each module was chosen
3. **Test the results** — Verify that injected modules produce the expected improvements
4. **Keep modules updated** — If you modify a module, propagate updates to all skills using it
5. **Track state in multi-turn conversations** — Use state-vector module in complex reasoning
6. **Surface assumptions early** — Especially in high-stakes analysis

---

## 📝 Version History

### ACC-Thinker
- **V.3.0** — 9 thinking modules injected; progressive elicitation; hypothesis-first; causal-chain formalized
- **V.2.0** — Original dual-layer architecture, K-CORE MAP, binary REJECT

### Thinking Corpus
- Stable module library with composable, non-conflicting designs
- All modules are language- and domain-agnostic

---

## 💡 Use Cases

- **System Architecture** — Use ACC-Thinker for design decisions with constraint mapping
- **Root-Cause Analysis** — Trace symptoms to root causes with causal-chain module
- **Skill Enhancement** — Improve existing skills with thinking-corpus modules
- **High-Fidelity Analysis** — Zero-hallucination responses with explicit assumptions
- **Technical Writing** — Density-max + scannable for structured, readable output
- **Complex Problem Solving** — Multi-turn reasoning with state-vector tracking

---

## ⚖️ License

This project is released under the **[MIT License](LICENSE)** — free to use, modify, and distribute for any purpose.

When using this project, please:
- 📌 Include a copy of the [LICENSE](LICENSE) file
- 📌 Attribute the skills to acc_core_skills
- 📌 Share improvements back to the community (optional but appreciated)

### A Gentle Suggestion

If these skills help your work and you find value in them, consider supporting health and medical research. Organizations like WHO, Médecins Sans Frontières, or local medical research institutions do critical work that benefits everyone.

Not a requirement—just a suggestion. 💚

---

## 🤝 Contributing

To extend or improve this library:

1. Add new thinking modules to `references/` with consistent naming and documentation
2. Update `modules-index.md` with selection criteria and use cases
3. Test modules in combination to ensure composability
4. Document your additions clearly with implementation guidance

---

## 📞 Questions?

Refer to the specific SKILL.md files for each skill. Each contains:
- Complete specification
- Architecture diagrams
- Protocol definitions
- Detailed module explanations
- Implementation examples

**For thinking-corpus module improvements:** See [thinking-corpus/SKILL.md](thinking-corpus/SKILL.md#design-principles)

**For ACC-Thinker usage and configuration:** See [acc-thinker/SKILL.md](acc-thinker/SKILL.md#initialization)

---

**Last Updated:** 2026-04-10  
**Status:** Production Ready  
**Compatibility:** Language-agnostic, domain-agnostic
