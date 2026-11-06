# Repolex Knowledge Graph of sphinx-contrib/erlangdomain

RDF knowledge graph data for [sphinx-contrib/erlangdomain](https://github.com/sphinx-contrib/erlangdomain), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/erlangdomain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae7f7a219575b3f3069a8bdf9bccc69c5b079923
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae7f7a219575b3f3069a8bdf9bccc69c5b079923
│           └── chunk-001.nq.gz
├── blob
│   ├── 1e092b9af214839f180a5c05ade3a3a2db15fd34.nq.gz
│   ├── 2530132a83cc3902d730cbd74023a7336b381121.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 3ce233fac7a8a68769d04cccefa0764ad6437d8a.nq.gz
│   ├── 3f16b68fb50fc10787187316b26ca9f3d481959f.nq.gz
│   ├── 4310ae15746fc35a2a0fe40d0d7cf7919c5ac17b.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 4d592664fb07a813801baf4794f5bb450a042206.nq.gz
│   ├── 5447fe0779f4720aa1c8108e59b98a72751e510b.nq.gz
│   ├── 576c5e457e3d4bd0fe64bafc828ce14aa24f4287.nq.gz
│   ├── 8a328719e8e4edd45e0a3c8b8b095051bb409e48.nq.gz
│   ├── 999d1c46260fbdc18622105f7087e573dd9766bc.nq.gz
│   ├── a560d7597d33842d3c3e7a19557d43c26576c13a.nq.gz
│   ├── b3f12423dd7a528d72e9f6e67ecf1a41d81f585e.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── cb047d76ab9d6f8a576b46ab82bc1dcaa6189f49.nq.gz
│   ├── cc2d9fce361917cefaab329f8eef6c93fd5a6b93.nq.gz
│   └── f1b45f2bf7f005083976397ede2f8464a172249d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae7f7a219575b3f3069a8bdf9bccc69c5b079923.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 24 files
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

[sphinx-contrib/erlangdomain](https://github.com/sphinx-contrib/erlangdomain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
