# Theoretical Frameworks for Rigorous Hypothesis Evaluation

## Comprehensive Research Survey

---

## 1. Philosophy of Science Evaluation Criteria

### 1.1 Popper's Falsifiability (Demarcation Criterion)

Karl Popper's principle of falsifiability serves as a **demarcation criterion** distinguishing science from non-science. A theory is scientific only if it makes predictions that can, in principle, be proved wrong.

**Key evaluation implications:**
- A hypothesis must make **specific, testable predictions** that could be refuted
- The more falsifiable (bold) a prediction, the more scientifically valuable
- Corroboration (surviving attempts at refutation) is meaningful; mere "confirmation" is not
- Ad hoc modifications to save a theory from refutation reduce its scientific status

**Limitations:** Naive falsificationism fails because (1) single experiments rarely decisively refute theories, and (2) the Quine-Duhem problem shows hypotheses cannot be tested in isolation.

### 1.2 Lakatos's Methodology of Scientific Research Programmes

Lakatos synthesized Popper and Kuhn, proposing that science proceeds through **research programmes** rather than individual hypotheses.

**Structure of a Research Programme:**
- **Hard core**: Fundamental assumptions, protected by methodological decision ("negative heuristic")
- **Protective belt**: Auxiliary hypotheses that can be modified
- **Positive heuristic**: Guidance for developing the programme

**Evaluation Criteria — Progressive vs. Degenerating:**
| Criterion | Progressive Programme | Degenerating Programme |
|-----------|----------------------|----------------------|
| Theoretical progress | Predicts novel facts | Only accommodates known facts |
| Empirical progress | Some novel predictions confirmed | Ad hoc adjustments dominate |
| Heuristic power | Generates new research questions | Increasingly defensive modifications |
| Problem-shift | Each modification increases content | Each modification is content-decreasing |

**Key insight for evaluation tool:** Do not evaluate hypotheses in isolation — evaluate them as part of a research programme. Ask: Does this hypothesis represent a progressive or degenerating problem-shift?

### 1.3 Kuhn's Paradigm Evaluation

Thomas Kuhn (1962, *The Structure of Scientific Revolutions*) argued that competing paradigms may be **incommensurable** — operating with different assumptions and standards that make direct comparison difficult.

**Kuhn's five criteria for theory choice:**
1. **Accuracy** — Consequences deducible from theory should agree with experiment
2. **Consistency** — Internally consistent and consistent with other accepted theories
3. **Broad scope** — Consequences extend beyond the particular observations it was designed to explain
4. **Simplicity** — Brings order to phenomena that would otherwise be individually isolated
5. **Fruitfulness** — Discloses new phenomena or new relationships among known phenomena

**Critical nuance:** Kuhn argued these criteria are necessary but **insufficient** — they function as values, not rules. Different scientists may weight them differently, leading to legitimate disagreement.

### 1.4 Bayesian Confirmation Theory

Bayesian epistemology provides a **formal, quantitative framework** for hypothesis evaluation.

**Core mechanism — Bayes' Theorem:**
```
P(H|E) = P(E|H) × P(H) / P(E)
```

**Key concepts for evaluation:**
- **Prior probability P(H)**: Initial plausibility before evidence
- **Likelihood P(E|H)**: How well the hypothesis predicts the evidence
- **Posterior P(H|E)**: Updated belief after evidence
- **Confirmation**: E confirms H iff P(H|E) > P(H)
- **Degree of confirmation**: Various measures (log-likelihood ratio, Bayes factor)

**Practical evaluation metrics:**
- **Bayes Factor**: Ratio of likelihoods under competing hypotheses; quantifies relative evidential support
- **Prior plausibility**: Can be informed by theoretical considerations, background knowledge
- **Predictive precision**: More specific predictions that are confirmed provide stronger confirmation

### 1.5 Inference to the Best Explanation (IBE) — Lipton

Peter Lipton's IBE framework provides criteria for what makes one explanation **better** than another.

**Lipton's "Two-Filter" Model:**
1. **Filter 1 — Potential explanations**: Generate candidate hypotheses
2. **Filter 2 — Best explanation**: Select the "loveliest" explanation that passes a quality threshold

