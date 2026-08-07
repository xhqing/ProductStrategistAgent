# Changelog

## [1.0.0] - 2026-08-07

- 初始版本：Scout 选品策略师 Agent 项目。核心职责为产出《机会研判报告》（热点 → 选品 → 市场调研 → 竞品分析 → 盈利模式 → 引流销售渠道建议），作为数字产品销售流水线的研判入口。
- 内置能力：`hot-trend`（全球热点扫描与选品）、`anysearch` / `find-skill`（通用搜索与技能发现）。
- 项目标配：README 中英双语 + LOGO + 徽章 + 版权署名段；MIT 许可证；`VERSION` 1.0.0。
- 移除 `.claude/rules/` 下与全局 `~/.claude/rules/` 逐字节重复的 3 个通用规则文件（file-operation-priority-rules.md、tmp-dir-for-artifacts.md、verify-before-report.md）：这些规则已由全局加载、项目副本属于冗余，删除后仅保留项目专属规则（available-channels.md、passive-income-only.md），避免项目内重复维护。
