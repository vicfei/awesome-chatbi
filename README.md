<div align="center">

# Awesome ChatBI

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)
[![Radar](https://github.com/vicfei/awesome-chatbi/actions/workflows/radar.yml/badge.svg)](https://github.com/vicfei/awesome-chatbi/actions/workflows/radar.yml)
[![Last commit](https://img.shields.io/github/last-commit/vicfei/awesome-chatbi)](https://github.com/vicfei/awesome-chatbi/commits)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**The systems & practice map of talking to your data —
ChatBI / text2SQL / 智能问数: products, semantic layers, research, benchmarks,
and honest maintenance signals for choosing one.**

English · [简体中文](README.zh-CN.md)

🤖 **Daily arXiv radar:** [docs/radar.md](docs/radar.md) — auto-refreshed every day.

</div>

---

## Why this list

The paper side of text2SQL is well served: [NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook), [Awesome-LLM-based-Text2SQL](https://github.com/DEEP-PolyU/Awesome-LLM-based-Text2SQL), and [Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) catalogue the literature. **Nobody maps the systems side**: the ChatBI products, semantic layers, and 智能问数 platforms teams actually deploy — or whether they're still being maintained.

That's this list. Every system entry carries a **maintenance status** and a **license check**, because in this category the two most-starred open-source projects are both dormant, and two of the most useful ones ship non-OSI licenses. Papers go to the incumbents above; systems, benchmarks, and selection signals live here.

## Three schools

| School | Idea | Representatives |
|---|---|---|
| **RAG retrieval** | Retrieve DDL / docs / past SQL, then generate | vanna, SQLBot |
| **Semantic governance** | Model the business meaning (metrics, joins) as a governed layer agents consume | WrenAI, DB-GPT |
| **Compute scaling** | Test-time scaling + fine-tuned open models to push the accuracy ceiling | Agentar-Scale-SQL, CHASE-SQL |

The frontier is moving from "generate better SQL" to **"serve agents better data"** — governed semantic layers in Git, MCP-native access, skills-based distribution (see WrenAI's pivot below).

## Boundary with sibling lists

One matrix, split by what the agent works on:

| Layer | List |
|---|---|
| **Code** (SWE-verifiable work) | [awesome-self-improving-coding-agents](https://github.com/vicfei/awesome-self-improving-coding-agents) |
| **Model & data production** (training runs, distillation, synthetic data) | [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml) |
| **Data serving** — talking to, querying, and governing data | **awesome-chatbi** (this list) |
| **Skills & organization** | [awesome-ai-native](https://github.com/vicfei/awesome-ai-native) |

## Start here

| # | Work | Why |
|---|---|---|
| 1 | [WrenAI](https://github.com/Canner/WrenAI) | The clearest view of where the category is going: a governed semantic layer consumed by the agents you already use. |
| 2 | [vanna](https://github.com/vanna-ai/vanna) | The canonical RAG recipe: train on DDL + docs + past SQL, retrieve, generate. (Mind the status column.) |
| 3 | [SQLBot](https://github.com/dataease/SQLBot) | The Chinese ChatBI product pattern end-to-end: RAG + 术语库 + permissions + MCP. |
| 4 | [BIRD leaderboard](https://bird-bench.github.io/) · [paper](https://arxiv.org/abs/2305.03111) | The yardstick the research frontier competes on. |
| 5 | [Agentar-Scale-SQL](https://github.com/antgroup/Agentar-Scale-SQL) | The compute-scaling school's flagship: #1 on BIRD via orchestrated test-time scaling. |

## Systems — international

| System | What it is | Status (Nov 2026) |
|---|---|---|
| [vanna](https://github.com/vanna-ai/vanna) · MIT | RAG text2SQL: DDL/docs/SQL training corpus + agentic retrieval; the most-starred OSS in the category. | ⚠️ No pushes since Feb 2026 |
| [pandas-ai](https://github.com/sinaptik-ai/pandas-ai) · MIT | Conversational analysis over dataframes/datalakes (SQL, CSV, parquet) in notebooks. | ⚠️ No pushes since Oct 2025 |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) · MIT | Full-stack agentic data platform: AWEL workflows, text2SQL, RAG, multi-agent, fine-tuning. | ✅ Active |
| [WrenAI](https://github.com/Canner/WrenAI) · AGPL-family | GenBI engine **for agents**: governed semantic layer as reviewable YAML/Markdown in your Git; agents consume it via MCP or `npx skills add`. | ✅ Active; pivoted to agent-first |
| [dash](https://github.com/agno-agi/dash) | Self-learning data agent built on systems-engineering primitives. | ✅ Active |

## Systems — Chinese 智能问数 ecosystem

| System | What it is | Status (Nov 2026) |
|---|---|---|
| [SQLBot](https://github.com/dataease/SQLBot) · GPL-family + logo clause | ChatBI by the DataEase/飞致云 team: RAG + term dictionaries + SQL example calibration; workspace isolation, fine-grained data permissions, MCP + embeddable into n8n/Dify/MaxKB. “越问越准” feedback loop. | ✅ Active; note the non-OSI license |
| [XiYan-SQL](https://github.com/XGenerationLab/XiYan-SQL) · [paper](https://arxiv.org/abs/2507.04701) | Alibaba's multi-generator ensemble framework for NL2SQL. | ⚠️ No pushes since May 2026 |

## Cloud signal

- [Tencent Cloud DataBuddy](https://www.tencentcloud.com/products/databuddy) (international launch Sep 2026) — the first hyperscaler "agent-native Data+AI platform": engineering / governance / analytics agents over a lakehouse, unified semantic layer + fine-grained access + MCP-native tools, "copilot → autopilot → multi-agent" roadmap. All performance figures (80% reductions, 5–10×) are **vendor claims**. Closed-source; tracked here as the incumbent-cloud shape of the category.

## Research frontier

| Work | What it shows |
|---|---|
| [Agentar-Scale-SQL](https://github.com/antgroup/Agentar-Scale-SQL) · [paper](https://arxiv.org/abs/2509.24403) — Ant Group | #1 on BIRD (81.67% EX) via orchestrated test-time scaling; open 32B model. Follow-up [FineStep](https://arxiv.org/abs/2605.04719) does step-level credit assignment for tool-integrated text2SQL. Repo quiet since May 2026 — corporate-research rhythm. |
| [CHASE-SQL](https://arxiv.org/abs/2410.01943) | Multi-path reasoning + preference-optimized candidate selection. |

## Classic methods (the 2023–24 generation)

The papers every newer system quietly borrows from:

| Year | Work | Contribution |
|---|---|---|
| 2023 | [DIN-SQL](https://arxiv.org/abs/2304.11015) | Decompose text2SQL into sub-tasks with self-correction. |
| 2023 | [DAIL-SQL](https://arxiv.org/abs/2308.15363) | The systematic prompt/design-space evaluation that reset the field's baselines. |
| 2023 | [C3](https://arxiv.org/abs/2307.07306) | Zero-shot text2SQL via clear prompting, contextual calibration, consistency selection. |
| 2023 | [MAC-SQL](https://arxiv.org/abs/2312.11242) | Multi-agent collaboration: decomposer / selector / refiner roles. |
| 2024 | [CodeS](https://arxiv.org/abs/2402.16347) | Open-source code models built for text2SQL — the fine-tuned-model school's early anchor. |

## Benchmarks

| Benchmark | What it measures | Link |
|---|---|---|
| **BIRD** | Large-scale, database-grounded text2SQL with dirty, huge real schemas | [paper](https://arxiv.org/abs/2305.03111) · [leaderboard](https://bird-bench.github.io/) |
| **Spider** | The classic cross-domain text2SQL test set (2018) | [paper](https://arxiv.org/abs/1809.08887) · [code](https://github.com/taoyds/spider) |
| **NL2SQL360** | Benchmark + analysis platform from the "Dawn of NL2SQL" (VLDB'24) line | [code](https://github.com/HKUSTDial/NL2SQL360) |

## Practice notes (the part paper lists don't give you)

1. **Star count misleads in this category.** The two most-starred OSS projects (pandas-ai ~23.9k, vanna ~23.8k) have been dormant for 9–12 months; smaller active projects (SQLBot, dash) ship weekly. Check `pushed_at`, not stars. This list's status column is dated — PRs to update it are welcome.
2. **License traps.** SQLBot's FIT2CLOUD license is GPLv3 **plus** a no-logo-modification clause (non-OSI); WrenAI is AGPL-family. MIT options: vanna, pandas-ai, DB-GPT.
3. **The category is consolidating into platforms.** Survivors are company-backed (Canner, 飞致云, eosphoros) or cloud-native (DataBuddy). Standalone OSS chat-with-data is a feature, not a business — expect more dormancy, and weight your build-vs-buy accordingly.

## 🤖 Radar

`docs/radar.md` is regenerated **daily** by [`scripts/radar.py`](scripts/radar.py) (GitHub Actions, [workflow](.github/workflows/radar.yml)) from arXiv new-submission listings, keyword-filtered for text2SQL / NL2SQL / ChatBI / data-agent titles. Tune the keywords via PR.

## Related lists

**Paper side (complementary incumbents):**

- [HKUSTDial/NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook) — the continuously-updated academic handbook
- [DEEP-PolyU/Awesome-LLM-based-Text2SQL](https://github.com/DEEP-PolyU/Awesome-LLM-based-Text2SQL) — TKDE 2025 survey companion
- [eosphoros-ai/Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) — tutorials & papers (dormant since Jan 2026)
- [HKUSTDial/awesome-data-agents](https://github.com/HKUSTDial/awesome-data-agents) — data-agent paper list

**Sibling lists (the four-layer matrix):**

- [awesome-self-improving-coding-agents](https://github.com/vicfei/awesome-self-improving-coding-agents) — code layer
- [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml) — model & data production layer
- [awesome-ai-native](https://github.com/vicfei/awesome-ai-native) — organization layer

## Contributing

PRs welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). The bar: primary sources, one line on what it is, **a dated maintenance status**, and license called out when non-OSI. Vendor claims must be labeled as such.

## License

[CC0 1.0](LICENSE) — public domain.
