# Repolex Knowledge Graph of litestar-org/litestar-piccolo

RDF knowledge graph data for [litestar-org/litestar-piccolo](https://github.com/litestar-org/litestar-piccolo), parsed by [repolex](https://repolex.ai).

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
rlex download litestar-org/litestar-piccolo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 943841d354bd6ffd190c246a4450ae8c71545947
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 943841d354bd6ffd190c246a4450ae8c71545947
│           └── chunk-001.nq.gz
├── blob
│   ├── 038758c2e70c42c5aca27050540e619ea1134ed5.nq.gz
│   ├── 10b1c9e45a1bb553f0932808977b58b255d5d4ce.nq.gz
│   ├── 164677e6677bf54e694968b0bd053222a968a583.nq.gz
│   ├── 1aaecc12639c2b115545582b1a03eee5dbed4688.nq.gz
│   ├── 21e868b549fc35aa71357d2c66e24e88c1f6d2e0.nq.gz
│   ├── 2a22f3ef2b0b7909bcde41e229917feabbba5cde.nq.gz
│   ├── 32ebbcc1ed05c3d9ccddd1fd8b9597e4d381ebe8.nq.gz
│   ├── 35d8df038aab51bf6fb2f3686dc85a1d8fce0be7.nq.gz
│   ├── 702ae6878143ce3c76e9c875d8e2225c3c3a7be5.nq.gz
│   ├── 730d7afabe7fd3562e534c073607b9c2e7a748da.nq.gz
│   ├── 736a066b2f9146b6e88c619cd0a8ce96836b37a1.nq.gz
│   ├── 78043efc045f6e9383957500ba5436aa7241f3ea.nq.gz
│   ├── 7bc7f50c6a7789e9e8a6aa95b131582662aef5bb.nq.gz
│   ├── 7ce4e529cd8c949b3fa02c3c892f8337e4fc88bb.nq.gz
│   ├── 8d0ef71a705069a55931cbc9ef73dccffef729d2.nq.gz
│   ├── 91ccd7f8160c018f2305248ceb9047e545b25d82.nq.gz
│   ├── 9ac31b4ee040cf47e148fbc7af33a90486ddf819.nq.gz
│   ├── a66afd5a8575be97ed8dca9753c96808d29d311c.nq.gz
│   ├── b0210ce0658f7a943e65f7cc183a3536563985d3.nq.gz
│   ├── b4491ff3676ad4ddab44598029f3dfdec778ffb6.nq.gz
│   ├── b56bcb476a67fa2564e5a0d59f65c95111180a69.nq.gz
│   ├── b5f8bebd567b71788a5b1a789a73002477fd5dfb.nq.gz
│   ├── bbb2c9299f4bd55db4dd9fc9287acc545b047713.nq.gz
│   ├── bbd440e7a11cd492aeadbc4fe999f354366866df.nq.gz
│   ├── bcc427694fe62b17fad4d2ebe902e51d5c01772f.nq.gz
│   ├── c950653f1ddab5af8e134fbd101b50eb77432225.nq.gz
│   ├── cc9a38dca70dad6f3fc6861e30b2f3b321ccb0b4.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── dbb401f81d07a15e4919ab526d7451559cda23ff.nq.gz
│   ├── dee862641c98000204e53297e799865ecc1bf69e.nq.gz
│   ├── def725abdf51cae9dad9d2daedcdb5829171d762.nq.gz
│   ├── e284c3da69fccdb6f6871bafd5a66bb8ebebd5c2.nq.gz
│   ├── e641790670ce638cb4ec224b8351f96c468eebaf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef1921377e37dd8397e89bced757f91fd0a63fc7.nq.gz
│   ├── f0a73bb14c1f096d673e24ecde4cf71cd21fd5e3.nq.gz
│   └── f4f5d1c291462ec21a7cfa9f69229d575390af94.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 943841d354bd6ffd190c246a4450ae8c71545947.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[litestar-org/litestar-piccolo](https://github.com/litestar-org/litestar-piccolo)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
