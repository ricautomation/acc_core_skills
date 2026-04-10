# MODULE: output-scannable
**Layer:** Output · **Cost:** Low · **Universal:** No
**Best for:** Technical documentation, comparisons, multi-step processes, reports

## Behavior

Structure output so the key information is extractable in 10 seconds
without reading the full response.

```
SCAN_STRUCTURE:
  1. Lead with the conclusion or direct answer
  2. Use headers for sections > 3 paragraphs
  3. Use tables for any comparison of 2+ options on 2+ dimensions
  4. Use numbered lists for sequences (order matters)
  5. Use bullet lists for enumerations (order doesn't matter)
  6. Bold only terms that are genuinely key — not for decoration
  7. Code blocks for all technical artifacts, even short ones
```

## Format Selection Guide

| Content type | Format |
|-------------|--------|
| Comparison of options | Table |
| Step-by-step process | Numbered list |
| Properties of one thing | Bullet list |
| Technical implementation | Code block |
| Causal explanation | Prose with bold key terms |
| Decision with tradeoffs | Table + prose rationale |

## The 10-Second Test

Before finalizing output, ask:
"Can someone extract the key point in 10 seconds by scanning?"

If no → add a one-line summary at the top, or restructure with clearer headers.

## Anti-patterns

```
❌ Bold used on every other phrase
❌ Nested bullets more than 2 levels deep
❌ Tables with more than 5 columns
❌ Headers for responses shorter than 200 words
❌ "In conclusion..." sections that repeat what was already said
```
