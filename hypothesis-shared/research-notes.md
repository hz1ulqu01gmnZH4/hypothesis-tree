# Hypothesis Generation Research Notes

## Core Frameworks Used

### 1. Platt's Strong Inference (1964)
- "Conditional inductive tree" — science as a decision tree with experiments as branching points
- Steps: devise alternative hypotheses → design crucial experiment → exclude hypotheses → make sub-hypotheses → recurse
- Key insight: always maintain MULTIPLE competing hypotheses to avoid confirmation bias
- Paper: https://pages.cs.wisc.edu/~markhill/science64_strong_inference.pdf

### 2. Tree of Thoughts (Yao et al., NeurIPS 2023)
- Generalizes Chain of Thought into tree structure with BFS/DFS exploration
- LLM generates AND evaluates thoughts at each branch
- Supports lookahead and backtracking
- Paper: https://arxiv.org/abs/2305.10601

### 3. Language Agent Tree Search (LATS)
- Dynamic tree-based search where LLM generates new branches
- Combines reasoning + acting + planning in tree structure
- Reference: https://towardsdatascience.com/tackle-complex-llm-decision-making-with-language-agent-tree-search-lats-gpt4-o-0bc648c46ea4/

### 4. Multi-Agent ToT Validator (2024)
- Multiple agents exploring and validating different branches
- Paper: https://arxiv.org/html/2409.11527v2

### 5. Agentic AI for Scientific Discovery (ICLR 2025)
- Multi-agent decomposition for hypothesis generation
- Iterative refinement: literature review → hypothesis → experiment → analysis → loop
- Survey: https://arxiv.org/html/2503.08979v1

### 5. Graph of Thoughts (Besta et al., AAAI 2024)
- Extends ToT: thoughts form a directed graph, not just tree
- Branches can merge, cross-pollinate, refine via feedback loops
- Paper: https://arxiv.org/abs/2308.09687

### 6. SciAgents (2024)
- Multi-agent + knowledge graph for scientific discovery
- Specialized roles: Ontologist, Scientist, Critic
- Paper: https://arxiv.org/abs/2409.05556

### 7. RDoLT - Recursive Decomposition of Logical Thoughts (JAIR 2025)
- Progressive complexity decomposition with scoring/selection
- Knowledge propagation tracking strong/weak paths
- Paper: https://arxiv.org/abs/2501.02026

### 8. Key Survey
- "A Survey on Hypothesis Generation for Scientific Discovery in the Era of LLMs" (April 2025)
- Paper: https://arxiv.org/abs/2504.05496

## Design Decisions for the Skill
- Max 4 depth levels by default (prevents infinite recursion)
- Convergence criteria: SUPPORTED, REFUTED, UNCERTAIN, NOVEL status tags
- NOVEL + UNCERTAIN branches get priority for deeper exploration
- Evidence-first: workers must search before rating hypotheses
- MECE decomposition preferred but not always possible for novel questions
- Cross-pollination phase (GoT): check for cross-branch connections after each wave
- Critic pass (SciAgents): dedicated opus agent checks for biases and gaps
- Optional research sweep (Phase 2.5): 4 parallel scouts search literature, landscape, contrarian, adjacent fields
- Live research feeder (Phase 4.5): runs alongside deeper waves to feed evidence to next wave
- Research → Explore → Research loop for iteratively better-grounded hypotheses
- Phase 9 saves persistent archive to ~/hypothesis-trees/ with REPORT.md + tree.json
- Full phases: Seed → Setup → [Research] → Explore → Monitor → [Feed] → Cross-pollinate → Critique → Recurse → Synthesize → Save
