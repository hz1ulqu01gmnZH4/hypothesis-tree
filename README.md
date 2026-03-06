# hypothesis-tree

A suite of 3 Claude Code skills for recursive hypothesis exploration, rigorous evaluation, and Japanese persona debate.

## Skills

### `/hypothesis-tree` — Recursive Hypothesis Generation
Generate competing hypotheses for any question, then spawn parallel agents to explore each branch — searching evidence, decomposing into sub-hypotheses, and converging. Based on Platt's Strong Inference + Tree of Thoughts.

- Quick mode (seed → explore → synthesize) or Deep mode (+ research sweep, critic, cross-pollination)
- Parallel Agent workers with evidence search
- Persistent output to `~/hypothesis-trees/`

### `/hypothesis-eval` — Hypothesis Evaluation
Stress-test hypotheses with 18-dimension scoring across 4 tiers (epistemic quality, explanatory power, scientific productivity, robustness). Grounded in philosophy of science.

- 3 parallel stress-test agents: Devil's Advocate, Steelman, Auxiliary Auditor (Quine-Duhem)
- ACH matrix for comparing competing hypotheses
- Discriminating test design (Platt's crucial experiments)
- Output to `~/hypothesis-evals/`

### `/hypothesis-debate` — 仮説バトル (Hypothesis Battle)
5 characters with distinct Japanese speech patterns (役割語) debate a hypothesis across 3 rounds. Funny but rigorous.

| Cast | Speech | Role |
|------|--------|------|
| 厳格先生 (`ω´)σ | Academic keigo | Falsificationist |
| 熱血後輩 (ﾉ≧∀≦)ﾉ | Casual kouhai | Steelman |
| 浪人哲学者 (¬_¬) | Archaic samurai | Epistemological critic |
| ギャル研究者 (☆▽☆) | Gyaru slang + stats | Empiricist |
| 座長 (￣ー￣) | Ultra-formal keigo | Judge |

## Pipeline

```
/hypothesis-tree "Why do some species cooperate?"
  → generates tree with ranked hypotheses

/hypothesis-eval ~/hypothesis-trees/.../REPORT.md
  → 18-dimension scores, stress tests, ACH matrix

/hypothesis-debate ~/hypothesis-evals/.../
  → 厳格先生 vs 熱血後輩 vs 浪人哲学者 vs ギャル研究者 → 座長の裁定
```

## Install

Copy skill directories to `~/.claude/skills/`:

```bash
cp -r hypothesis-tree ~/.claude/skills/
cp -r hypothesis-eval ~/.claude/skills/
cp -r hypothesis-debate ~/.claude/skills/
cp -r hypothesis-shared ~/.claude/skills/

# Symlink shared resources
for skill in hypothesis-tree hypothesis-eval hypothesis-debate; do
  ln -sf ../hypothesis-shared/methodology.md ~/.claude/skills/$skill/methodology.md
done
```

## Theoretical Grounding

Popper (falsifiability), Lakatos (progressive/degenerating programmes), Kuhn (5 theory-choice values), Lipton (inference to best explanation), Bayesian confirmation, Quine-Duhem (auxiliary hypotheses), Heuer ACH (intelligence analysis), Bradford Hill (causal criteria), Tree of Thoughts, Graph of Thoughts, SciAgents, HARPA.

## License

WTFPL
