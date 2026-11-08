# Repolex Knowledge Graph of canonical/charmcraftcache

RDF knowledge graph data for [canonical/charmcraftcache](https://github.com/canonical/charmcraftcache), parsed by [repolex](https://repolex.ai).

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
rlex download canonical/charmcraftcache
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b9e5fce8b77eac4e418290ad03ae8366fba10b14
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b9e5fce8b77eac4e418290ad03ae8366fba10b14
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 34f7c6c9f9e9c7fe9ea897e988666e8d45e81df4.nq.gz
│   ├── 49ec4dd96dfda524eed8610067870d11c4057cb9.nq.gz
│   ├── 4be332471769dd5ab7e31af98ca34c175de2c814.nq.gz
│   ├── 57a7dd98e6628a569aff9b28052eac3619238551.nq.gz
│   ├── 6b1c7c51ba4d1a4a4a2aad74decdfb8e3a2ccf3c.nq.gz
│   ├── 717688050a21c636d0ac315bd23218ce777c4686.nq.gz
│   ├── 7221c077f08e5a16b4cde29b27128e7149c70fb0.nq.gz
│   ├── 932a17f417345772f2e66a69cd420cd087c0e501.nq.gz
│   ├── cbc59a6c1827f87d71633e925b087b91d55e2d20.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b9e5fce8b77eac4e418290ad03ae8366fba10b14.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[canonical/charmcraftcache](https://github.com/canonical/charmcraftcache)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
