# Repolex Knowledge Graph of pypa/scripttest

RDF knowledge graph data for [pypa/scripttest](https://github.com/pypa/scripttest), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/scripttest
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3bebe70d1148f6f6c1204e4ddd09de50f6dac859
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3bebe70d1148f6f6c1204e4ddd09de50f6dac859
│           └── chunk-001.nq.gz
├── blob
│   ├── 00fd2463d43d42b694cfae5594aae4743c118f2f.nq.gz
│   ├── 02afdefcd4646d3bd9b4cf7cf5a48d50462e7ce8.nq.gz
│   ├── 112ca519ac35c7d12b4d1fe4a87b04694ab9f4d8.nq.gz
│   ├── 157b8e574f0ea96e79e0a3c8076755e39f37e157.nq.gz
│   ├── 1b64d40d216f1e3ac5b4d51d2ea941a285809d3a.nq.gz
│   ├── 2369791c52f5cb99c88fb24dc37ecf453e70804f.nq.gz
│   ├── 2f155de240fc4b551ccafa8ee545e186f3bfdf2f.nq.gz
│   ├── 30f58bca155aeb717c6915986a3be23215cc4d05.nq.gz
│   ├── 6b570520488fcc122128dc563493217306da1447.nq.gz
│   ├── 744805b2623febb3395cfbafcccb24d5025ac0e5.nq.gz
│   ├── 8baf63a3efca9c865cb807d30178f9b25cf381e3.nq.gz
│   ├── a3afdbe9969f37da92e960fd82fc4458f086c0d6.nq.gz
│   ├── c2f8a81f91d5eed2db23db5fc258390dc54dbcf6.nq.gz
│   ├── c85ceec132358d0e955a23fbafade0e42180ed6a.nq.gz
│   ├── d1707ef098aaf834661f6bf9d2a8761bba441119.nq.gz
│   ├── d5a46cf05d82e45968a5cac6da97ae3399b40bc0.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3bebe70d1148f6f6c1204e4ddd09de50f6dac859.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[pypa/scripttest](https://github.com/pypa/scripttest)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
