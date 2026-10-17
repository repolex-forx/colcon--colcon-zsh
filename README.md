# Repolex Knowledge Graph of colcon/colcon-zsh

RDF knowledge graph data for [colcon/colcon-zsh](https://github.com/colcon/colcon-zsh), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-zsh
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ea584ed779482e6be019a622605f67fc20f63d51
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ea584ed779482e6be019a622605f67fc20f63d51
│           └── chunk-001.nq.gz
├── blob
│   ├── 03ab80aea9b91ac9e0abab556a4910c986af3f5e.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 13295faab3f84ebe216b6e5d1ead463083f7d31f.nq.gz
│   ├── 37e595e501d3f49488ed8fbd4744b3d13135a519.nq.gz
│   ├── 6a83ffadbbfefb74e98577def4531caaa2ec494b.nq.gz
│   ├── 7770b2bb0be613c63654d38507a779064726364d.nq.gz
│   ├── 897e8599a974e32177f3aa6ddbdb23475943b2f7.nq.gz
│   ├── 942c8c510de8049c63df5472c4d05b1bc489e929.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d9fba75b81ed2097c852b8925efa9f8519523edb.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e5542827ee3fdba67c3fd8134713b5fdfe7942c3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   ├── eca76bf1e2d2b5b65bf3872ea711d1afc2c92cda.nq.gz
│   └── f7a16d48081a6848a9b505f27d969e2e0df2213c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ea584ed779482e6be019a622605f67fc20f63d51.nq.gz
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

[colcon/colcon-zsh](https://github.com/colcon/colcon-zsh)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
