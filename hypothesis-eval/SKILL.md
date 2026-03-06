---
name: hypothesis-eval
description: Rigorously evaluate hypotheses using philosophy of science frameworks (Popper, Lakatos, Bayesian, ACH). Use when the user wants to stress-test, evaluate, or compare hypotheses. Accepts a hypothesis, a set of hypotheses, or a path to a hypothesis-tree REPORT.md.
argument-hint: <hypothesis to evaluate, or path to REPORT.md>
allowed-tools: [Bash, Read, Write, Edit, Glob, Grep, Agent, AskUserQuestion, WebSearch, mcp__arxiv-mcp-server__search_arxiv_papers, mcp__claude_ai_bioRxiv__search_preprints, mcp__gemini-cli__ask-gemini, mcp__openrouter__openrouter_chat]
---

# Hypothesis Evaluator

Rigorously evaluate hypotheses using theoretically-grounded frameworks from philosophy of science, intelligence analysis, and AI research.

See [methodology.md](methodology.md) for foundational methods. See [evaluation-framework.md](evaluation-framework.md) for the full scoring rubric and bias checklist.

## Input

$ARGUMENTS

**Detect input type:**
- If a file path (e.g., `~/hypothesis-trees/.../REPORT.md`) → read it, extract top-ranked hypotheses, evaluate them
- If a single hypothesis → evaluate it directly
- If multiple hypotheses → evaluate comparatively using ACH matrix

## Phase 1: Setup & Parse

```bash
EVAL_DIR="$HOME/hypothesis-evals/$(date +%Y%m%d-%H%M)"
mkdir -p "$EVAL_DIR"
```

Parse the input. If from a hypothesis-tree REPORT, extract hypotheses with status SUPPORTED or UNCERTAIN (most worth evaluating). Present them and ask user which to evaluate.

## Phase 2: Multi-Dimensional Scoring

For each hypothesis, score across **4 tiers / 18 dimensions** (see [evaluation-framework.md](evaluation-framework.md)):

**Tier 1 — Epistemic Quality** (Is it good science?)
- Falsifiability, Specificity, Internal Consistency, Evidential Support, Groundedness

**Tier 2 — Explanatory Power** (Does it explain well?)
- Scope, Mechanistic Depth, Unification, Coherence, Simplicity

**Tier 3 — Scientific Productivity** (Will it advance knowledge?)
- Novelty, Progressiveness, Fruitfulness, Discriminability, Feasibility

**Tier 4 — Robustness** (Can it survive scrutiny?)
- Auxiliary Transparency, Bias Resistance, Sensitivity, Replicability

Score each dimension **1-10** with explicit justification. Do NOT score without evidence or reasoning.

## Phase 3: Stress Tests (Parallel Agents)

Launch 3 agents in parallel to attack the hypothesis from different angles:

**Agent 1 — Devil's Advocate**
```
"You are a Devil's Advocate. Your ONLY job is to argue AGAINST this hypothesis:
[HYPOTHESIS]
Find the strongest counter-arguments, counter-evidence, and alternative explanations.
Search for disconfirming evidence (WebSearch). Be ruthless but intellectually honest.
Write to $EVAL_DIR/devils-advocate.md"
```

**Agent 2 — Steelman**
```
"You are a Steelman. Your job is to construct the STRONGEST possible version of this hypothesis:
[HYPOTHESIS]
Fix weaknesses, sharpen predictions, find the best supporting evidence.
Search for confirming evidence (WebSearch). Be generous but not uncritical.
Write to $EVAL_DIR/steelman.md"
```

**Agent 3 — Auxiliary Auditor**
```
"You are an Auxiliary Hypothesis Auditor (Quine-Duhem analysis). For this hypothesis:
[HYPOTHESIS]
1. List ALL auxiliary assumptions this hypothesis depends on
2. Rate each auxiliary: well-established / debatable / speculative
3. For debatable/speculative auxiliaries, find counter-evidence
4. Assess: if this hypothesis were refuted, could it be 'saved' by modifying an auxiliary?
5. Is the hypothesis genuinely testable or protected by ad hoc adjustments?
Write to $EVAL_DIR/auxiliary-audit.md"
```

## Phase 4: ACH Matrix (for multiple hypotheses)

If evaluating 2+ competing hypotheses, build an **Analysis of Competing Hypotheses** matrix:

1. List all evidence collected across agents
2. For each piece of evidence, assess: **consistent (C)**, **inconsistent (I)**, or **neutral (N)** with each hypothesis
3. Calculate **diagnosticity** — evidence that is C with one hypothesis but I with another is highly diagnostic
4. Focus on the **most diagnostic** evidence
5. Rank hypotheses by which has the **least inconsistent evidence** (Heuer's principle)

```
| Evidence              | H1  | H2  | H3  | Diagnosticity |
|----------------------|-----|-----|-----|---------------|
| [evidence 1]         |  C  |  I  |  N  | HIGH          |
| [evidence 2]         |  C  |  C  |  C  | LOW           |
| [evidence 3]         |  I  |  C  |  I  | HIGH          |
| Inconsistent count   |  1  |  1  |  2  |               |
```

## Phase 5: Discriminating Tests

Design **crucial experiments** (Platt) that would distinguish between hypotheses:

For each pair of competing hypotheses:
1. Where do their predictions **diverge most**?
2. What observable outcome would **confirm one and refute the other**?
3. How **feasible** is this test? (thought experiment / literature search / empirical test)
4. What is the **expected information gain**?

Present as:
```
Test 1: [description]
  If result A → supports H1, refutes H2
  If result B → supports H2, refutes H1
  Feasibility: [high/medium/low]
  Information gain: [high/medium/low]
```

## Phase 6: Synthesis & Verdict

Produce and write to `$EVAL_DIR/EVALUATION.md`:

### 1. Scorecard
Full 18-dimension scores per hypothesis, with tier averages.

### 2. Stress Test Summary
Key findings from Devil's Advocate, Steelman, and Auxiliary Audit.

### 3. ACH Results (if multiple hypotheses)
Matrix, diagnosticity analysis, ranking.

### 4. Discriminating Tests
Proposed crucial experiments with expected outcomes.

### 5. Verdict
- **Overall assessment**: Strong / Promising / Weak / Fatally flawed
- **Key strength**: What's best about this hypothesis
- **Key vulnerability**: What could most easily refute it
- **Recommended action**: Accept (provisionally) / Refine (specify how) / Test (specify what) / Abandon (explain why)
- **Lakatos assessment**: Progressive or degenerating problem-shift?

### 6. Bias Check
Flag any biases detected in the evaluation itself (see [evaluation-framework.md](evaluation-framework.md) bias checklist).

Report location to user: `Evaluation saved to: $EVAL_DIR/`

## Rules

- **Use Agent tool** for all parallel workers
- **Disconfirmation focus** — weight evidence AGAINST hypotheses more heavily (Popper/ACH)
- **No isolated evaluation** — always evaluate against alternatives (Chamberlin)
- **Explicit auxiliaries** — list background assumptions (Quine-Duhem)
- **Calibrated scores** — justify every score, prefer uncertainty over false precision
- **Cite sources** — every evidence claim needs a URL
- **Diagnosticity over volume** — one diagnostic piece of evidence > ten non-diagnostic ones
- **Intellectual honesty** — a hypothesis can be novel AND fatally flawed
