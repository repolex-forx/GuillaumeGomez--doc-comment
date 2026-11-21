# Repolex Knowledge Graph of GuillaumeGomez/doc-comment

RDF knowledge graph data for [GuillaumeGomez/doc-comment](https://github.com/GuillaumeGomez/doc-comment), parsed by [repolex](https://repolex.ai).

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
rlex download GuillaumeGomez/doc-comment
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2cf5d3c8595374191ed587e9476e99b410f377d3
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2cf5d3c8595374191ed587e9476e99b410f377d3.nq.gz
│   └── repolex
│       └── 2cf5d3c8595374191ed587e9476e99b410f377d3
│           └── chunk-001.nq.gz
├── blob
│   ├── 4eda8cc0d38d2b1bec59d522fc0d32a409e4a559.nq.gz
│   ├── 6254288db3bec2367c0177d42b4bf8e969c1a1e9.nq.gz
│   ├── 77348e762c68d44b45bd6b29f8ea05208a306ec7.nq.gz
│   ├── 7c3fc392b52c8f84cf1cce7fb066ec54a6961af8.nq.gz
│   ├── a4a4cfffff13b6933c5ebe2a9473c16b028704c9.nq.gz
│   ├── a81db3678b7b3092ed9cad2d2596d17cfe035647.nq.gz
│   ├── c86b850e2a55ae83d417369845ba5d1ba0031595.nq.gz
│   └── fa8d85ac52f19959d6fc9942c265708b4b3c2b04.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2cf5d3c8595374191ed587e9476e99b410f377d3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
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

[GuillaumeGomez/doc-comment](https://github.com/GuillaumeGomez/doc-comment)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
