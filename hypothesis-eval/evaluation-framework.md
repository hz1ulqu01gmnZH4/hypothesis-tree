# Evaluation Framework Reference

## Scoring Rubric: 5 Dimensions

Compressed from 18 dimensions to 5 independent factors to eliminate multicollinearity and false precision.

### 1. Testability (Can it be proven wrong?)

Combines: falsifiability, specificity, discriminability, feasibility.

| 1-3 (Weak) | 4-6 (Moderate) | 7-9 (Strong) | 10 (Exceptional) |
|------------|----------------|--------------|-------------------|
| Unfalsifiable, vague, no way to distinguish from alternatives | Some testable predictions, partially distinguishable | Clear falsifiable predictions, discriminating tests identifiable, testable with current methods | Precisely specified refutation conditions, already discriminated empirically |

### 2. Evidence Quality (Is it grounded in reality?)

Combines: evidential support, groundedness, replicability.

| 1-3 | 4-6 | 7-9 | 10 |
|-----|-----|-----|----|
| No evidence, pure speculation, no connection to prior work | Some indirect evidence, loosely connected to literature | Direct evidence from multiple sources, built on established findings, methodology replicable | Strong, replicated, convergent evidence extending well-established theory |

### 3. Explanatory Power (Does it explain well?)

Combines: scope, mechanistic depth, unification, coherence.

| 1-3 | 4-6 | 7-9 | 10 |
|-----|-----|-----|----|
| Explains one observation, no mechanism, isolated, conflicts with known facts | Covers a class of phenomena, plausible mechanism sketched, connects 2-3 phenomena | Explains across domains, detailed causal mechanism, unifies a field, consistent with known facts | Universal scope, mechanism independently verified, bridges fields, predicted by broader theory |

### 4. Productivity (Will it advance knowledge?)

Combines: novelty, progressiveness, fruitfulness.

| 1-3 | 4-6 | 7-9 | 10 |
|-----|-----|-----|----|
| Restates known fact, degenerating (ad hoc saves), dead end | Minor twist on existing idea, neutral, suggests 1-2 follow-ups | Genuinely new prediction, progressive (novel predictions), opens research programme | Paradigm-shifting, confirmed novel predictions, spawns entire subfield |

### 5. Robustness (Can it survive scrutiny?)

Combines: simplicity, auxiliary transparency, sensitivity, bias resistance, internal consistency.

| 1-3 | 4-6 | 7-9 | 10 |
|-----|-----|-----|----|
| Many ad hoc assumptions, hidden auxiliaries, collapses if any assumption wrong, contains contradictions, evaluated in isolation | Moderate complexity, some assumptions stated, sensitive to key assumptions, minor tensions | Parsimonious, most assumptions explicit, robust to most changes, logically coherent, evaluated via ACH | Elegant minimal assumptions, all auxiliaries explicit + evaluated, robust under all variations, formally consistent, red-teamed |

## Verdicts

| Overall | Score Range (avg) | Meaning |
|---------|------------------|---------|
| **Strong** | 7-10 | Well-supported, testable, novel, robust |
| **Promising** | 5-7 | Worth pursuing, needs refinement |
| **Weak** | 3-5 | Significant gaps, needs major revision |
| **Fatally flawed** | 1-3 | Unfalsifiable, contradicted, or incoherent |

## Confidence Bands

Use qualitative bands, not point estimates. LLM-generated scores are ordinal assessments, not calibrated probabilities.

| Band | Range | Meaning |
|------|-------|---------|
| **low** | <30% | Speculative, minimal evidence |
| **moderate** | 30-60% | Some evidence, significant uncertainty |
| **moderate-high** | 60-80% | Good evidence, open questions remain |
| **high** | >80% | Strong convergent evidence |

## Bias Checklist (apply to the evaluation itself)

After scoring, check whether YOUR evaluation fell into these traps:

- [ ] **Confirmation bias**: Did you look harder for supporting than refuting evidence?
- [ ] **Anchoring**: Did the first hypothesis evaluated anchor your scores for the rest?
- [ ] **Halo effect**: Did strength in one dimension inflate scores in others?
- [ ] **Eloquent Consensus Trap**: Does the structured output create a false sense of validated rigor?
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
- **Bayesian**: Prior x likelihood -> posterior; Bayes factors for comparison
- **Quine-Duhem**: Hypotheses cannot be tested in isolation; auxiliary assumptions matter
- **Heuer (ACH)**: Matrix-based, diagnosticity-focused, disconfirmation-oriented
- **Chamberlin**: Multiple working hypotheses prevent confirmation bias
- **Platt**: Strong inference via crucial experiments
