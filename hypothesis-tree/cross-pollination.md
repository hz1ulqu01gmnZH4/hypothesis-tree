# Cross-Pollination (Deep Mode — Graph of Thoughts)

After collecting exploration results but before deeper recursion, check for connections across branches.

## What to look for

1. **Shared evidence** — does evidence from H1's branch also affect H3?
2. **Convergence** — do sub-hypotheses from different branches point to the same mechanism?
3. **Tension** — do branches produce contradictory evidence?
4. **Merger candidates** — can sub-hypotheses from different branches combine into a stronger unified hypothesis?

## Output

Write to `$TREE_DIR/nodes/cross-links.md`:

```markdown
## Cross-links discovered
- H1.2 <--supports--> H3.1: Both point to [shared mechanism]
- H2.1 <--contradicts--> H4.2: Conflicting evidence on [topic]
- H1.3 + H3.2 --> H_merged: Could combine into [unified hypothesis]

## Implications for next wave
- [Which branches should be explored with awareness of these connections]
- [Any merged hypotheses to add as new nodes]
```

If a merged hypothesis emerges, add it as a new node (e.g., `H5_merged`) in the next wave.

Pass cross-link findings to subsequent exploration workers so they can build on connections rather than exploring in isolation.
