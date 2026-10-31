# Contributing

Thanks for keeping this list sharp. 谢谢帮助维护本列表。中文说明在下半部分。

## The bar for an entry

1. **Primary sources only.** Link the official repo, the arXiv abs page, or the official product page. No aggregators, no tweets, no secondhand summaries.
2. **One line on what it is** — the school it belongs to (RAG retrieval / semantic governance / compute scaling) helps readers navigate.
3. **A dated maintenance status.** This list's core value is honesty about whether systems still live: check `pushed_at`, note "✅ Active" or "⚠️ No pushes since YYYY-MM" with the observation date.
4. **License called out when non-OSI** (GPL-family, AGPL-family, custom clauses) — enterprise readers need this before adopting.
5. **Vendor claims must be labeled.** Cloud/product performance numbers ("80% reduction", "5–10×") are recorded as vendor claims, never as established results.
6. **Scope:** systems, benchmarks, and practice signals for talking to / querying / governing data. Papers in bulk belong with the handbook lists in [Related lists](README.md#related-lists); producing models/datasets belongs in [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml).

## Checklist for PRs

- [ ] Added to the right section in **both** `README.md` and `README.zh-CN.md` (keep the two in sync).
- [ ] Link resolves (no 404) — yes, please actually click it.
- [ ] Maintenance status dated; license noted if non-OSI; vendor claims labeled.
- [ ] One-line description, English in `README.md`, 中文在 `README.zh-CN.md`。

Keyword tuning for the [radar](scripts/radar.py) is also welcome — keep precision high.

## 贡献指南（中文）

**收录门槛：**

1. **只链一手来源**——官方仓库、arXiv 页面或官方产品页；不收聚合站、推特转述或二手总结。
2. **一句话说明是什么**——注明流派（RAG 检索 / 语义治理 / 算力扩展）更有导航价值。
3. **带日期的维护状态。** 本列表的核心价值是对"系统还活着吗"的诚实：查 `pushed_at`，写"✅ 活跃"或"⚠️ YYYY-MM 后无提交"并注明观察日期。
4. **非 OSI 许可必须注明**（GPL 系、AGPL 系、自定义条款）——企业读者选型前需要这个。
5. **厂商口径必须标注。** 云/产品的性能数字（"80% 降幅""5–10 倍"）一律记为 vendor claims，不作既成事实。
6. **范围**：与数据对话/查询/治理的系统、基准与实践信号。批量论文请投[相邻列表](README.zh-CN.md#相邻列表)中的手册类清单；生产模型/数据请投 [awesome-agentic-ml](https://github.com/vicfei/awesome-agentic-ml)。

**PR 检查项：** 中英两个 README 同步更新；链接实际点开过；维护状态带日期、非 OSI 许可注明、厂商口径标注；一句话描述中英各一份。也欢迎调整[雷达](scripts/radar.py)关键词——保持高精度。
