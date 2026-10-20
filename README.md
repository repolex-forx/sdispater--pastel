# Repolex Knowledge Graph of sdispater/pastel

RDF knowledge graph data for [sdispater/pastel](https://github.com/sdispater/pastel), parsed by [repolex](https://repolex.ai).

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
rlex download sdispater/pastel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 760a8e52dd989dfd47c72e82776657c530c8c1b0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 760a8e52dd989dfd47c72e82776657c530c8c1b0
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f2630e4c5acc307af867c372cd20d695a349ddf.nq.gz
│   ├── 24baec696532aa3a95f8174859b9b60175f4c747.nq.gz
│   ├── 2a9339c5bc67048be22d5724d5aca0e1f726aea3.nq.gz
│   ├── 2f07a56fb90f8cb396a5d6e084eddbe77bdd4f99.nq.gz
│   ├── 3445c0f146a320e5fdfb6205c31a839681eac58b.nq.gz
│   ├── 3d56664b3652914b452b465ecc7d4b95ff1dd7d6.nq.gz
│   ├── 40a96afc6ff09d58a702b76e3f7dd412fe975e26.nq.gz
│   ├── 44cf2b30e6888272f6b278672d0077cd5948b1e7.nq.gz
│   ├── 49feedec7020df8d5ea440fc9e6495a317e13ff8.nq.gz
│   ├── 4d6d8b3adbebedc87100c29b2be3ba02ff970aee.nq.gz
│   ├── 76f106cd1bcc4b080d445a38f7dc5227904e9ba8.nq.gz
│   ├── 7a6e0f2d33d856c85149c5f66417c54a1a8412a7.nq.gz
│   ├── 9115196a6be7a4ae7f28cf33047909a98b304747.nq.gz
│   ├── 948298e91e967a00d21948e3583a289a655eee2c.nq.gz
│   ├── a5a98f918bbf320c9b1223e4ca8b046a64deef64.nq.gz
│   ├── a8f3b45b9f2949159e4864ea4c7ca373c9439602.nq.gz
│   ├── e682838a99ce6c04f3a03ad1a589ae169da145ee.nq.gz
│   ├── ec0874b8a3c5f1997483365828703aad74dd83e5.nq.gz
│   └── f11664c8e7a5aabf68e8e96c97a23edf51004507.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 760a8e52dd989dfd47c72e82776657c530c8c1b0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[sdispater/pastel](https://github.com/sdispater/pastel)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
