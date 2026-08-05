# KnowledgeHub

> 中文版：[README.md](README.md)

KnowledgeHub is an evolving knowledge base powered by Obsidian + Codex. It is not a "file storage repository"; it is a "compile once, keep updating" knowledge system. Raw material is refined first, then accumulated into topic notes and queryable knowledge pages, so knowledge keeps compounding as it is used.

This manual is for new users: copy this repository, add your own content, and turn it into your own knowledge base.

## What Is This

The knowledge base follows the LLM Wiki idea: humans collect, ask, and judge; Codex organizes, links, maintains, and writes back. Answers prefer the already compiled knowledge layer over reconstructing answers from raw material every time.

Core layers:

```text
Raw material (Inbox)
    ↓ Organic ingest
Topic notes (Notes/<topic>/)
    ↓ Summarize and navigate
Knowledge pages (Wiki/Theme + Wiki/Items)
```

## Quick Start

1. Open this directory as a Vault in Obsidian.
2. Edit `AGENTS.md` and replace the personal information with your own.
3. Put your first piece of material into `Inbox/`.
4. Ask Codex to run an organic ingest according to `AGENTS.md`; it creates source cards and updates the topic manual.
5. Ask questions based on `Wiki/`; Codex says "no evidence found" clearly when the vault has no answer.

## Directory Structure

| Directory | Responsibility |
| --- | --- |
| `Inbox/` | New captures and unprocessed raw material; processed material is archived to `Inbox/archive/` |
| `Notes/` | Organized source cards and knowledge notes, grouped by topic folders |
| `Wiki/` | Knowledge pages for learning: `Theme/` holds topic manuals, `Items/` holds cross-topic concept pages |
| `Outputs/` | Personal deep-learning outputs such as long-form notes and project retrospectives; read-only, manually refluxed into `Notes/` |
| `Ideas/` | Inspiration, reflections, and thinking |
| `Projects/` | Active work and projects |
| `assets/` | Media resources such as images |
| `AGENTS.md` | The operating rules of the knowledge base; read-only and maintained by the user |

## Core Workflows

1. **Organic ingest**: material in `Inbox/` is judged for net value, organized into source cards or knowledge notes under `Notes/<topic>/`, and the original file is archived to `Inbox/archive/`.
2. **Topic manual**: each topic has a `Wiki/Theme/<topic>.md` that explains the learning path, key concepts, sources, conclusions, conflicts, and gaps.
3. **Deep-learning reflux**: valuable outputs in `Outputs/` are manually refluxed, upgrading shallow notes in `Notes/` and updating the topic manual.
4. **Q&A reflux**: valuable Q&A candidates are merged into existing notes or knowledge pages instead of being left in chat history.
5. **Cross-topic concepts**: concepts that are reused across multiple topics become `Wiki/Items/` pages for repeated querying.

## Use Cases

**Daily collection and retrieval**

Drop articles, web pages, and ideas into `Inbox/`, then ask Codex questions when needed. The knowledge base prefers the compiled knowledge layer; when evidence is missing, Codex says so instead of filling in with generic online answers.

**Deep dive into a topic**

Keep accumulating around one direction: every ingested piece updates the topic manual. Learning path, key concepts, current conclusions, and gaps live on one page, which helps answer "what is missing and what should I read next."

**Project and experience accumulation**

Write project retrospectives, experiment logs, and failure cases into `Outputs/`, then reflux them into stable knowledge. Later, similar problems can reuse decisions, implementation anchors, and applicability boundaries instead of being derived from memory.

**Cognitive review and feedback**

Ask Codex to scan the whole vault regularly to find hidden connections, old/new viewpoint conflicts, cognitive changes, and blind spots. Briefs and retrospectives generate candidates by default; stable, reusable conclusions enter the knowledge layer through Q&A reflux.

**Output and sharing**

`Wiki/` pages are already well-organized material. When writing articles, preparing talks, or building a topic digest, use the topic manuals and concept pages as a base; then reflux the writing process into `Outputs/`.

**Cross-domain connection**

When the same concept appears in multiple topics, it is promoted to a `Wiki/Items/` concept page. The knowledge base can then reuse concepts across domains, for example transferring a "control risk first, then pursue returns" framework from investing to project decisions or study planning.

## Usage Tips

- Ingest one piece at a time; optimize the loop before batching.
- Install the official Obsidian Web Clipper for web material: set the save location to `Inbox` and use `{{date|date:"YYYY-MM-DD"}} - {{title}}` as the note name so clippings land in the collection area and filenames are recognizable by Codex. After clipping, use the shortcut to download images into local `assets/`.
- Build `Wiki/Theme/` topic manuals first before adding advanced retrieval; a small vault does not need a vector database.
- Run health checks regularly: contradictions, stale conclusions, orphan pages, broken links, and high-value Q&A that has not been written back.
- Write your practical experience and retrospectives into `Outputs/`, then manually reflux them into stable knowledge.

## Usage Examples

**Collect**

Save an article, web page, or idea as Markdown into `Inbox/`, preferably with a date in the filename:

```text
Inbox/2026-08-05 - Article title.md
```

**Ingest one piece with Codex**

```text
Please ingest Inbox/2026-08-05 - Article title
```

Codex first judges the net value and lists exact file actions; after your approval it creates a source card or knowledge note, updates the corresponding topic manual, and archives the original to `Inbox/archive/`.

**Ask Codex**

```text
Please answer based on Wiki/ and Notes/: what is the difference between X and Y?
```

Answers should cite the compiled knowledge pages first; if the vault has no evidence, Codex clearly says "no evidence found in notes" and does not fill gaps with generic online knowledge.

**Reflux a deep-learning output**

```text
Please reflux Outputs/<topic>/<filename>
```

Codex checks whether `Notes/` already has a shallow note for the same source: if yes, it upgrades it to a deep-learning note; if not, it creates a new one, and updates `Wiki/Theme/<topic>.md`. `Outputs/` files stay read-only.

**Run a health check**

```text
Please scan Wiki/ and Notes/ for contradictions, stale conclusions, orphan pages, broken links, and gaps
```

The results are candidate maintenance actions; writes still require your explicit approval.

## Rules

- `AGENTS.md` is the only operating rule of this vault. It is read-only and maintained by the user; Codex does not modify it.
- All writes to `Notes/`, `Wiki/`, and `Ideas/` list precise file actions first and execute only after explicit approval.
- Image paths use forward slashes `/`; local images live in `assets/` and external images keep their original URLs.
- Math formulas use `$...$` / `$$...$$`; source cards and knowledge notes keep the original metaphors, examples, and figures instead of over-compressing.
