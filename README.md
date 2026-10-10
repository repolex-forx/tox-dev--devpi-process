# Repolex Knowledge Graph of tox-dev/devpi-process

RDF knowledge graph data for [tox-dev/devpi-process](https://github.com/tox-dev/devpi-process), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/devpi-process
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b4d09adc26bda7dabeb489737e36d42ae76ed9e4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b4d09adc26bda7dabeb489737e36d42ae76ed9e4
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f7f364f3886843ff9548a87f83e83313d77a65.nq.gz
│   ├── 17a712ab247c833b73f9d37dfbedfa9b6c233280.nq.gz
│   ├── 19f75f451811d073dee45fa48f7af1581ea02e46.nq.gz
│   ├── 35c4c96547f77f4e717c1081a7018f0e59973e2c.nq.gz
│   ├── 35fb4162b9d1107c0030994ee6ed3a3913481935.nq.gz
│   ├── 3a016a0deb004f82225f1cb4f80f0996861e61a8.nq.gz
│   ├── 5968e5bcc55e7d0e43554bfb3203512e1e1fe0d0.nq.gz
│   ├── 5abf3e7c1a71ef78a6f3856c5fdced58fa90f3fa.nq.gz
│   ├── 5f89818f9e63c2f6829c7706c57f223cdb5bbd38.nq.gz
│   ├── 69d0cfd202c019ca1d5a92d59faf9a1380c61930.nq.gz
│   ├── 792cdac044e456e9999eaba5223f45aab09479e8.nq.gz
│   ├── 8babb03aeb50f552f90c772ddc1a2f2f9c8c44c3.nq.gz
│   ├── 97e22757480c6da9f4d71e250451d96aa4218be7.nq.gz
│   ├── a7321b7e631262ec27d8ba13cc1a4425037848c2.nq.gz
│   ├── b371c1a0d75a2deccc085d5e9d2ae9bc294a9642.nq.gz
│   ├── c0fd26bfab64fab7b16f5ee8f66f2eadc728809d.nq.gz
│   ├── cb7c58d3ed58fdb87e8fc37b7a73f9953efee6c5.nq.gz
│   ├── cba9a7bfe25e80fe223540069f26ed377177f623.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ed5d7fafb95ac23a1970d4f66e3942fe89062e9e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b4d09adc26bda7dabeb489737e36d42ae76ed9e4.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[tox-dev/devpi-process](https://github.com/tox-dev/devpi-process)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
