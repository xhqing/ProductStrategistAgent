# ProductStrategistAgent 备忘录（超低频需求，比绿色紧急度还低）

> **功能定位（2026-08-19 用户立）**：本文件专门放「不那么紧急、没有明确完成时点」的备忘事项——优先级低于 TODO.md 的四级紧急度（🔴🟠🟡🟢）中最低的绿色紧急度。TODO.md 是「要尽快处理、要及时清空」的待办清单，**不设「长期备忘」分类**——备忘类内容一律放本文件，不污染待办清单的定位。
>
> - **放什么**：超低频需求、周期性 / 条件触发才需要做的事、没有排期压力的持续口径。
> - **不放什么**：要尽快处理的待办（进 TODO.md 对应紧急度分节）；已完成变更的记录（进 CHANGELOG.md）；当前规范的描述（进 SKILL.md / references）。
> - **条目格式**：与 TODO.md 一致——每条带记录时间戳（精确到分钟，`（记录：YYYY-MM-DD HH:MM）`）；条目触发条件满足、事情做完后移入**专属归档文件 `MEMO-archive.md`**（项目根，与 `TODO-archive.md` 平行——待办归档进 TODO-archive、备忘归档进 MEMO-archive，互不混放），或在本文件内更新状态 / 计数。
> - **触发时机**：相关场景出现时（做选品方案、看运营数据、规划引流打法时）由 AI 或用户主动翻本文件对照，不设自动提醒。

## 备忘条目

- [ ] **持续跟踪 `xai-org/x-algorithm`（X 推荐算法开源仓库）**（记录：2026-08-20 18:35）：一有 release / commit 更新立即分析新内容（`gh api repos/xai-org/x-algorithm/releases` 与 `commits`，建议每周一次），重点看打分权重、可见性过滤、召回机制的变化，从中提炼产品定位与运营方案调整，分析结果同步更新 `docs/product/hot-trend-ai-agent-money-system.md` §3.5 与 §5 运营手册。当前基线：2026-08-13 release（公开 blending weights 与 visibility filtering）。正确仓库是 `xai-org/x-algorithm`（2026 年 1 月首次开源），勿用 2023 年旧仓库 `twitter/the-algorithm`（已过时）。触发场景：每次做选品 / 引流 / 运营相关会话时顺手查一次。
- [ ] **持续跟踪 `deepseek-ai/deepseek-harness`（DSH）版本节点——每波节点都是桥接内容的流量窗口**（记录：2026-08-20 22:01）：DSH 2026-08-13 发布（developer preview，v0.1.0-rc.x，两天破 95k-112k stars），跟踪 `gh api repos/deepseek-ai/deepseek-harness/releases`，关注三类节点：① 正式版发布（v1.0，预示生态稳定、第二波流量高峰）；② 插件生态里程碑（官方插件商店 / 生态计数，预示「组织缺口」话题再升温）；③ 破坏性变更公告（预示迁移潮讨论 + 第三波流量）。每个节点出现即触发桥接帖：「DSH 让装插件更容易，不帮你把插件组织成团队——那是难的部分」（强化 Fleet Playbook「组织 > 囤积」卖点，只蹭流量、不卖 DSH 品牌付费内容，边界见报告 §1 DSH 处置决策）。触发场景：每次做选品 / 引流 / 运营相关会话时顺手查一次（与 x-algorithm 同批）。
