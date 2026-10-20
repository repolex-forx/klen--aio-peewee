# Repolex Knowledge Graph of klen/aio-peewee

RDF knowledge graph data for [klen/aio-peewee](https://github.com/klen/aio-peewee), parsed by [repolex](https://repolex.ai).

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
rlex download klen/aio-peewee
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a28e681b8859b11a1daa6ba92a9402a814a888ac
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a28e681b8859b11a1daa6ba92a9402a814a888ac
│           └── chunk-001.nq.gz
├── blob
│   ├── 0850d8d1bffc9ff0c550bd0814cf012974e3e8fc.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2e81ce52ff1b9cec38ea5e61ac145a70b0185580.nq.gz
│   ├── 43c82c6e83f813c8c6e48038c2f88072a7735fd2.nq.gz
│   ├── 52c2c2e601f33cb26e37b831b9a0c923b3bbf13b.nq.gz
│   ├── 63e1e810fb6af617ac61784cb227f60b18901034.nq.gz
│   ├── 824804178d2dd2d86903e779622b1d64dae4eb99.nq.gz
│   ├── 9918019d0ac9f96a8ccff9d3102db5dce9bcc288.nq.gz
│   ├── b024da80e9c1c8c800cc1b46e90c1e783cb446cc.nq.gz
│   ├── b9f4c12bf12bcc272ff04a2566d6613d6cc1b179.nq.gz
│   ├── e23904ba7ebd91a81630d688a097719155dfcb19.nq.gz
│   ├── e30b53729de1f4934667279dadbef3c212ec221a.nq.gz
│   ├── e3906aae066be7dbc6ec1ad0c81be157c9c1fac6.nq.gz
│   ├── e3f8656be2552c369acf17a9d254dcd8433300b8.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a28e681b8859b11a1daa6ba92a9402a814a888ac.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[klen/aio-peewee](https://github.com/klen/aio-peewee)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
