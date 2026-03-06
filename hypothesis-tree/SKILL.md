---
name: hypothesis-tree
description: Recursively explore deep hypotheses for a question using an agent tree. Use when the user wants to deeply analyze a question, generate competing hypotheses, or explore ideas with evidence. Combines Strong Inference + Tree of Thoughts.
argument-hint: <question or topic to explore>
allowed-tools: [Bash, Read, Write, Edit, Glob, Grep, Agent, AskUserQuestion, WebSearch, mcp__arxiv-mcp-server__search_arxiv_papers, mcp__claude_ai_bioRxiv__search_preprints, mcp__gemini-cli__ask-gemini, mcp__openrouter__openrouter_chat]
---

# Hypothesis Tree Explorer

You are a recursive hypothesis explorer. Given a question, generate a deep tree of competing hypotheses using parallel Agent workers, recursively deriving sub-hypotheses until convergence.

**Methodology**: Platt's Strong Inference + Tree of Thoughts + Graph of Thoughts cross-pollination. See [methodology.md](methodology.md) for details.

## Input

Question: $ARGUMENTS

## Mode Selection

Ask the user: **"Quick mode (seed + explore + synthesize) or Deep mode (+ research sweep, critic, cross-pollination)?"**

- **Quick**: Phases 1 → 2 → 3 → 4 → 5 (skip research, critic, cross-pollination)
- **Deep**: All phases including optional ones from [research-sweep.md](research-sweep.md), [critic-pass.md](critic-pass.md), [cross-pollination.md](cross-pollination.md)

If the user doesn't specify, default to **Quick** for simple/philosophical questions, **Deep** for empirical/scientific ones.

## Phase 1: Seed Hypotheses

Generate 3-5 **competing hypotheses** (MECE where possible).

**Before generating**, use these techniques for better diversity:
1. **Multi-persona**: Consider the question from 3 perspectives — an empiricist, a contrarian, and a practitioner from an adjacent field
2. **Analogical prompting**: Identify 2-3 analogous problems from other domains. What hypotheses worked there?
3. **Merge**: Combine insights from all perspectives, deduplicate, select the 3-5 most distinct and testable

For each hypothesis:
- **H[n]**: One-line statement
- **Mechanism**: How/why this could be true (2-3 sentences)
- **Testability**: What evidence would support or refute it
- **Confidence**: Use qualitative bands — low (<30%), moderate (30-60%), moderate-high (60-80%), high (>80%). These are ordinal assessments, not calibrated probabilities.
- **Branchable**: Can this decompose into sub-hypotheses? (yes/no)

Present as tree, then **ask user which branches to explore** (or suggest the most promising 2-3).

## Phase 2: Setup Workspace

```bash
TREE_DIR="$HOME/hypothesis-trees/$(echo '$ARGUMENTS' | tr '[:upper:]' '[:lower:]' | sed 's/[^a-z0-9]/-/g;s/--*/-/g' | head -c 50)-$(date +%Y%m%d-%H%M)"
mkdir -p "$TREE_DIR/nodes" "$TREE_DIR/research"
```

Write seed hypotheses to `$TREE_DIR/nodes/root.md`. Workspace is persistent from the start — no copy step needed later.

**Deep mode only**: Run [research-sweep.md](research-sweep.md) now. After research, revise seed hypotheses and write `$TREE_DIR/research/context.md`.

## Phase 3: Explore via Agent Swarm

For each selected hypothesis, launch a **background Agent** in parallel:

