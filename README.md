# Repolex Knowledge Graph of davecgh/go-spew

RDF knowledge graph data for [davecgh/go-spew](https://github.com/davecgh/go-spew), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download davecgh/go-spew
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8991bc29aa16c548c550c7ff78260e27b9ab7c73
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 8991bc29aa16c548c550c7ff78260e27b9ab7c73.nq.gz
│   └── repolex
│       └── 8991bc29aa16c548c550c7ff78260e27b9ab7c73
│           └── chunk-001.nq.gz
├── blob
│   ├── 00268614f04567605359c96e714e834db9cebab6.nq.gz
│   ├── 0f5ce47dcaf6c4fa8768a6655340a381195d691c.nq.gz
│   ├── 108baa55f1db47eddda32520e97d8a10c405ca5a.nq.gz
│   ├── 1be8ce9457612e02a64c01b2321d087ebd6415f2.nq.gz
│   ├── 1f4cbf5425dc0804b9ca1112e8a54a5e1346db25.nq.gz
│   ├── 205c28d68c474e4497e6aa1ce8b9fdeb260f4586.nq.gz
│   ├── 2cd087a2a1273c5446897521ae85658fb8e66def.nq.gz
│   ├── 2e3d22f312026ff2c863bbffcbc88b7f6fb942f5.nq.gz
│   ├── 32c0e338825308f6b9b4d0407aa5682a23e2dc9c.nq.gz
│   ├── 4a31a2ee37fe536c16666e01b405a83a1760e7fa.nq.gz
│   ├── 52a0971fb3f1f4c712d485ddc64f918567d508ab.nq.gz
│   ├── 5c87dd456ed031deaca010e64a7ed55168df66b3.nq.gz
│   ├── 792994785e36ca74c5545a0d93a2cdecda006678.nq.gz
│   ├── 80dc22177db25720abc48df563ed6053c11dce5f.nq.gz
│   ├── 87ee9651e363b2872cdbf57ed225d5143b6c3a04.nq.gz
│   ├── 9579497e4115f7e90e1adf99417ddb65d113e532.nq.gz
│   ├── aacaac6f1e1e936ee0022c00e139756c9bdc2b3e.nq.gz
│   ├── b04edb7d7ac278ae0b873a1335f37822a00bfd7c.nq.gz
│   ├── b70466c69f8e6443d35c9454f1222ddf3d279777.nq.gz
│   ├── bc52e96f2b0ea97cc450e2fefbbb4cc430d1ac5a.nq.gz
│   ├── c6ec8c6d59e0169f58fec1c92ce1b2a3205c4bf5.nq.gz
│   ├── e312b4fadc070b6c9cffa98a2666a6d61d146470.nq.gz
│   ├── f6ed02c3b672fa9c70ce790bc7f34bb957e61643.nq.gz
│   └── f78d89fc1f6c454df58cd1e346817db6e30c4299.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8991bc29aa16c548c550c7ff78260e27b9ab7c73.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 33 files
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

## Source repository

[davecgh/go-spew](https://github.com/davecgh/go-spew)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
