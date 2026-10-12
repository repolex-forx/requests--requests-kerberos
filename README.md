# Repolex Knowledge Graph of requests/requests-kerberos

RDF knowledge graph data for [requests/requests-kerberos](https://github.com/requests/requests-kerberos), parsed by [repolex](https://repolex.ai).

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
rlex download requests/requests-kerberos
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d4088c05ad7f3c1f4968590f3243404e50c36749
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d4088c05ad7f3c1f4968590f3243404e50c36749
│           └── chunk-001.nq.gz
├── blob
│   ├── 18de33d2d717da9edc67f0755032687c4dea2743.nq.gz
│   ├── 28287fa54076bd2d90f509f40547965066d68376.nq.gz
│   ├── 51e11eca0dda118a2cee3695e5e8f16c99c38a53.nq.gz
│   ├── 57b05dcd94ccdc1705c860d3334d8f89244359cd.nq.gz
│   ├── 581f115e7877e1f262b58ffff112d066ea9de9d2.nq.gz
│   ├── 779e7b6cb33fa9bfd3ade20b0e1eeef6a3709742.nq.gz
│   ├── 7b586efc2cb48b367e2491610e1542b2c435db2f.nq.gz
│   ├── 8d6a747dee24790e6851ac652a0f8feba5430b4a.nq.gz
│   ├── 8e5e227686603e0389ad21b7703cee94960b42e6.nq.gz
│   ├── c1792a46733a5d7de4547b855797cde0eb494cae.nq.gz
│   ├── c5c480fe838d5b575eb3ff031844db9152445994.nq.gz
│   ├── d38c8ad1681983f6159507db54803217da1810cf.nq.gz
│   ├── d88d94d7cdeccf319fb5694957e3435fb023c4a8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eae61ac9e64823e412371d6535805e60b5cfaca6.nq.gz
│   ├── f2515bca1055353c0ccc6125e79ef91bcca9f024.nq.gz
│   └── f3e9ba87fb22cdc9f7b3022df9204be89d54c13a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d4088c05ad7f3c1f4968590f3243404e50c36749.nq.gz
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

[requests/requests-kerberos](https://github.com/requests/requests-kerberos)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
