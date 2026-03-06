# Evaluation Framework Reference

## Scoring Rubric: 18 Dimensions across 4 Tiers

### Tier 1 — Epistemic Quality (Is it good science?)

| Dimension | 1-3 (Weak) | 4-6 (Moderate) | 7-9 (Strong) | 10 (Exceptional) |
|-----------|-----------|----------------|--------------|-------------------|
| **Falsifiability** | Unfalsifiable, vague | Some testable predictions | Clear, specific falsifiable predictions | Precisely specified conditions for refutation |
| **Specificity** | Vague, could explain anything | Moderately constrained | Precise predictions, narrow scope | Quantitative predictions with error bounds |
| **Internal Consistency** | Contains contradictions | Minor tensions | Logically coherent | Formally consistent, no tensions |
| **Evidential Support** | No evidence, pure speculation | Some indirect evidence | Direct evidence from multiple sources | Strong, replicated, convergent evidence |
| **Groundedness** | No connection to prior work | Loosely connected | Built on established findings | Extends well-established theory |

### Tier 2 — Explanatory Power (Does it explain well?)

| Dimension | 1-3 | 4-6 | 7-9 | 10 |
|-----------|-----|-----|-----|----|
| **Scope** | Explains one observation | Covers a class of phenomena | Explains across domains | Universal scope |
| **Mechanistic Depth** | No mechanism offered | Plausible mechanism sketched | Detailed causal mechanism | Mechanism independently verified |
| **Unification** | Isolated explanation | Connects 2-3 phenomena | Unifies a field | Bridges fields |
| **Coherence** | Conflicts with known facts | Minor tensions with established knowledge | Consistent with known facts | Predicted by broader theory |
| **Simplicity** | Requires many ad hoc assumptions | Moderate complexity | Parsimonious | Elegant, minimal assumptions |

### Tier 3 — Scientific Productivity (Will it advance knowledge?)

| Dimension | 1-3 | 4-6 | 7-9 | 10 |
|-----------|-----|-----|-----|----|
| **Novelty** | Restates known fact | Minor twist on existing idea | Genuinely new prediction/connection | Paradigm-shifting |
| **Progressiveness** | Degenerating (ad hoc saves) | Neutral | Progressive (novel predictions) | Confirmed novel predictions |
| **Fruitfulness** | Dead end | Suggests 1-2 follow-ups | Opens research programme | Spawns entire subfield |
| **Discriminability** | Indistinguishable from alternatives | Some differential predictions | Clear discriminating tests | Already discriminated empirically |
| **Feasibility** | Cannot be tested | Testable in principle | Testable with current methods | Test already designed/underway |

### Tier 4 — Robustness (Can it survive scrutiny?)

| Dimension | 1-3 | 4-6 | 7-9 | 10 |
|-----------|-----|-----|-----|----|
| **Auxiliary Transparency** | Hidden assumptions | Some assumptions stated | Most assumptions explicit | All assumptions explicit + evaluated |
| **Bias Resistance** | Evaluated in isolation, confirmation bias likely | Compared to 1 alternative | Evaluated via ACH against multiple alternatives | Red-teamed, devil's advocate tested |
| **Sensitivity** | Collapses if any assumption wrong | Sensitive to key assumptions | Robust to most assumption changes | Robust under all plausible variations |
| **Replicability** | One-off, not reproducible | Could be replicated in theory | Methodology clear enough to replicate | Already replicated |

## Verdicts

| Overall | Score Range (tier avg) | Meaning |
|---------|----------------------|---------|
| **Strong** | 7-10 | Well-supported, testable, novel, robust |
| **Promising** | 5-7 | Worth pursuing, needs refinement |
| **Weak** | 3-5 | Significant gaps, needs major revision |
| **Fatally flawed** | 1-3 | Unfalsifiable, contradicted, or incoherent |

## Bias Checklist (apply to the evaluation itself)

After scoring, check whether YOUR evaluation fell into these traps:

- [ ] **Confirmation bias**: Did you look harder for supporting than refuting evidence?
- [ ] **Anchoring**: Did the first hypothesis evaluated anchor your scores for the rest?
- [ ] **Availability**: Did you overweight recent/dramatic findings?
- [ ] **Status quo bias**: Did you penalize novel hypotheses for being unfamiliar?
- [ ] **Halo effect**: Did strength in one dimension inflate scores in others?
- [ ] **Bandwagon**: Did you favor the hypothesis with most citations/popularity?
- [ ] **Base rate neglect**: Did you ignore prior probabilities?

If any bias detected, note it in the evaluation and adjust.

## ACH Diagnosticity Guide

Evidence diagnosticity levels:
- **HIGH**: Consistent with one hypothesis, inconsistent with another
- **MEDIUM**: Consistent with one, neutral for others
- **LOW**: Consistent (or inconsistent) with all hypotheses equally

Focus evaluation on HIGH diagnosticity evidence. Non-diagnostic evidence is noise.

## Key Frameworks Referenced

- **Popper**: Falsifiability as demarcation
- **Lakatos**: Progressive vs degenerating research programmes
- **Kuhn**: Five theory-choice values (accuracy, consistency, scope, simplicity, fruitfulness)
- **Lipton (IBE)**: Explanatory virtues (scope, precision, mechanism, unification, simplicity, loveliness)
- **Bayesian**: Prior × likelihood → posterior; Bayes factors for comparison
- **Quine-Duhem**: Hypotheses cannot be tested in isolation; auxiliary assumptions matter
- **Bradford Hill**: Nine viewpoints for causal claims
- **Heuer (ACH)**: Matrix-based, diagnosticity-focused, disconfirmation-oriented
- **Chamberlin**: Multiple working hypotheses prevent confirmation bias
- **Platt**: Strong inference via crucial experiments
- **HARPA**: Testability-driven AI evaluation (specificity, novelty, feasibility, groundedness)
