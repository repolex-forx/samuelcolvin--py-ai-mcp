# Repolex Knowledge Graph of samuelcolvin/py-ai-mcp

RDF knowledge graph data for [samuelcolvin/py-ai-mcp](https://github.com/samuelcolvin/py-ai-mcp), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/py-ai-mcp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d878d6478c4ac5b74fda681622230747cf45a0ae
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d878d6478c4ac5b74fda681622230747cf45a0ae
│           └── chunk-001.nq.gz
├── blob
│   ├── 0358a607d6105992c9dc8d849f556267b7526132.nq.gz
│   ├── 0c1c5d1090fa36ba5e5e0b1b7285fef658c9b1e3.nq.gz
│   ├── 1bfdee81b28261858f3a1829a53e5bfad95a3acc.nq.gz
│   ├── 6215cfbb70d7fd378dd25b10b7e1561deb13a2e0.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 956f2a4417aabfae9fd2168964c862c4f6d977c5.nq.gz
│   ├── bb254358f87c34eeef3eed0c81de615edf13bdfa.nq.gz
│   ├── c4d62b531cc253b04a5c32d577eef5125cf5c7cf.nq.gz
│   └── c76d7c1a9df18ea9d64cf8e9ecfff419d90fbd02.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d878d6478c4ac5b74fda681622230747cf45a0ae.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[samuelcolvin/py-ai-mcp](https://github.com/samuelcolvin/py-ai-mcp)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
