# Repolex Knowledge Graph of google-deepmind/chex

RDF knowledge graph data for [google-deepmind/chex](https://github.com/google-deepmind/chex), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/chex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 02bfaa78564cdcac0bf498f40d6e39edeebacd36
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 02bfaa78564cdcac0bf498f40d6e39edeebacd36
│           └── chunk-001.nq.gz
├── blob
│   ├── 0108a27ea8c48bd9c16fd86a833e4713a52d11a5.nq.gz
│   ├── 107d25c46091a9d776b9fabb9244fd708b2148e7.nq.gz
│   ├── 1671f233be2e8394b8a83de0ef7812f6bab62756.nq.gz
│   ├── 17b423207e6e98f1a33c89565ba4d5b04b33db85.nq.gz
│   ├── 186989dd754da99777ae9e92e3bb8b9f254fa7e1.nq.gz
│   ├── 1d72caf97071462ba0dd4aa7f6766bd012755ead.nq.gz
│   ├── 21c3c87ed79d4d86fd5b952839a7f5f16332fbfa.nq.gz
│   ├── 25cb00f80e209681514c3f2a11853f18b10580ae.nq.gz
│   ├── 28704d7c31278a49ebf673798aa432aff1fb6eb1.nq.gz
│   ├── 293b2475d190777a5c307c52662e0610f7306b3e.nq.gz
│   ├── 2a3fb8256139823c6648e1bbfe842d269e5a4756.nq.gz
│   ├── 33c1dd236af146f471cbb116063551e0f25f902f.nq.gz
│   ├── 37912584bc289059f4a64a314e09742c84968137.nq.gz
│   ├── 3db4914813f96aeac00cdfb2234c9590e8570aee.nq.gz
│   ├── 3ead307d1c8fea3834d05b82227514cd0ca22b1e.nq.gz
│   ├── 5812d2a9212f562eb93a9f0bb424f22e51deebcf.nq.gz
│   ├── 653f00dfdc79c3137776f517d28ceef848f44996.nq.gz
│   ├── 662d53aed87f65d275a7ade3ae49199782951234.nq.gz
│   ├── 81523679eb66d12225e7d41cddd21816de99f181.nq.gz
│   ├── 8adfc62d8a10ab10da6b8fac3def6877a76063a4.nq.gz
│   ├── 8cc5474eae2cc85dab553ce85a60130a675ca00b.nq.gz
│   ├── 8d8438dc36f2421763ac20fbc95b8a1ec5c566db.nq.gz
│   ├── 97a299f23db54e681c797ad127fa0228a14f6faf.nq.gz
│   ├── a248e26a552c49fe8e6bff1d30eb03ca026a4756.nq.gz
│   ├── a6ac3f04600d7bc59713d324d60061471aa7adf2.nq.gz
│   ├── b235f7e2f9111548b621c0ffa9c4102f27966206.nq.gz
│   ├── b3ca14a5e841c42037cd7e59d16b55dbbdcf7535.nq.gz
│   ├── b70985e6acf918eef71452c276f6229ae5bfe702.nq.gz
│   ├── be7a0607d0a818a8e4d78b30903df260c33c9134.nq.gz
│   ├── bf4eb2dd08db294a7be9d129e175600698150a2d.nq.gz
│   ├── c6da0777d2f02963f09b9ead0939024dd9a8cdfb.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── ec82e623f09ff341c76e507421f32ee5542557fa.nq.gz
│   ├── f1a17854590811c812917ad04eec1145a63f74cb.nq.gz
│   ├── f416b7e51f07e233a4fe42c8f998a3b8c14399e6.nq.gz
│   ├── fab3e643c6351764d394614f1896f303e71c0e1d.nq.gz
│   └── fd3edb85dff4e284c43b4fa625e42512de2050fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 02bfaa78564cdcac0bf498f40d6e39edeebacd36.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[google-deepmind/chex](https://github.com/google-deepmind/chex)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
