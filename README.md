# Repolex Knowledge Graph of sphinx-contrib/tikz

RDF knowledge graph data for [sphinx-contrib/tikz](https://github.com/sphinx-contrib/tikz), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/tikz
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a6ba7fad8bc2a3beec4da6144c0906ac344943ab
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a6ba7fad8bc2a3beec4da6144c0906ac344943ab
│           └── chunk-001.nq.gz
├── blob
│   ├── 27d158e10d5f5f85c953d6ce442d4d1ccb566f6e.nq.gz
│   ├── 689f948d94e3d2fa0e2f7c3e59f23c86335f1f59.nq.gz
│   ├── 893535524197e05197b74640fa29e493a1b65a6a.nq.gz
│   ├── 8a8721b9ddde5d524f99279194bfc60c11fded6b.nq.gz
│   ├── 9f077c038b573fda4f0f284213e9626c0cbecc5a.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── c83779cdd96bc83e408dc80dbee0716fb3442599.nq.gz
│   ├── de88fc3c2a80dab73fa363d635670eef11f3c657.nq.gz
│   ├── dff61de6e2d4af9378d2e58bc332e97aea5bcd3a.nq.gz
│   ├── e2a0bdfb87cf6e63b7bef065f32943aa641d4cb7.nq.gz
│   ├── e43ed0c7b42a35048b6766246e4c7969a20e1d70.nq.gz
│   ├── e872ef993915525b6c8d0a4f22c3e81af836125a.nq.gz
│   ├── ed385f15ed2f407e50b0764e40eb5a5b720aeea1.nq.gz
│   └── f139ba1370aef21dcab039436221b87166a8895d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a6ba7fad8bc2a3beec4da6144c0906ac344943ab.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[sphinx-contrib/tikz](https://github.com/sphinx-contrib/tikz)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