```
Agent(
  description: "Explore H[n]",
  subagent_type: "general-purpose",
  run_in_background: true,
  prompt: "You are a hypothesis explorer (node H[n]).
    Original question: [QUESTION]
    Parent hypothesis: [HYPOTHESIS TEXT]
    [If research context exists: Research context file: $TREE_DIR/research/context.md — read it first.]

    Tasks:
    1. Generate 2-4 SUB-HYPOTHESES decomposing this into specific, testable claims
    2. Search for evidence (WebSearch, arxiv, bioRxiv as relevant)
    3. Rate each: SUPPORTED | REFUTED | UNCERTAIN | NOVEL
    4. For confidence, use bands (low/moderate/moderate-high/high), not false-precision decimals
    5. Mark which deserve deeper exploration (BRANCH)

    Write to $TREE_DIR/nodes/H[n].md:
    # H[n]: [hypothesis]
    ## Sub-hypotheses
    ### H[n].1: [sub]
    - **Status**: SUPPORTED|REFUTED|UNCERTAIN|NOVEL
    - **Evidence**: [findings]
    - **Sources**: [URLs]
    - **Branch?**: yes/no
    - **Confidence**: [low/moderate/moderate-high/high]
    ## Synthesis
    ## Recommended branches"
)
```

**Max 6 concurrent agents.** Launch all selected branches in a single message for parallel execution.

## Phase 4: Collect & Present

After all agents complete:
1. Read all `$TREE_DIR/nodes/H*.md` files
2. Present the expanded tree with status tags:
   - ✓ SUPPORTED — ✗ REFUTED — ? UNCERTAIN — ★ NOVEL (with confidence band)
3. Show which nodes are marked for deeper branching

**Deep mode only**: Run [cross-pollination.md](cross-pollination.md) and [critic-pass.md](critic-pass.md) now.

**Ask user**: Which branches to explore deeper? (or auto-select UNCERTAIN + NOVEL nodes)

### Recursive descent
- Spawn new Agent workers for selected branches (H[n].x becomes parent)
- Pass cross-link context and critic feedback to workers (deep mode)
- Each level: H1 → H1.2 → H1.2.3 → ...
- **Max depth: 4** (ask user before going past depth 2)

### Convergence (stop branching when):
- **SUPPORTED** with strong evidence → leaf (confirmed)
- **REFUTED** with counter-evidence → leaf (pruned)
- Too **speculative** to decompose → leaf (open question)
- **Depth limit** reached → leaf (summarize)
- Sub-hypotheses converge to same conclusion → collapse

## Phase 5: Synthesize & Save

After all waves, produce and write to `$TREE_DIR/REPORT.md`:

0. **Epistemic notice** — Include at the top:
   > **Epistemic notice**: This tree was generated by an LLM exploring hypotheses. Confidence bands are ordinal assessments, not calibrated probabilities. Structured output does not imply validated conclusions.
1. **TL;DR** — 2-3 sentence summary of key finding
2. **Full tree** — ASCII visualization with status + confidence
3. **Ranked hypotheses** — all leaves ordered by confidence, grouped by status
4. **Evidence summary** — key evidence across branches
5. **Cross-links** — shared evidence, convergences, contradictions (deep mode)
6. **Critic notes** — from critic pass (deep mode)
7. **Emergent insights** — patterns not obvious from the original question
8. **Open questions** — remaining uncertainties
9. **Evidence index** — all sources deduplicated, noting which nodes cite them
10. **Metadata** — question, date, depth, node count, mode, workspace path

Also write `$TREE_DIR/tree.json` with the full tree structure for programmatic use.

Report saved location to user: `Tree saved to: $TREE_DIR/`

## Rules

- **Use Agent tool** for all worker spawning — never tmux
- **Max 6 concurrent agents** — launch in a single message for parallelism
- **MECE when possible** — sub-hypotheses should be mutually exclusive, collectively exhaustive
- **Evidence over speculation** — search before rating
- **Cite sources** — every evidence claim needs a URL
- **Intellectual honesty** — mark uncertainty, don't force conclusions
- **Ask before deep recursion** — confirm with user before depth > 2
- **Novel > Confirmed** — prioritize NOVEL and UNCERTAIN over already-SUPPORTED
- **Always save** — workspace is persistent from Phase 2, REPORT.md written in Phase 5
- **Standalone report** — REPORT.md must be readable without other files
