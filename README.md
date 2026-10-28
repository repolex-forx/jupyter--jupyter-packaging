# Repolex Knowledge Graph of jupyter/jupyter-packaging

RDF knowledge graph data for [jupyter/jupyter-packaging](https://github.com/jupyter/jupyter-packaging), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/jupyter-packaging
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4915fc8e36e38111b96c23e28e37b2873ca57907
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4915fc8e36e38111b96c23e28e37b2873ca57907
│           └── chunk-001.nq.gz
├── blob
│   ├── 1e11e82c59916d29e1e5a31b7613623a4d8066d4.nq.gz
│   ├── 2896e3c0648213fafb3deec52bbaeffc42e3b3ec.nq.gz
│   ├── 2ec12cc295bacf4ad78d8bce295c2ed9c52fcfbc.nq.gz
│   ├── 385b47bb4a14f077d7b423618015f42a9758f423.nq.gz
│   ├── 45014fc44d76a3605a05ba3be909954917438c36.nq.gz
│   ├── 4bb9b39e7d8edd1dbb7ac1dbde8a4baa5811c559.nq.gz
│   ├── 5c78f81cd0eac65862c567b390c61540d91bd809.nq.gz
│   ├── 6fda381bd7622cdfdedf0e1ba45d09b072b07337.nq.gz
│   ├── 72364f99fe4bf8d5262df3b19b33102aeaa791e5.nq.gz
│   ├── 725feab5ce652dc39f3f2c77b9fd3c90bf049c65.nq.gz
│   ├── 7e8f67faef3850426c5eacc3115db550fc28dec9.nq.gz
│   ├── 84e11fe35544592c22a07193034d0105f0970bc2.nq.gz
│   ├── 8a6dafbf1a1d9bbf058ffedf41524244450bf3da.nq.gz
│   ├── a75a95ff14032967f45c259b9b4a968049dc5836.nq.gz
│   ├── a99e707ac794bb87fff7cbdc314d30445bc7a6fc.nq.gz
│   ├── aabf1d753dfe5f86eeb6f4909d0857a9684e8bbb.nq.gz
│   ├── ab47198c14e98f2b9edfc3bddd7d89e72278b6ab.nq.gz
│   ├── b6739fe8ce3947dffca566efd02934e5c922124a.nq.gz
│   ├── c2108499eed8cd2c2397e2cd1eeaa00c350e5c9f.nq.gz
│   ├── c30c2c143a716c2aa202a0640757df688b03c0d0.nq.gz
│   ├── cbfdbe4a48837feb4a5142d4daa15d4d5bc8ac7e.nq.gz
│   ├── db054adc261ccb402f3b4bf6de27a21c0e5370b8.nq.gz
│   ├── dc4e4a1221c6a12ec9ee0751e738689bd19b3ba1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb5c3b356c6ac08e355926b4505be20927ad3f83.nq.gz
│   ├── ec50f0fc60e33aea4aa09b044577819f6b84869e.nq.gz
│   └── f0ebbf4713e6194118ae7f37e9fd537e3f175660.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4915fc8e36e38111b96c23e28e37b2873ca57907.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[jupyter/jupyter-packaging](https://github.com/jupyter/jupyter-packaging)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
