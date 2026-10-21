# Repolex Knowledge Graph of ibis-project/ibis-sqlflite

RDF knowledge graph data for [ibis-project/ibis-sqlflite](https://github.com/ibis-project/ibis-sqlflite), parsed by [repolex](https://repolex.ai).

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
rlex download ibis-project/ibis-sqlflite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7868c5308583f4b74c3f1a7961049abd144822b1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7868c5308583f4b74c3f1a7961049abd144822b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 04ed0db14018ffc406fa05ffd6dcdfa229599868.nq.gz
│   ├── 18a0ec7fe2b540ea7d75143766676c5337419961.nq.gz
│   ├── 3a2706e66b97ca56e709f0146b216feff0dfa874.nq.gz
│   ├── a4277ca82760898172cd947ee1f1445a4180abb5.nq.gz
│   ├── b53402d0aa76ed163396075995f725cc38d9413f.nq.gz
│   ├── c1285714b2daef0a3d44733e98dba83a9c9f2503.nq.gz
│   ├── d0bfe807c99164515173c3b20cd3b9985cd0e94a.nq.gz
│   ├── dd79d090423bdf94ba6acb28bb1b4112174b070c.nq.gz
│   └── e8719ac71b561404b08f445cea52f6dbe1e0a493.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7868c5308583f4b74c3f1a7961049abd144822b1.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[ibis-project/ibis-sqlflite](https://github.com/ibis-project/ibis-sqlflite)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
