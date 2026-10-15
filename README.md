# Repolex Knowledge Graph of simonw/paginate-json

RDF knowledge graph data for [simonw/paginate-json](https://github.com/simonw/paginate-json), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/paginate-json
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b4f5e64423ea792bbd16b1d074a073267ee87b9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4b4f5e64423ea792bbd16b1d074a073267ee87b9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e1f5a182bdf8b8aea99def12145f3bb3771a765.nq.gz
│   ├── 11dccadd048931220cb22df16ac97432023e1b3d.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 487907e3073b75ddbc6000fed508765d10059209.nq.gz
│   ├── 5a147533e524ad54695ba86f7bb7c4c129b998d1.nq.gz
│   ├── 7d7dc7d3eac287a8309fec93eb6afb47a4baebc1.nq.gz
│   ├── 9d6175d6765a530b54d4a3290289ab81e37761e8.nq.gz
│   ├── ba15a02a19b6492617f757123b1ff85ad35434b9.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b4f5e64423ea792bbd16b1d074a073267ee87b9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[simonw/paginate-json](https://github.com/simonw/paginate-json)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
