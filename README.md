# Repolex Knowledge Graph of allenai/IFBench

RDF knowledge graph data for [allenai/IFBench](https://github.com/allenai/IFBench), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/IFBench
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cd189a9c2889526d8af901d2103fd3e1ffcea6df
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cd189a9c2889526d8af901d2103fd3e1ffcea6df
│           └── chunk-001.nq.gz
├── blob
│   ├── 0383ae03852a52efe7786e8461665dffa21cb778.nq.gz
│   ├── 17364550afd1de37ebbdbf52bb322fef1e43b742.nq.gz
│   ├── 1751ab60b97063bd047b1e1a5cf8eaaabee2aefb.nq.gz
│   ├── 221b70a015715f63677735f341c7c86484c03073.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c362e3ed59913a656f19d0da790b57f7b54b62f.nq.gz
│   ├── 3bf45e3d2b0e0de6a0670bc55d210376e9195ec6.nq.gz
│   ├── 3fbe1ac812a5ea4aad82273baedcbfc2337317b4.nq.gz
│   ├── 5283fef0e3678ddaeaa2289b2188c34a3e8a4f82.nq.gz
│   ├── 52fa00f383967432c41baf31586ff56e6bd3e1c5.nq.gz
│   ├── 5d7b90a6bb51b0df068990d023b741c3d1d76c50.nq.gz
│   ├── 65b589b94d1269dc2e2ebdba66f02bf4128f8962.nq.gz
│   ├── 6b4dcdac0894cd7b17fcf5816b464b158f7821d1.nq.gz
│   ├── 874058cfeb59fe8d2d6746662205f1883ad2d28c.nq.gz
│   ├── 8f2c4ecfbff0a13a71efa27ab10666bc54eeaa92.nq.gz
│   ├── 965d00ae5477193cde17447c5a0ca9c734efde62.nq.gz
│   ├── 972ad1b6ee2bb164c5610a798900885781485105.nq.gz
│   ├── 9dcfce8f741dca419a2d3352617ef683307c6a81.nq.gz
│   ├── a03612eac041b5244572209b6f63e57f4e837ed0.nq.gz
│   ├── a8e343ed928d8b4e649b9dba651fed7757ccacc3.nq.gz
│   ├── acba40b66032b750dfc9034ceb98e3a6c2d00a2c.nq.gz
│   ├── c3d2f5ef7de81fca058efd7f81f9bd258eff54fd.nq.gz
│   ├── c3ff72ead12d0e30d4040b5c6646c0e6af81729e.nq.gz
│   ├── d23846147468b3263569048fb3ed41daa6cbe954.nq.gz
│   ├── dc4d138e9db0572c5baff5a848f8edc00e76a89a.nq.gz
│   └── f6e26a38b6b0a018dc34675a02da327b36bca43d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cd189a9c2889526d8af901d2103fd3e1ffcea6df.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[allenai/IFBench](https://github.com/allenai/IFBench)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
