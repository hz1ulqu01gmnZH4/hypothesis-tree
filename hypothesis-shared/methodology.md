# Methodology Reference

## Platt's Strong Inference (1964)
The "conditional inductive tree" — science progresses like a decision tree with experiments as branching points. Steps:
1. Devise alternative hypotheses (multiple, competing)
2. Design crucial experiment with alternative outcomes
3. Each outcome excludes one or more hypotheses
4. Recurse: make sub-hypotheses on survivors
5. Repeat until convergence

Key insight: ALWAYS maintain multiple competing hypotheses to avoid confirmation bias.

## Tree of Thoughts (Yao et al., NeurIPS 2023)
Generalizes Chain of Thought into a tree:
- Each "thought" is an intermediate reasoning step
- BFS or DFS explores the thought tree
- LLM both generates AND evaluates thoughts
- Supports lookahead and backtracking
- 74% success on Game of 24 vs 4% with basic CoT

## Graph of Thoughts (Besta et al., AAAI 2024)
Extends ToT by allowing thoughts to form a directed graph, not just a tree:
- Thoughts can be **combined** (aggregation from multiple branches)
- Thoughts can be **refined** via feedback loops
- Branches can **cross-pollinate** — evidence from one branch informs another
- Overcomes ToT's limitation that branches are isolated
- Paper: https://arxiv.org/abs/2308.09687

## SciAgents Pattern (Multi-Agent Roles)
Specialized agents produce higher quality than a single generalist:
- **Generator** (divergent): produces candidate hypotheses, creative exploration
- **Critic** (convergent): finds weaknesses, biases, logical gaps
- **Synthesizer** (integrative): merges findings across branches, identifies patterns
- From: SciAgents (2024) — multi-agent + knowledge graph for scientific discovery
- Paper: https://arxiv.org/abs/2409.05556

## Recursive Decomposition of Logical Thoughts (RDoLT)
Three innovations (JAIR, 2025):
1. Recursively breaks complex reasoning into sub-tasks of progressive complexity
2. Uses selection/scoring to prioritize promising thoughts
3. Knowledge propagation module tracks strong vs weak reasoning paths
- Paper: https://arxiv.org/abs/2501.02026

## MECE Decomposition (McKinsey)
Sub-hypotheses should be:
- **Mutually Exclusive**: no overlap between branches
- **Collectively Exhaustive**: cover all possibilities
- Not always achievable for novel/open questions, but aim for it

## Node Status Tags
| Status | Meaning | Action |
|--------|---------|--------|
| SUPPORTED | Evidence found for this hypothesis | Leaf node (confirmed) |
| REFUTED | Counter-evidence found | Leaf node (pruned) |
| UNCERTAIN | Insufficient evidence either way | Branch candidate |
| NOVEL | Interesting unexplored angle | Priority branch |

## Seed Generation Techniques
Improve Phase 1 diversity beyond single-pass generation:
- **Multi-persona**: generate from empiricist, contrarian, adjacent-field perspectives
- **Analogical prompting** (Yasunaga et al., ICLR 2024): identify analogous problems from other domains first
- **Self-consistency** (Wang et al., 2022): sample multiple hypothesis sets, merge/deduplicate

## Convergence Criteria
Stop branching when:
- Strong evidence confirms or refutes
- Too speculative to decompose further
- Depth limit reached (default: 4)
- Sub-hypotheses converge to same conclusion
- Critic finds no further weaknesses to probe

## Key References
- Platt (1964): https://pages.cs.wisc.edu/~markhill/science64_strong_inference.pdf
- Tree of Thoughts: https://arxiv.org/abs/2305.10601
- Graph of Thoughts: https://arxiv.org/abs/2308.09687
- RDoLT: https://arxiv.org/abs/2501.02026
- SciAgents: https://arxiv.org/abs/2409.05556
- Hypothesis Generation Survey: https://arxiv.org/abs/2504.05496
- Agentic AI for Science (ICLR 2025): https://arxiv.org/abs/2503.08979
