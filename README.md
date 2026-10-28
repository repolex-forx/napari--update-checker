# Repolex Knowledge Graph of napari/update-checker

RDF knowledge graph data for [napari/update-checker](https://github.com/napari/update-checker), parsed by [repolex](https://repolex.ai).

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
rlex download napari/update-checker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8e406192a218a64915ae189e7441e2566c9414e6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8e406192a218a64915ae189e7441e2566c9414e6
│           └── chunk-001.nq.gz
├── blob
│   ├── 00dfe7e0c4ff3a897d608ad489fc3119d4158701.nq.gz
│   ├── 11d7edca8e837c02a6a4ecbb95919c0af4d2e52d.nq.gz
│   ├── 2e073d5907962a701db17fbe72a69b3e48ac04bf.nq.gz
│   ├── 31f4f5cc91483ab1a95918bf4e372304fa912655.nq.gz
│   ├── 451bedaec21ea36474276ced4ad7260227f5b227.nq.gz
│   ├── 4c73f1baedae6cb335e486a604b2d1df4fadea9d.nq.gz
│   ├── 5077f12d56fbfdf3569c148f087f657bc58eb3e9.nq.gz
│   ├── 6e456df3359370ec0991fb329a63248c013d14c7.nq.gz
│   ├── 7120e739eb1f492efe39d637176bb8ef362398ee.nq.gz
│   ├── 736ee20849af2f250d266a209ae48d3b9728e510.nq.gz
│   ├── 7500707140e92be35d10d2dfdccf1d6b3b23e16d.nq.gz
│   ├── 88b21dd18b189a55be207090c9013f0ee07fe0a1.nq.gz
│   ├── 8a986551e0323817d3de61e718938561a516eaf7.nq.gz
│   ├── aefe310d88275929dd2f550ea3c7b7f5bc03bfe8.nq.gz
│   ├── af3fd05058d2b7db1a8e5947c93e7658268a09e5.nq.gz
│   ├── b23115a9b2416bd27950a3b1c557ba803928f2ab.nq.gz
│   ├── b7c0379d70f22d163166588c859d8a1c0ee382ff.nq.gz
│   ├── c645c67094127643e845f4630b97f049a8903a18.nq.gz
│   ├── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
│   ├── d8762c17e736e343ddfd40831627e9353704e1a5.nq.gz
│   ├── dd8355ac9e303249e99d31391fb02187c43e8cd8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eedd6d30095b8c58a1505603d65791ded7bdcb69.nq.gz
│   ├── f827b8292ce3b9838a3a0befa452d280af56f061.nq.gz
│   └── ff21248873756e3b9b5572516131df3ddbbc8f33.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8e406192a218a64915ae189e7441e2566c9414e6.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 32 files
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

[napari/update-checker](https://github.com/napari/update-checker)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