**Explanatory Virtues (Lipton's Criteria):**
- **Scope**: Explains more types of phenomena
- **Precision**: Explains phenomena with greater specificity
- **Mechanism**: Provides information about underlying causal mechanisms
- **Unification**: Connects apparently disparate phenomena
- **Simplicity**: Achieves explanation with fewer assumptions
- **Loveliness**: Depth of understanding provided (not just likely truth)

**Bridge to Bayesianism:** Lipton argued IBE and Bayesianism are **compatible** — explanatory considerations can supply the actual values of prior probabilities and likelihoods in Bayes' theorem. "Bayesian conditionalisation is run in part on explanationist tracks."

**The "Bad Lot" Problem (van Fraassen):** IBE only selects the best of available explanations — but the truth might not be among them. Lipton's response: the best explanation must be "good enough" to merit inference, not merely best among bad options.

### 1.6 The Quine-Duhem Problem

**Core thesis:** It is impossible to test a scientific hypothesis in isolation because any empirical test requires assuming the truth of one or more **auxiliary hypotheses** (background assumptions, measurement theories, initial conditions).

**Formal structure:**
- It is not H alone that entails E, but H ∧ B (where B = background knowledge)
- Therefore, ¬E entails ¬H ∨ ¬B — but does not tell us *where* the problem lies

**Implications for hypothesis evaluation:**
1. **No crucial experiment** can conclusively refute a single hypothesis
2. Any theory can be "saved" by modifying auxiliary assumptions
3. Theory evaluation requires assessing the **entire web of beliefs**, not isolated hypotheses
4. **Confirmation holism**: A bundle of hypotheses is tested against the world, not individual claims

**Practical response:** While absolute isolation is impossible, we can:
- Make auxiliary assumptions explicit and evaluate their independent support
- Assess whether protective modifications are independently motivated or purely ad hoc
- Use Lakatos's progressive/degenerating distinction to evaluate the pattern of modifications

---

## 2. Formal Hypothesis Evaluation Frameworks

### 2.1 Bradford Hill Criteria (Causal Hypotheses)

Proposed in 1965 for evaluating causal claims in epidemiology. Hill described nine **"viewpoints"** (not a checklist) for studying association before crying causation.

**The Nine Criteria:**

| # | Criterion | Description | Evaluation Question |
|---|-----------|-------------|-------------------|
| 1 | **Strength** | Larger associations more likely causal | How large is the effect? |
| 2 | **Consistency** | Replicated across persons, places, times | Has this been found by others? |
| 3 | **Specificity** | Specific exposure-outcome relationship | Is the cause-effect pair specific? |
| 4 | **Temporality** | Cause precedes effect | Is the temporal order established? (Only "necessary" criterion) |
| 5 | **Biological gradient** | Dose-response relationship | Does more exposure mean more effect? |
| 6 | **Plausibility** | Biologically plausible mechanism | Is there a known mechanism? |
| 7 | **Coherence** | Consistent with known biology | Does it conflict with known facts? |
| 8 | **Experiment** | Supported by experimental evidence | Does intervention change outcome? |
| 9 | **Analogy** | Similar cause-effect known | Are there analogous examples? |

**Important caveat:** Hill explicitly warned these should NOT be used as a checklist. They are considerations, not necessary conditions. Only temporality is strictly required.

### 2.2 GRADE Framework (Systematic Reviews / Meta-Analyses)

The **Grading of Recommendations, Assessment, Development and Evaluation (GRADE)** framework is the most widely used tool for assessing evidence certainty in systematic reviews.

**Evidence Certainty Levels:**
- **High**: Further research very unlikely to change confidence in the effect estimate
- **Moderate**: Further research likely to have an important impact
- **Low**: Further research very likely to have an important impact
- **Very Low**: Any estimate of effect is very uncertain

**Factors that DECREASE certainty:**
1. Risk of bias (study limitations)
2. Inconsistency (heterogeneity of results)
3. Indirectness (applicability concerns)
4. Imprecision (wide confidence intervals)
5. Publication bias

**Factors that INCREASE certainty:**
1. Large magnitude of effect
2. Dose-response gradient
3. All plausible confounders would reduce the effect

**Starting points:** RCTs begin as high-quality; observational studies begin as low-quality.

### 2.3 Chamberlin's Method of Multiple Working Hypotheses (1890)

T.C. Chamberlin's method, first published in *Science* (1890, reprinted 1965), is foundational for scientific reasoning.

**Core principles:**
1. **Generate multiple hypotheses** — never settle on a single "ruling theory"
2. Each hypothesis suggests different lines of inquiry
3. Facts are sought for **induction and demonstration**, not to prove a favored hypothesis
4. The method guards against **confirmation bias** by distributing intellectual commitment

**Three dangers the method prevents:**
1. **Parental affection** for a pet hypothesis (confirmation bias)
2. **Premature closure** — accepting the first plausible explanation
3. **Tunnel vision** — failing to see alternative explanations

**Modern relevance:**
- Directly connects to model selection vs. null hypothesis testing debate
- Framework for determining hypothesis identifiability *a priori*
- "Be heartily skeptical of any explanation of a natural phenomenon that is simple"

### 2.4 Journal/Reviewer Evaluation of Hypothesis Quality

Based on peer review criteria from multiple sources:

**Standard Review Dimensions:**
1. **Originality/Novelty** — New question, new interpretation, better model, new application
2. **Significance/Importance** — Impact on field, addresses important problem
3. **Soundness/Rigor** — Logical validity, methodological quality
4. **Clarity** — Clearly stated, well-structured
5. **Relevance/Scope** — Fits journal scope, generalizable
6. **Evidence-based grounding** — Built on existing literature, not speculation

**What makes a "good" hypothesis (per journals):**
- Clear and testable
- Falsifiable — specifies conditions under which it would be wrong
- Based on previous evidence-based reports
- Well-balanced evaluation of existing knowledge
- Novel synthesis of existing information in unexpected ways
- Ethically sound — can be tested by ethical experiments

**Pre-registration quality criteria:**
- Research hypotheses explicitly stated
- Sampling procedure specified
- Sample size justified
- Measures and data coding defined
- Criteria for data exclusions stated
- Statistical analyses pre-specified
- Clear distinction between confirmatory and exploratory analyses

**Problem:** Studies show "very low concordance among coders about the number of hypotheses (14%)" in pre-registrations — hypotheses are often not clearly stated even when required.

---

## 3. AI/LLM Hypothesis Evaluation

### 3.1 Current Evaluation Metrics in AI Science Systems

**Common dimensions used across systems:**
| Dimension | Description | Used By |
|-----------|-------------|---------|
| **Novelty** | Distinct from existing work | IdeaBench, HARPA, HypoGen, AI Scientist |
| **Feasibility** | Can be implemented/tested with available resources | IdeaBench, HARPA, AI Scientist |
| **Significance/Impact** | Importance to the field | AI Scientist, IdeaBench |
| **Clarity** | Well-articulated and understandable | Peer review systems |
| **Soundness** | Logically/scientifically valid | Automated reviewers |
| **Specificity** | Precise enough to guide experiments | HARPA |
| **Groundedness** | Supported by existing literature | HARPA, BioVerge |
| **Testability** | Can be empirically verified | HARPA |

### 3.2 Key Systems and Their Evaluation Approaches

**IdeaBench (2411.02429):**
- Two-stage evaluation: GPT-4o ranks ideas based on user-specified quality indicators (novelty, feasibility), then calculates relative-ranking-based "Insight Score"
- Benchmarks LLMs against each other on idea generation quality

**HARPA (2510.00620) — Testability-Driven Framework:**
- Evaluates on: specificity, novelty, overall quality, feasibility, groundedness
- Uses 10-point Likert scale
- Key finding: feasibility (+0.78) and groundedness (+0.85) gains over baseline
- Expert feasibility judgments tracked with actual execution success (20 vs 11 out of 40)
- Learns a reward model from prior experimental outcomes (+28% gain)

**HypoGen / Sparks of Science (2504.12976):**
- "Bit-Flip-Spark" schema: Bit (conventional assumption), Spark (key insight), Flip (counterproposal)
- Evaluates: novelty, feasibility, overall quality
- Uses automated metrics + LLM judge rankings
- Chain-of-Reasoning component reflects intellectual process

**BioVerge (2511.08866):**
- Self-evaluating agents for biomedical hypothesis generation
- ReAct-based approach with distinct Generation and Evaluation modules
- Self-evaluation significantly improves novelty and relevance
- Key finding: different agent architectures influence exploration diversity and reasoning strategies

**AI Scientist (Sakana Labs, 2408.06292) & AI Scientist-v2:**
- Seeds ideas with "interestingness," "feasibility," and "novelty" values
- Automated LLM-powered reviewer achieves near-human accuracy
- Reviewer dimensions (standard ML conference criteria): soundness, presentation, contribution, overall confidence
- AI Scientist-v2: one manuscript exceeded average human acceptance threshold at ICLR workshop

**SciAgents (Ghafarollahi & Buehler, MIT, 2024):**
- Multi-agent system: Ontologist, Scientists, Critic
- Generates, refines, and critically evaluates hypotheses against novelty and feasibility
- Knowledge-graph grounded
- Limitation: lacks mechanisms for experimental validation

**Can LLMs Unlock Novel Research Ideas? (2409.06185):**
- Proposes two automated metrics: **Idea Alignment Score (IAScore)** and **Idea Distinctness Index**
- Human evaluation on: novelty, relevance, feasibility
- Notes: no prior automated evaluation metric existed for idea generation

### 3.3 Automated Review Scoring Frameworks

**Standard dimensions across automated reviewers:**
- Originality, Importance, Support, Soundness, Clarity, Value, Contextualization
- Typically combined into 1-10 overall score
- Some use binary accept/reject decisions

**Key automated review systems:**
- Stanford Agentic Reviewer: 7-dimension scoring, trained on 150 ICLR 2025 submissions
- DeepReview: structured three-stage process (understanding, criterion-based evaluation, synthesis)
- DEBATE framework: uses Devil's Advocate agent to resolve bias in multi-agent scoring

### 3.4 Emerging Approaches

**Execution-Based Validation (2601.05930):**
- "Generate-Execute-Feedback" paradigm has an execution bottleneck
- Proposes predicting experimental outcomes before execution
- Addresses the gap between hypothesis generation and validation

**Scientific General Intelligence Framework (2512.16969):**
- Practical Inquiry Model (PIM): Deliberation, Hypothesis, Experiment, Evaluation
- Scientist-aligned workflows for evaluating LLM scientific reasoning

**SelfAI (2512.00403):**
- Long-horizon scientific discovery with efficiency-diversity trade-offs
- Balances exploration of hypothesis space vs. exploitation

---

## 4. Cognitive Biases in Hypothesis Evaluation

### 4.1 Primary Biases Affecting Hypothesis Evaluation

**Confirmation Bias:**
- Preference for information consistent with a hypothesis rather than opposing it
- Systematic errors in inductive reasoning
- People seek out, interpret, and remember information that supports existing beliefs
- In science: selective literature review, biased experimental design, motivated reasoning in data interpretation

**Anchoring Bias:**
- Over-reliance on first piece of information encountered (the "anchor")
- Insufficient adjustment from initial value
- Extremely difficult to de-bias — even arbitrary/irrelevant values affect judgment
- In hypothesis evaluation: first hypothesis considered becomes anchor for evaluating all others

**Availability Heuristic:**
- Judging frequency/probability by how easily examples come to mind
- Readily available ideas seem more plausible
- In science: recent/dramatic findings seem more important; obscure but critical evidence overlooked

**Other relevant biases:**
- **Bandwagon effect**: Adopting hypotheses because of peer acceptance
- **Status quo bias**: Resistance to novel hypotheses challenging established views
- **Framing effect**: How a hypothesis is presented affects evaluation
- **Overconfidence**: Systematic underestimation of uncertainty (driven by availability and anchoring)
- **Base rate neglect**: Ignoring prior probabilities when evaluating evidence

### 4.2 Analysis of Competing Hypotheses (ACH) — Heuer's Method

Developed by Richards J. Heuer Jr. at the CIA in the 1970s. Published in *Psychology of Intelligence Analysis* (1999).

**The 8-Step ACH Process:**
1. **Identify all potential hypotheses** — brainstorm with diverse analysts
2. **List evidence and arguments** for/against each hypothesis (including assumptions)
3. **Construct a matrix** — hypotheses as columns, evidence as rows
4. **Assess diagnosticity** — which evidence discriminates between hypotheses?
5. **Refine the matrix** — reconsider hypotheses, add evidence
6. **Draw tentative conclusions** — based on which hypotheses have LEAST disconfirming evidence
7. **Analyze sensitivity** — what if key evidence is wrong/deceptive?
8. **Report conclusions** — identify milestones for future monitoring

**Critical principle:** Focus on **disconfirming** evidence, not confirming evidence. The hypothesis with the least evidence against it is preferred (Popperian logic applied to intelligence analysis).

**Diagnosticity concept:** Evidence is "diagnostic" when it is consistent with one hypothesis but inconsistent with another. Non-diagnostic evidence (consistent with all hypotheses) is noise.

### 4.3 Structured Analytic Techniques (SATs)

From Heuer & Pherson's taxonomy, eight categories:

1. **Decomposition and visualization** — Break complex problems into parts
2. **Idea generation** — Brainstorming, nominal group technique
3. **Scenarios and indicators** — Multiple futures planning
4. **Hypothesis generation and testing** — ACH, diagnostic reasoning
5. **Cause and effect** — Causal mapping, influence diagrams
6. **Challenge analysis** — Devil's advocate, Team A/Team B, "What if?" analysis
7. **Conflict management** — Structured debate, adversarial collaboration
8. **Decision support** — Decision matrices, pros-cons-fixes

### 4.4 Red Team / Devil's Advocate Methods

**Historical origin:** 11th-century Vatican "Advocatus Diaboli" — charged with finding arguments against candidates for sainthood.

**Red Team Analysis:**
- Adversarial approach: challenge assumptions, test environment, evaluate all alternatives
- Dedicated team whose role is to find flaws in the prevailing analysis
- Used by military, intelligence, and cybersecurity communities

**Devil's Advocate Method:**
- Artificially presents intelligence assessment contradicting the prevailing view
- Goal: encourage doubts among assessors and decision-makers
- Minimizes risks of groupthink and conformity pressure

**Team A/Team B:**
- Two independent teams analyze same evidence
- Team A: develops best case for prevailing hypothesis
- Team B: develops best case for alternative hypothesis
- Structured comparison reveals weaknesses and hidden assumptions

**AI Application — DEBATE Framework:**
- Multi-agent scoring with dedicated Devil's Advocate agent
- Agent instructed to criticize other agents' arguments
- Designed to resolve bias in automated evaluation

---

## 5. Practical Evaluation Methods

### 5.1 Pre-Registration Criteria

**Purpose:** Separate confirmatory from exploratory research; reduce researcher degrees of freedom.

**Standard pre-registration elements:**
- Research hypotheses (clearly stated)
- Sampling procedure and sample size justification
- Research design and testing conditions
- Measures, stimuli, and data coding
- Criteria for data exclusions
- Pre-specified statistical analyses
- Distinction between confirmatory and exploratory analyses

**Quality problems:**
- Hypotheses often not clearly stated (14% inter-coder agreement on number of hypotheses)
- Pre-registration formats vary greatly in specificity guidance
- Structured formats improve quality over unstructured

### 5.2 Strong Inference — Platt (1964)

John R. Platt's "Strong Inference" (*Science*, 1964) argues that the fastest-progressing sciences share a common method.

**The Three Essential Steps (Iterated):**
1. **Devise alternative hypotheses** — multiple, not just one
2. **Devise a crucial experiment** — with alternative possible outcomes, each excluding one or more hypotheses
3. **Carry out the experiment** — obtain a clean result

Then **recycle**: refine remaining possibilities, generate new alternatives, design new crucial experiments.

**Key principles:**
- Hypotheses must be clearly visible and explicit
- Experiments designed to **exclude** hypotheses, not support them
- "Conditional inductive tree" — systematic branching through hypothesis space
- Each experiment prunes the tree, narrowing toward truth

**Why some sciences progress faster:**
- Fields that use strong inference (molecular biology, particle physics) progress rapidly
- Fields that rely on "weak inference" (accumulating evidence for a single hypothesis) progress slowly

### 5.3 Designing Discriminating Tests Between Competing Hypotheses

**Requirements for a discriminating test:**
1. **Differential predictions**: H1 and H2 must predict different outcomes for the same observable
2. **Auxiliary assumptions**: Must be independently established (minimize Quine-Duhem problems)
3. **Clean outcomes**: Experimental design must minimize ambiguity
4. **Exclusion power**: Result should strongly exclude at least one hypothesis

**Strategies:**
- Identify the **point of maximum divergence** between competing hypotheses
- Design observations at the point where predictions differ most
- Use **crucial experiments** (Bacon's "instantia crucis") — though recognize their limitations
- Employ Bayesian reasoning: which experiment maximizes expected change in posterior probability?
- Apply information-theoretic approach: which experiment maximizes expected information gain?

**Modern framework (from Chamberlin + Platt + Bayesian):**
1. Enumerate all plausible hypotheses
2. For each pair, identify differential predictions
3. Rank potential experiments by **expected diagnosticity**
4. Prioritize experiments that discriminate among the most hypotheses simultaneously
5. Execute and update; iterate

---

## 6. Synthesis: Requirements for a Rigorous Hypothesis Evaluation Tool

### 6.1 Evaluation Dimensions (Synthesized from All Frameworks)

Drawing from philosophy of science, formal methods, AI research, and intelligence analysis:

**Tier 1 — Epistemic Quality (Is it good science?)**
| Dimension | Source(s) | Description |
|-----------|-----------|-------------|
| **Falsifiability/Testability** | Popper, Platt, HARPA | Can the hypothesis be empirically refuted? |
| **Specificity/Precision** | Kuhn, Bradford Hill, HARPA | Are predictions specific enough to test? |
| **Internal Consistency** | Kuhn, formal logic | Free from self-contradiction? |
| **Evidential Support** | Bayesian, GRADE, Bradford Hill | What is the current evidence base? |
| **Groundedness** | HARPA, BioVerge, Bradford Hill | Rooted in existing scientific knowledge? |

**Tier 2 — Explanatory Power (Does it explain well?)**
| Dimension | Source(s) | Description |
|-----------|-----------|-------------|
| **Scope/Breadth** | Kuhn, Lipton (IBE) | How many phenomena does it explain? |
| **Mechanistic Depth** | Lipton, Bradford Hill | Does it identify causal mechanisms? |
| **Unification** | Lipton, Kuhn (simplicity) | Does it connect disparate phenomena? |
| **Coherence** | Kuhn, Bradford Hill | Consistent with broader knowledge? |
| **Simplicity/Parsimony** | Kuhn, Lipton, Bayesian (priors) | Is it the simplest adequate explanation? |

**Tier 3 — Scientific Productivity (Will it advance knowledge?)**
| Dimension | Source(s) | Description |
|-----------|-----------|-------------|
| **Novelty/Originality** | Lakatos, IdeaBench, AI Scientist | Does it predict/explain new things? |
| **Progressiveness** | Lakatos | Progressive or degenerating problem-shift? |
| **Fruitfulness** | Kuhn, Chamberlin | Generates new research questions? |
| **Discriminability** | Platt, ACH | Can it be distinguished from alternatives? |
| **Feasibility** | HARPA, AI Scientist, IdeaBench | Can it be tested with available methods? |

**Tier 4 — Robustness (Can it survive scrutiny?)**
| Dimension | Source(s) | Description |
|-----------|-----------|-------------|
| **Auxiliary transparency** | Quine-Duhem | Are background assumptions explicit? |
| **Bias resistance** | ACH, Heuer, cognitive science | Evaluated against alternatives, not in isolation? |
| **Sensitivity** | ACH Step 7, GRADE | How sensitive are conclusions to key assumptions? |
| **Replicability potential** | Bradford Hill (consistency) | Would others reach same conclusion? |

### 6.2 Process Requirements (Synthesized)

1. **Multiple hypotheses** — Always evaluate multiple competing hypotheses (Chamberlin, Platt, ACH)
2. **Focus on disconfirmation** — Weight disconfirming evidence heavily (Popper, ACH, Strong Inference)
3. **Assess diagnosticity** — Prioritize evidence that discriminates between hypotheses (ACH, Bayesian)
4. **Make assumptions explicit** — List and evaluate auxiliary hypotheses (Quine-Duhem)
5. **Structured comparison** — Use matrix-based comparison (ACH, decision matrices)
6. **Adversarial review** — Include Devil's Advocate / red team challenge (SATs, DEBATE)
7. **Iterative refinement** — Update evaluations as new evidence arrives (Bayesian updating, Platt cycling)
8. **Bias awareness** — Actively counter confirmation bias, anchoring, availability (cognitive science, ACH)
9. **Sensitivity analysis** — Assess how conclusions change if key evidence is wrong (ACH, GRADE)
10. **Calibrated confidence** — Express uncertainty levels, not binary judgments (GRADE, Bayesian)

### 6.3 Recommended Scoring Approach

Based on the AI literature and formal frameworks:

- Use **multi-dimensional scoring** (not a single number)
- **10-point Likert scales** per dimension (standard in HARPA, peer review)
- Group dimensions into tiers (epistemic quality, explanatory power, productivity, robustness)
- Require **explicit justification** for each score (not just numbers)
- Include **relative ranking** among competing hypotheses (IdeaBench approach)
- Calculate **diagnosticity** of available evidence (ACH approach)
- Provide **confidence/uncertainty** for each assessment (GRADE approach)
- Use **adversarial evaluation** — separate generation from critique (BioVerge, DEBATE)

---

## Sources

### Philosophy of Science
- [Kuhn vs Popper; the philosophy of Lakatos](https://antimatter.ie/2011/02/11/kuhn-vs-popper-the-philosophy-of-lakatos/)
- [Imre Lakatos' Approach: Bridging Popper and Kuhn](https://philosophy.institute/philosophy-of-science-and-cosmology/imre-lakatos-philosophy-science-bridge/)
- [Popper, Kuhn, Lakatos and Aim-Oriented Empiricism](https://www.ucl.ac.uk/from-knowledge-to-wisdom/essays/popperkuhnlakatosaoe)
- [Popper, Kuhn, Lakatos, and Feyerabend (lecture notes)](https://wuthrich.net/teaching/2013_145/Lect07_PopperEtAl.pdf)
- [Lakatos — Falsification and the Methodology of Scientific Research Programs](http://www.inf.fu-berlin.de/lehre/pmo/eng/Lakatos-Falsification.pdf)
- [Inference to the Best Explanation, 2nd edition — Review](https://ndpr.nd.edu/reviews/inference-to-the-best-explanation-2nd-edition/)
- [Inference to the Best Explanation — Overview (PhilSci-Archive)](https://philsci-archive.pitt.edu/20363/1/Inference+to+the+Best+Explanation+-+An+Overview+Penultimate%20Draft.pdf)
- [Confirmation by Explanation: A Bayesian Justification of IBE](https://philsci-archive.pitt.edu/13328/)
- [Hartmann review of Lipton](https://sas-space.sas.ac.uk/1068/1/S_Hartmann_Lipton.pdf)
- [Duhem-Quine thesis (Wikipedia)](https://en.wikipedia.org/wiki/Duhem%E2%80%93Quine_thesis)
- [Underdetermination of Scientific Theory (Stanford Encyclopedia)](https://plato.stanford.edu/entries/scientific-underdetermination/)
- [The Quine-Duhem Thesis and Implications for Scientific Method](https://faculty.fairfield.edu/rdewitt/Psci/Ch05.pdf)

### Formal Hypothesis Evaluation
- [Bradford Hill criteria (Wikipedia)](https://en.wikipedia.org/wiki/Bradford_Hill_criteria)
- [Revisiting Bradford Hill to incorporate developments in causal thinking](https://pmc.ncbi.nlm.nih.gov/articles/PMC8206235/)
- [Applying Bradford Hill criteria in the 21st century](https://pmc.ncbi.nlm.nih.gov/articles/PMC4589117/)
- [Chamberlin — The Method of Multiple Working Hypotheses (original PDF)](https://www.whoi.edu/cms/files/chamberlin65sci_72744.pdf)
- [Revisiting Chamberlin: Multiple Working Hypotheses for the 21st Century](https://academic.oup.com/bioscience/article/57/7/608/238555)
- [Modern method of multiple working hypotheses (Royal Society)](https://royalsocietypublishing.org/doi/10.1098/rsos.200231)
- [GRADE Handbook](https://gradepro.org/handbook/)
- [Introduction to GRADE](https://www.sciencedirect.com/science/article/pii/S2213398423002713)
- [Pre-registration (Wikipedia)](https://en.wikipedia.org/wiki/Preregistration_(science))
- [Ensuring quality and specificity of preregistrations](https://pmc.ncbi.nlm.nih.gov/articles/PMC7725296/)
- [Hypothesis Requirements — Journal of Emerging Investigators](https://emerginginvestigators.org/submissions/hypothesis-driven-research)
- [Developing Criteria Framework for Peer Review](https://onlinelibrary.wiley.com/doi/10.1002/leap.2016)

### AI/LLM Hypothesis Evaluation
- [IdeaBench (arXiv 2411.02429)](https://arxiv.org/abs/2411.02429)
- [HARPA: Testability-Driven Framework (arXiv 2510.00620)](https://arxiv.org/abs/2510.00620)
- [Sparks of Science / HypoGen (arXiv 2504.12976)](https://arxiv.org/abs/2504.12976)
- [BioVerge (arXiv 2511.08866)](https://arxiv.org/abs/2511.08866)
- [Can LLMs Unlock Novel Research Ideas? (arXiv 2409.06185)](https://arxiv.org/abs/2409.06185)
- [AI Scientist — Sakana Labs](https://sakana.ai/ai-scientist/)
- [AI Scientist-v2 paper](https://pub.sakana.ai/ai-scientist-v2/paper/paper.pdf)
- [Evaluating Sakana's AI Scientist (arXiv 2502.14297)](https://arxiv.org/abs/2502.14297)
- [SciAgents (arXiv 2409.05556)](https://arxiv.org/abs/2409.05556)
- [Can We Predict Before Executing ML Agents? (arXiv 2601.05930)](https://arxiv.org/abs/2601.05930)
- [Scientific General Intelligence framework (arXiv 2512.16969)](https://arxiv.org/abs/2512.16969)
- [SelfAI (arXiv 2512.00403)](https://arxiv.org/abs/2512.00403)
- [InnovatorBench (arXiv 2510.27598)](https://arxiv.org/abs/2510.27598)
- [AI-Researcher (arXiv 2505.18705)](https://arxiv.org/abs/2505.18705)
- [Exploring LLMs in the Scientific Method (Nature)](https://www.nature.com/articles/s44387-025-00019-5)
- [Stanford Agentic Reviewer](https://paperreview.ai/tech-overview)
- [DEBATE: Devil's Advocate-Based Assessment](https://arxiv.org/html/2405.09935v2)

### Cognitive Biases & Intelligence Analysis
- [ACH — How Does It Improve Intelligence Analysis? (Pherson)](https://pherson.org/wp-content/uploads/2013/06/06.-How-Does-ACH-Improve-Analysis_FINAL.pdf)
- [Analysis of Competing Hypotheses (Wikipedia)](https://en.wikipedia.org/wiki/Analysis_of_competing_hypotheses)
- [CIA Tradecraft Primer: Structured Analytic Techniques](https://www.cia.gov/resources/csi/static/Tradecraft-Primer-apr09.pdf)
- [ACH in intelligence analysis (Dhami, 2019)](https://onlinelibrary.wiley.com/doi/full/10.1002/acp.3550)
- [Confirmation bias (Wikipedia)](https://en.wikipedia.org/wiki/Confirmation_bias)
- [Heuristics and biases in expert assessment](https://www.ncbi.nlm.nih.gov/books/NBK571047/)
- [Devil's Advocate in Intelligence: Israeli Experience](https://www.tandfonline.com/doi/full/10.1080/02684527.2018.1470062)

### Strong Inference & Discriminating Tests
- [Platt (1964) — Strong Inference (original)](https://pages.cs.wisc.edu/~markhill/science64_strong_inference.pdf)
- [Fifty years of Platt's Strong Inference](https://journals.biologists.com/jeb/article/217/8/1202/13095/Fifty-years-of-J-R-Platt-s-strong-inference)
- [Strong Inference (Wikipedia)](https://en.wikipedia.org/wiki/Strong_inference)
- [Strong Inference for Systems Biology](https://pmc.ncbi.nlm.nih.gov/articles/PMC2724742/)
