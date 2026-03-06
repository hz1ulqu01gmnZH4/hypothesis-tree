# Research Sweep (Deep Mode — Phase 2.5)

Spawn 3-4 parallel **Agent** workers to search different angles of the question before hypothesis exploration begins.

## Workers

| Agent | Role | Prompt focus |
|-------|------|-------------|
| R-literature | Key papers, reviews, meta-analyses | "Find established knowledge: consensus, key papers (title/authors/year/URL), methodological notes" |
| R-landscape | Map known vs debated vs unsolved | "What is settled? What is actively debated? What is unknown?" |
| R-contrarian | Dissenting views, negative results, retractions | "Find views that challenge the mainstream. Failed hypotheses. Surprising negative results." |
| R-adjacent | Cross-domain insights | "Search adjacent/unexpected fields for relevant analogies and insights" |

## Agent Template

```
Agent(
  description: "Research [role]",
  subagent_type: "general-purpose",
  run_in_background: true,
  prompt: "You are a research scout. Search for existing knowledge on: [QUESTION]
    Do NOT generate hypotheses — only find and summarize what is known.
    Search multiple queries, follow citations, note contradictions.
    Write to $TREE_DIR/research/[role].md with sections:
    ## Key findings
    ## Active debates
    ## Key papers (title, authors, year, summary, URL)
    ## Surprising findings
    ## Gaps in knowledge"
)
```

## After Research

1. Read all research files
2. Present a **Research Brief** to the user
3. **Revise seed hypotheses** — some may now be confirmed, refuted, or refined. New ones may emerge.
4. Write merged context to `$TREE_DIR/research/context.md` — all subsequent workers read this
