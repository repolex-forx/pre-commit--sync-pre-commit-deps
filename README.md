# Repolex Knowledge Graph of pre-commit/sync-pre-commit-deps

RDF knowledge graph data for [pre-commit/sync-pre-commit-deps](https://github.com/pre-commit/sync-pre-commit-deps), parsed by [repolex](https://repolex.ai).

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
rlex download pre-commit/sync-pre-commit-deps
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eb61537bdfde28d178b8f06aa9f13b46b77ca4cf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eb61537bdfde28d178b8f06aa9f13b46b77ca4cf
│           └── chunk-001.nq.gz
├── blob
│   ├── 0345f426b49152caaa2ce8f8d27fb2f6bb034142.nq.gz
│   ├── 05534ce10ef0c4fb5cce69ec809b48c834893912.nq.gz
│   ├── 076f2a478a3004dd57a40d9cc39059bbbdb1976f.nq.gz
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 3fdffa121e3b0e62264cdf10bc360c93537670b7.nq.gz
│   ├── 674555ca480a239763fd085f51a318b85de90328.nq.gz
│   ├── 886c8ae7ad217df7a479e7b8e0a40e7ec29d2c12.nq.gz
│   ├── a03590f54d8b03c2bee4276a20b3bf402d26b06c.nq.gz
│   ├── ab6639b3e08857b0d8947f8dd2ebc1a5c1e470fe.nq.gz
│   ├── b2db189864279efd1303cab1454fdddab149091c.nq.gz
│   ├── db0db108e1a9769656b4f4fc1f379b66de2be91a.nq.gz
│   ├── dd119794a57dd31e2ce54881b18fe9bb0c1ae545.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eb61537bdfde28d178b8f06aa9f13b46b77ca4cf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[pre-commit/sync-pre-commit-deps](https://github.com/pre-commit/sync-pre-commit-deps)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
