# Repolex Knowledge Graph of adamchainz/patchy

RDF knowledge graph data for [adamchainz/patchy](https://github.com/adamchainz/patchy), parsed by [repolex](https://repolex.ai).

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
rlex download adamchainz/patchy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8f3f9bf0c0ebda7e53fa1192527b4a02e8254ced
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8f3f9bf0c0ebda7e53fa1192527b4a02e8254ced
│           └── chunk-001.nq.gz
├── blob
│   ├── 06576b23d0ac66e7ce14a603918d6c42135b52bb.nq.gz
│   ├── 13b2aacd2a066ad35ee196b5df2996d7588fc11f.nq.gz
│   ├── 205ab9ad9df4ab629d1b7b8d8a72b41f44d8824c.nq.gz
│   ├── 22ddbb118475b52ce8ecba56d9ec45009923da58.nq.gz
│   ├── 2777df92f6415108e7383be658192d7da0ffe595.nq.gz
│   ├── 2a7f84f54867d02714727f82eef95d3be939d666.nq.gz
│   ├── 30acc83b6797da94e6f047ba88ccfb5b934894ee.nq.gz
│   ├── 3ba13e0cec6cbbfd462e9ebf529dd2093148cd69.nq.gz
│   ├── 40f4ac757715bb1a8c355eda9124141fdda3aeff.nq.gz
│   ├── 438d629c3ce988e3afffa71110b9660853d38549.nq.gz
│   ├── 4525e13b968bd456b31677d4430f5b526f83c03a.nq.gz
│   ├── 4a235c40c90583af154bb61a8cb830e72d805d98.nq.gz
│   ├── 4fb7faec2960085d0994a23838947e58b6228aa7.nq.gz
│   ├── 533ff689a01128cf1fd2c139cd0d45186304e330.nq.gz
│   ├── 5b5feb5d35ae1f5cbdc44f54c28668405a8423db.nq.gz
│   ├── 5f4e8b9d5855ee5a1a3d7a9f7f047472f5e71342.nq.gz
│   ├── 674aa9f159d7b10ca739630c3c665db2bdb37c2b.nq.gz
│   ├── 7670784c4f93aaf2ac6f58da11f1d01cccecac3d.nq.gz
│   ├── 7f1d007c01048570d774e58f46203d3e92056c39.nq.gz
│   ├── 8cf69add569b562affef123f735d5ca92f5e1281.nq.gz
│   ├── 9097f62d7d15020c243314bd6456525ba073c1ce.nq.gz
│   ├── 93acb639926ccf42e9a2f76f02419eeaf0405c3a.nq.gz
│   ├── aa43ec31d1df0140dc31cdba9a62e7aba610a1e2.nq.gz
│   ├── b33b8e53c6a60a969985daef0828998c0b266bed.nq.gz
│   ├── c2052352efe85a31ff97f015bfc0a35137d4cf61.nq.gz
│   ├── e3a606abcb6783d6ddff0ee50ab9612f700e4fff.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed8fa1878c8411620843c20e63e05765a2fc7850.nq.gz
│   ├── efa54568d45d44f72e4bc42aa89ae06b0afc8fa3.nq.gz
│   └── f0a2abfa16717167b289159a2f38a41fde8a3457.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8f3f9bf0c0ebda7e53fa1192527b4a02e8254ced.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[adamchainz/patchy](https://github.com/adamchainz/patchy)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
