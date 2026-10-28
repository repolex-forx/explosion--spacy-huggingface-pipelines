# Repolex Knowledge Graph of explosion/spacy-huggingface-pipelines

RDF knowledge graph data for [explosion/spacy-huggingface-pipelines](https://github.com/explosion/spacy-huggingface-pipelines), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/spacy-huggingface-pipelines
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c7bb7a74d505d14374bd5bd97301e5836ec5e258
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c7bb7a74d505d14374bd5bd97301e5836ec5e258
│           └── chunk-001.nq.gz
├── blob
│   ├── 03b92fb4adc3b193f7e49b17c3fcd909da5ce229.nq.gz
│   ├── 0d4bf58a93a8a6f82dc7645c2abd48ea6505834d.nq.gz
│   ├── 138d8171888dd22c44c807bbddf90c28c9c13213.nq.gz
│   ├── 242d0794e5bfef72c037ddb7b5fee50a2aa3af26.nq.gz
│   ├── 270041b68dffacdb60cf6d613bd8da7e70adf94f.nq.gz
│   ├── 3d4fded10fddcb5590f4e2a2320bcfa1726fa1ac.nq.gz
│   ├── 4d3bb6749c0df63f084e0f266068b01ee7fc2500.nq.gz
│   ├── 4e9fd251d3f258bfc9e35301044a860bcbab4bbd.nq.gz
│   ├── 61924727f712f1034a858ffbc20341b7cd04f19e.nq.gz
│   ├── 74f0f6c263846982ed5b8dae3612f5daf9f7d207.nq.gz
│   ├── 7b12d99eb1a2e0681e1bd992b2cdbc1017776798.nq.gz
│   ├── 916418f1191710f100a14f4ea8f25d9722932a66.nq.gz
│   ├── bb393f8b74d6e80b9991b1ef38d0aa9f1b2f7051.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ebafc94f62e75d27bff066a20b825af430d61a7f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c7bb7a74d505d14374bd5bd97301e5836ec5e258.nq.gz
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

[explosion/spacy-huggingface-pipelines](https://github.com/explosion/spacy-huggingface-pipelines)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
