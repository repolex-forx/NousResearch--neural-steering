# Repolex Knowledge Graph of NousResearch/neural-steering

RDF knowledge graph data for [NousResearch/neural-steering](https://github.com/NousResearch/neural-steering), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/neural-steering
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0083b8530a14f353d19737b944be8d93b2b130a5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 0083b8530a14f353d19737b944be8d93b2b130a5.nq.gz
│   └── repolex
│       └── 0083b8530a14f353d19737b944be8d93b2b130a5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d99204d19e6610baf5e5f291783ae6e0c9a50cb.nq.gz
│   ├── 29e851f82c2247f0995881bb38541894ebe3e33e.nq.gz
│   ├── 3a1b1d362ca871df00ae62c6325798e26ec71b0e.nq.gz
│   ├── 4d1d3628e058e97a7ab9653a004edcb09ff00b66.nq.gz
│   ├── 53ecc6038000822a7e32751a133c77a07c9af65a.nq.gz
│   ├── 6aa18ae62ceacb25e3cee70122bdabadccb543bd.nq.gz
│   ├── 7da1ecbc3cb87f7bb77d6a75ee16f7c664f6acb3.nq.gz
│   ├── 8672e535cb0203320586cce871ad3bb90fa91725.nq.gz
│   ├── 8978114ba30050c5c14b85c735559ddb82c3ac20.nq.gz
│   ├── 949b96e8eb81de0d050464bf2a056f53365843a1.nq.gz
│   ├── 9a2957b8b641184039f5f96db1664b1a6a1f84aa.nq.gz
│   ├── a899e1e06a8f899a2d310922a1069433e0a5e1cc.nq.gz
│   ├── ae583092a19c4b91f1a5e10d73b3b2e1057717ca.nq.gz
│   ├── b77bf2ab726c6e7cb5a81a9d3b7dc38266ebfd3d.nq.gz
│   ├── b9b6258cd6fae35a8392c1d3cc4aa0368d0a5d79.nq.gz
│   ├── c71b5553d6643acdaa98693f1a4e1dad141c7737.nq.gz
│   ├── ca1271ee2a9897c169b839d9f7728c9e25087580.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 0083b8530a14f353d19737b944be8d93b2b130a5.nq.gz
├── filetree
│   └── 0083b8530a14f353d19737b944be8d93b2b130a5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 28 files
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

[NousResearch/neural-steering](https://github.com/NousResearch/neural-steering)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
