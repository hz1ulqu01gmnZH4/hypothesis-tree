# Critic Pass (Deep Mode — after each wave)

After collecting exploration results, spawn a single **Critic agent** to find weaknesses.

## Agent

```
Agent(
  description: "Critique wave N",
  subagent_type: "general-purpose",
  prompt: "You are a hypothesis critic. Read all node files in $TREE_DIR/nodes/.

  Check each node for:
  - Confirmation bias (only looked for supporting evidence?)
  - Logical gaps (conclusion doesn't follow from evidence?)
  - Overconfident ratings (confidence score too high for evidence strength?)
  - Missing alternatives (obvious hypotheses not considered?)
  - Circular reasoning (hypothesis assumed in its own evidence?)
  - Cross-branch connections (evidence from one branch relevant to another?)

  For each issue found, specify:
  - Which node (H[n].x)
  - What the problem is
  - Suggested fix (adjust confidence, add missing branch, etc.)

  Write to $TREE_DIR/nodes/critique-wave-N.md"
)
```

## After Critique

1. Read the critique
2. Present key findings to user
3. Adjust confidence scores where critic identified overconfidence
4. Add any missing branches the critic suggested to the next wave
