# Repolex Knowledge Graph of asimov-platform/skills

RDF knowledge graph data for [asimov-platform/skills](https://github.com/asimov-platform/skills), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download asimov-platform/skills
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a992743050740ab0a04dd8aabe4f87b086f17dc0
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a992743050740ab0a04dd8aabe4f87b086f17dc0.nq.gz
│   └── repolex
│       └── a992743050740ab0a04dd8aabe4f87b086f17dc0
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d8142a80a6663191a1b72925fc11ba2ec9e8e71.nq.gz
│   ├── 22701d9d3d7a51e8840cdf5c54dcd7be2618431c.nq.gz
│   ├── 89ba833e848b932937d142d4697795add7d4aac8.nq.gz
│   └── efb98088164f5786b17e83ed384971fc3c74f93c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a992743050740ab0a04dd8aabe4f87b086f17dc0.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 12 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[asimov-platform/skills](https://github.com/asimov-platform/skills)

---
*Parsed on 2026-09-27 by [repolex](https://repolex.ai)*
