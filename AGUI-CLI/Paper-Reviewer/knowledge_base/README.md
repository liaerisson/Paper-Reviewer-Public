# Knowledge Base - AI in Economic Decision-Making

## Overview

This knowledge base provides the instructions, schema, terminology, and examples that the research analysis agent uses to process user-supplied academic sources. It's pre-standing information is scoped to the intersection of artificial intelligence and economic decision-making (a topic I personally find very interesting).

## File Structure

### Static Files (do not modify at runtime)

| File | Purpose |
|---|---|
| `README.md` | This file. Maps the knowledge base structure. |
| `agent_scope.md` | Defines what the agent does, how it handles documents, and its behavioral guidelines. **Start here.** |
| `analysis_schema.md` | The table template the agent fills about each source (research question, method, findings, etc.). |
| `topic_dictionary.md` | Pre-provided reference of foundational AI and economics terms. This ensures that responses by the agent are of similar depth and consistency in terminology. |
| `_example_summary.md` | Example of a single-source summary document. The agent follows this format. |
| `_example_glossary.md` | Example of a single-source glossary page. The agent follows this format. |
| `_example_comparative_summary.md` | Example of the comparison table + narrative synthesis. The agent follows this format when it's handed 2+ sources. |

### Agent-Generated Files (created at runtime)

| File Pattern | When Created |
|---|---|
| `summary_<author>_<year>.md` | Created automatically when a user provides a new source document. |
| `glossary_<author>_<year>.md` | Created atomatically when a user provides a new source document. |
| `comparative_summary.md` | Created when ≥2 sources exist; it is updated each time a new source is added. |

## Workflow

1. User provides a document (paper, report, article).
2. Agent produces two files: a **summary document** and a **glossary page** for that source.
3. When two or more sources exist, the agent generates or updates the **comparative summary** - a table (papers as rows, schema fields as columns) followed by a short synthesis/summary of the topics and their relation.
4. User can then ask questions about the content. The agent retrieves supporting passages, labels evidence vs. inference, and grounds all answers in the corpus.

## Conventions

- All outputs use terminology consistent with `topic_dictionary.md`.
- Every finding is labeled as empirical evidence, analytical inference, or speculative claim.
- The agent does not inject external knowledge unless the user explicitly requests it.
- Novel terms found in sources are flagged as candidates for `topic_dictionary.md` addition, but the agent does not modify the dictionary directly.
