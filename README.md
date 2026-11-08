# Repolex Knowledge Graph of bentoml/BentoDiffusion

RDF knowledge graph data for [bentoml/BentoDiffusion](https://github.com/bentoml/BentoDiffusion), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/BentoDiffusion
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 41a42d606d73697ed9a7bb66c0d6fc879875db18
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 41a42d606d73697ed9a7bb66c0d6fc879875db18
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dca65973129819f3b53d5a23186fb1f4a1b6e54.nq.gz
│   ├── 1a2efecc8675cbc6236d83b29f0dd686dbeb7e40.nq.gz
│   ├── 1ea8ad8d84280f47d52ff2d6e78f1c1e84a5d747.nq.gz
│   ├── 21a998fd3f2e76ce9928575ef1ef31b03ca7a08b.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 362352db9c8ad70f5b01c2fe5c0809fef180b4d7.nq.gz
│   ├── 39b98b3190b9fdb30857d9ad56523a368f7638f5.nq.gz
│   ├── 49e2841dd5b28c471cf89ea484cf496256d61c1b.nq.gz
│   ├── 5a2f99a1aea76ffd875c1bf3a1a904397adb98ac.nq.gz
│   ├── 61002c659b1cf7bd6a1cb5c87417ff1ff949e51c.nq.gz
│   ├── 62abb6b0ba4b9d9539e7d6acdef5aa18c3a428b8.nq.gz
│   ├── 67a99ba18a0108fdc152b8dea2e5158cc3bee130.nq.gz
│   ├── 698ebdbdeca466cdab9ac71fdfe025c1d784d222.nq.gz
│   ├── 6ef234c4e7799677c0ba194459f0969ba699eb59.nq.gz
│   ├── 73883c094aef9202ffb810561af12bebaaa89918.nq.gz
│   ├── 7b2e3b920757ece63953fe4b8289737982390b55.nq.gz
│   ├── 7baabf0c05a42b8b584c9c3c07ae050e3fdfdae3.nq.gz
│   ├── 908b8ed556d4a052107602f8e3d81830ca5bc1d1.nq.gz
│   ├── 92afa22fd84964797c24ac50c6a69227c2534b99.nq.gz
│   ├── 9f99e480fdae06cfa8e7728b82c22f85dc6dff70.nq.gz
│   ├── a039af3bece82b1d96f771f1926419a85a20cdb8.nq.gz
│   ├── a168a948e89c1cea5d1d4d17d4965f1de1e2e568.nq.gz
│   ├── a4b09777dd7e8ba0f41738728ab5b0b96b87f137.nq.gz
│   ├── aae9445ae1059532ad4c4e729e43bc77baa6e7be.nq.gz
│   ├── c2ee3e5f671497ffc86c45cd74de9a9bf7b65fa3.nq.gz
│   ├── cd3ec71a83cd777e06a0f3d706c9cb2b44420b49.nq.gz
│   ├── d9cf1150b84cca06b20e7dcae3a5941ad67e1d87.nq.gz
│   ├── db502fefc74b3dc16f644114b155e8f682802be5.nq.gz
│   ├── e4807e6d4a35294929c974a64c2c35d5ab69b7a3.nq.gz
│   └── f57e7b4809a3cba30d028b7d8a19fb2882fc582c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 41a42d606d73697ed9a7bb66c0d6fc879875db18.nq.gz
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

[bentoml/BentoDiffusion](https://github.com/bentoml/BentoDiffusion)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
