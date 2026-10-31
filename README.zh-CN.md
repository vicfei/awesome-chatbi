<div align="center">

# Awesome ChatBI

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)
[![Radar](https://github.com/vicfei/awesome-chatbi/actions/workflows/radar.yml/badge.svg)](https://github.com/vicfei/awesome-chatbi/actions/workflows/radar.yml)
[![Last commit](https://img.shields.io/github/last-commit/vicfei/awesome-chatbi)](https://github.com/vicfei/awesome-chatbi/commits)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**与数据对话的系统与实践地图 —— ChatBI / text2SQL / 智能问数：
产品、语义层、研究、基准，以及诚实的选型信号（维护状态 / 许可证）。**

[English](README.md) · 简体中文

🤖 **每日 arXiv 雷达：** [docs/radar.md](docs/radar.md) —— 每天自动刷新。

</div>

---

## 为什么做这个列表

text2SQL 的论文侧已被三家守好：[NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook)、[Awesome-LLM-based-Text2SQL](https://github.com/DEEP-PolyU/Awesome-LLM-based-Text2SQL)、[Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL)（论文请看它们）。**但系统侧没人画地图**：团队真正部署的 ChatBI 产品、语义层平台、智能问数系统——以及它们还在不在维护。

这就是本列表。每个系统条目都带**维护状态**和**许可证核查**，因为在这个类目里，星数最高的两个开源项目都已停更，而两个最好用的之一用的是非 OSI 许可。论文归在位者，系统、基准与选型信号归这里。

## 三大流派

| 流派 | 思路 | 代表 |
|---|---|---|
| **RAG 检索派** | 检索 DDL / 文档 / 历史 SQL，再生成 | vanna、SQLBot |
| **语义治理派** | 把业务含义（指标、join）建模成受治理的层，供 agent 消费 | WrenAI、DB-GPT |
| **算力扩展派** | 测试时扩展 + 微调开源模型，抬准确率天花板 | Agentar-Scale-SQL、CHASE-SQL |

前沿正在从"生成更好的 SQL"转向"**给 agent 供给更好的数据**"——Git 里受治理的语义层、MCP 原生接入、技能化分发（见下方 WrenAI 的转型）。

## 与姊妹列表的分界

一个矩阵，按 agent 工作的对象分：

| 层 | 列表 |
|---|---|
| **代码**（SWE 可验证的工作） | [awesome-self-improving-coding-agents](https://github.com/vicfei/awesome-self-improving-coding-agents) |
| **模型与数据的生产**（训练、蒸馏、合成数据） | [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml) |
| **数据的服务** —— 问数、查询、治理 | **awesome-chatbi**（本列表） |
| **技能与组织** | [awesome-ai-native](https://github.com/vicfei/awesome-ai-native) |

## 从这里读起

| # | 工作 | 为什么 |
|---|---|---|
| 1 | [WrenAI](https://github.com/Canner/WrenAI) | 类目去向的最清晰样本：受治理的语义层，供你已在用的 agent 消费。 |
| 2 | [vanna](https://github.com/vanna-ai/vanna) | 经典 RAG 配方：DDL + 文档 + 历史 SQL 训练、检索、生成。（注意状态列。） |
| 3 | [SQLBot](https://github.com/dataease/SQLBot) | 中文 ChatBI 产品形态的完整样本：RAG + 术语库 + 权限 + MCP。 |
| 4 | [BIRD 榜单](https://bird-bench.github.io/) · [论文](https://arxiv.org/abs/2305.03111) | 研究前沿竞逐的那把尺子。 |
| 5 | [Agentar-Scale-SQL](https://github.com/antgroup/Agentar-Scale-SQL) | 算力扩展派的旗舰：编排式测试时扩展拿下 BIRD 第一。 |

## 系统 —— 国际

| 系统 | 是什么 | 状态（2026-11） |
|---|---|---|
| [vanna](https://github.com/vanna-ai/vanna) · MIT | RAG text2SQL：DDL/文档/SQL 语料 + 智能体检索；类目内星数最高的开源项目。 | ⚠️ 2026-02 后无提交 |
| [pandas-ai](https://github.com/sinaptik-ai/pandas-ai) · MIT | notebook 里的对话式数据分析（SQL、CSV、parquet）。 | ⚠️ 2025-10 后无提交 |
| [DB-GPT](https://github.com/eosphoros-ai/DB-GPT) · MIT | 全栈智能体数据平台：AWEL 工作流、text2SQL、RAG、多智能体、微调。 | ✅ 活跃 |
| [WrenAI](https://github.com/Canner/WrenAI) · AGPL 系 | **给 agent 用的** GenBI 引擎：受治理语义层以可评审的 YAML/Markdown 放在你的 Git 里；agent 经 MCP 或 `npx skills add` 消费。 | ✅ 活跃；已转向 agent 优先 |
| [dash](https://github.com/agno-agi/dash) | 基于系统工程原语的自学习数据智能体。 | ✅ 活跃 |

## 系统 —— 中文智能问数生态

| 系统 | 是什么 | 状态（2026-11） |
|---|---|---|
| [SQLBot](https://github.com/dataease/SQLBot) · GPL 系 + Logo 条款 | 飞致云/DataEase 出品的 ChatBI：RAG + 术语库 + SQL 示例校准；工作空间隔离、细粒度数据权限、MCP，可嵌入 n8n/Dify/MaxKB；“越问越准”反馈闭环。 | ✅ 活跃；注意非 OSI 许可 |
| [XiYan-SQL](https://github.com/XGenerationLab/XiYan-SQL) · [论文](https://arxiv.org/abs/2507.04701) | 阿里的多生成器集成 NL2SQL 框架。 | ⚠️ 2026-05 后无提交 |

## 云厂商信号

- [腾讯云 DataBuddy](https://www.tencentcloud.com/products/databuddy)（2026 年 9 月国际发布）—— 首个以"agent 原生 Data+AI 平台"为名的云大厂产品：湖仓之上的工程/治理/分析三智能体，统一语义层 + 细粒度权限 + MCP 原生工具，"copilot → autopilot → 多智能体"路线。所有性能数字（80% 降幅、5–10 倍人效）均为**厂商口径**。闭源；作为类目的云在位形态收录。

## 研究前沿

| 工作 | 展示了什么 |
|---|---|
| [Agentar-Scale-SQL](https://github.com/antgroup/Agentar-Scale-SQL) · [论文](https://arxiv.org/abs/2509.24403) —— 蚂蚁集团 | 以编排式测试时扩展拿下 BIRD 第一（81.67% EX），开源 32B 模型；续作 [FineStep](https://arxiv.org/abs/2605.04719) 做工具集成 text2SQL 的步级功劳分配。仓库 2026-05 后静默——企业研究仓的典型节奏。 |
| [CHASE-SQL](https://arxiv.org/abs/2410.01943) | 多路径推理 + 偏好优化的候选选择。 |

## 经典方法（2023–24 一代）

后来的系统都在悄悄借用这些论文：

| 年份 | 工作 | 贡献 |
|---|---|---|
| 2023 | [DIN-SQL](https://arxiv.org/abs/2304.11015) | 把 text2SQL 分解为子任务并自我纠错。 |
| 2023 | [DAIL-SQL](https://arxiv.org/abs/2308.15363) | 系统化的提示/设计空间评测，重置了全领域基线。 |
| 2023 | [C3](https://arxiv.org/abs/2307.07306) | 零样本 text2SQL：清晰提示 + 上下文校准 + 一致性选择。 |
| 2023 | [MAC-SQL](https://arxiv.org/abs/2312.11242) | 多智能体协作：分解者/选择者/修正者三角色。 |
| 2024 | [CodeS](https://arxiv.org/abs/2402.16347) | 为 text2SQL 而生的开源代码模型——微调模型派的早期锚点。 |

## 基准

| 基准 | 度量什么 | 链接 |
|---|---|---|
| **BIRD** | 大规模、数据库落地、脏而大的真实 schema | [论文](https://arxiv.org/abs/2305.03111) · [榜单](https://bird-bench.github.io/) |
| **Spider** | 经典跨域 text2SQL 测试集（2018） | [论文](https://arxiv.org/abs/1809.08887) · [代码](https://github.com/taoyds/spider) |
| **NL2SQL360** | "Dawn of NL2SQL"（VLDB'24）谱系的基准与分析平台 | [代码](https://github.com/HKUSTDial/NL2SQL360) |

## 实践注记（论文列表不告诉你的部分）

1. **这个类目里星数会骗人。** 星数最高的两个开源项目（pandas-ai 约 23.9k、vanna 约 23.8k）已停更 9–12 个月；更小但活跃的项目（SQLBot、dash）每周都在发版。看 `pushed_at`，别看星数。本列表的状态列带日期——欢迎提 PR 更新。
2. **许可证陷阱。** SQLBot 的 FIT2CLOUD 许可是 GPLv3 **加** Logo 不可修改条款（非 OSI）；WrenAI 为 AGPL 系。MIT 选项：vanna、pandas-ai、DB-GPT。
3. **类目正在向平台收敛。** 幸存者要么有公司输血（Canner、飞致云、eosphoros），要么云原生化（DataBuddy）。独立开源的 chat-with-data 是功能不是生意——预期更多停更，自建 vs 采购的权重据此调整。

## 🤖 雷达

`docs/radar.md` 由 [`scripts/radar.py`](scripts/radar.py)（GitHub Actions，[workflow](.github/workflows/radar.yml)）基于 arXiv 新提交列表**每天**重建，按 text2SQL / NL2SQL / ChatBI / data agent 标题关键词过滤。欢迎提 PR 调整关键词。

## 相邻列表

**论文侧（互补的在位者）：**

- [HKUSTDial/NL2SQL_Handbook](https://github.com/HKUSTDial/NL2SQL_Handbook) —— 持续更新的学术手册
- [DEEP-PolyU/Awesome-LLM-based-Text2SQL](https://github.com/DEEP-PolyU/Awesome-LLM-based-Text2SQL) —— TKDE 2025 综述配套
- [eosphoros-ai/Awesome-Text2SQL](https://github.com/eosphoros-ai/Awesome-Text2SQL) —— 教程与论文（2026-01 后停更）
- [HKUSTDial/awesome-data-agents](https://github.com/HKUSTDial/awesome-data-agents) —— data agent 论文列表

**姊妹列表（四层矩阵）：**

- [awesome-self-improving-coding-agents](https://github.com/vicfei/awesome-self-improving-coding-agents) —— 代码层
- [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml) —— 模型与数据生产层
- [awesome-ai-native](https://github.com/vicfei/awesome-ai-native) —— 组织层

## 贡献

欢迎 PR —— 见 [CONTRIBUTING.md](CONTRIBUTING.md)。门槛：一手来源、一句话说明是什么、**带日期的维护状态**、非 OSI 许可必须注明、厂商口径必须标注。

## 许可

[CC0 1.0](LICENSE) —— 公共领域。
