# Changelog

## [Unreleased]

### 变更（Git 漫画书生产任务交接 Wright：T2 已写入其 TODO.md，流水线进入生产环节）

- **为什么改**：用户裁定「让 Wright 开干」，按 2026-08-20 定下的交接机制（生产任务直接写入 Wright 项目 TODO.md，Wright 会话开工读 TODO 即获完整指令，用户无需当信使），本报告进入生产交接。
- **改了什么**：ProductProducerAgent `TODO.md` 新增 T2 生产任务（本仓报告 `artifacts/git-comic-book-report.md` 为唯一权威输入）——范围限定 20 页英文试读版（先验证后全本）、中文分镜定稿后翻译嵌字、场景驱动五命令极简主义、同步产出 Git-Comic-Mini 图卡；验收线（非技术读者 10 分钟翻完能复述 / 画风跨页一致 / 英文无语法硬伤）与产物 product_id 要求均写入；其 CHANGELOG 已另记。全本任务等试读验证结果再派。

### 变更（Git 漫书报告补充版本顺序决策：英文版先行验证、中文版跟进）

- **为什么改**：用户追问「先做英文试读版还是中文试读版好」，补一轮中文市场调研（国内 vibe coding 现状、中文平台 git 学习需求、小红书技术内容生态）后裁定：英文先行。核心依据是国内 vibe coding 起步比海外晚约一年、2026 年才迎来产品集中爆发期（钛媒体 2026-08）——大量用户还在工具尝鲜阶段、尚未密集踩到 git 的坑，此时中文验证容易出「假阴性」（无信号≠产品不行，可能是市场还没痛）；而海外痛点已被内容生态反复验证，试读验证的是「漫画形态是否比长文更有转化」这一干净信号；且主力收入市场在英文（$14.9 vs ¥29-49）、英文竞争窗口在收窄（Leanpub 故事书已出现）。
- **改了什么**：`artifacts/git-comic-book-report.md`——① §2 候选 1 新增「版本顺序（2026-09-19 补充决策）」块（四条理由：痛点成熟度时间差、验证对象应为主力收入市场、英文窗口收窄、一套分镜双语出稿的制作流程）；② §6 引流打法标注发布顺序（英文先发验证、中文跟进）；③ 来源附录补中文市场两源（钛媒体 vibe coding 市场报道、小红书 Red Skill 上线 qbitai/36kr）。

### 新增（机会研判报告：Git 漫画书面向 vibe coding 非技术用户，artifacts/ 目录首份报告）

- **为什么改**：用户提问「把 git 使用写成漫画书让普通人和小学生都能懂，有市场吗？值得做吗」，按产物契约产出《机会研判报告》。经三轮联网调研（vibe coding 市场与人群、漫画教技术形态先例、竞品与免费替代品、电子书收入先例）交叉验证后给出结论：有市场、值得做，但主力客群应定为非技术 vibe coding 成人，「小学生也能看懂」作难度锚点而非目标客群。
- **改了什么**：新建 `artifacts/` 目录与 `artifacts/git-comic-book-report.md`（trend_id: TR-vibecoding-nontech-2026；product_id: Git-Comic-v1）。报告含八节：热点（vibe coding 成长期后段、63% 用户非开发者）、选品建议（漫画式电子书主书 $14.9 + 图卡包 $4.9 + 后续系列）、市场调研、竞品分析（英文/中文市场无漫画形态 git 书直接竞品，日本わかばちゃん与英文 Manga Guide 系列验证形态可行）、盈利模式（保守 $685/月至乐观 $6,850/月测算，标注收入方差风险）、引流销售渠道（X 漫画 thread / Instagram 图卡 / 小红书中文版直售 / YouTube，上架 Payloadz+PayPal）、风险与对策、下游交接。

### 新增（.pi/skills 软链接指向 .claude/skills，多 harness 共享 skills）

- **为什么改**：用户 2026-09-18 要求建立软链接。pi 等 harness 从项目 `.pi/skills/` 读取项目级 skills，而本项目内置 skill（hot-trend）放在 `.claude/skills/`；软链接让 pi 会话直接复用同一份 skills，无需维护两份副本，也符合 v3.3「定位去 CC 绑定、方法论跨 harness」的方向（事实层与能力层对多 harness 开放）。
- **改了什么**：新建目录 `.pi/`，内建软链接 `skills -> ../.claude/skills`（相对路径，仓库移动 / clone 后仍有效）。已验证经链接可正常读取 hot-trend/SKILL.md。

### 变更（v3.3 产品定位去 Claude Code 绑定：通称 AI agents，组织方法论跨 harness）

- **为什么改**：用户 2026-09-14 指示「不要强调 Claude Code，其它 harness 也能用」。产品卖点本体是组织方法论（角色 / 契约 / 接力 / 沉淀），天然跨 harness；多底座市场已被验证（CC / Codex / Cursor / Gemini CLI / Copilot 均支持 skills，DSH 爆火证明插件生态在扩散），绑死 CC 等于把非 CC 用户挡在门外；与「国内 CC 口碑差、不能国内强调 CC」的用户判断同向。v3.1 模块 7 已埋跨 harness 伏笔，本次升格为产品定位原则。
- **改了什么**（2026-09-14）：`docs/product/hot-trend-ai-agent-money-system.md`——① §0 新增「产品定位去 CC 绑定（v3.3）」块，固化执行边界「定位层去 CC、事实层留 CC、运营层降位蹭流量」；② 英文主标题 `20 Claude Code Agents` → `20 AI Agents`（定名块同步）；③ 关键词重排：主词改 `agent skills` / `AI agent team` / `how to organize AI agents`，CC 系词降长尾（注明蹭流量不作定位），hashtag `#ClaudeCode` 移末位；④ §5 主攻平台描述改写（旧逻辑「渠道与卖点关键词都用 CC」废弃，新逻辑「蹭标签流量 ≠ 产品自我定位」）；⑤ 教程 thread 文案两处 `How I turned Claude Code into a company` → `How I turned 20 AI agents into a company`；⑥ Payloadz 上架标签去 Claude Code；⑦ §3.5 主题一致性、§2 关键词行同步通称化；⑧ 模块 2 Role Templates 补各 harness 配置文件名映射（`CLAUDE.md` / `AGENTS.md` / `.cursorrules` 等，五段式结构同构）；⑨ 模块 7 从「一节前瞻内容」升格为贯穿标题 / 关键词 / 文案 / 标签的定位原则。
- **边界**：事实层保留 CC——热点数据（多 harness 并列陈述）、付费锚点（CC 订阅价）、生产流程（本地 CC 实测）、素材源（CLAUDE.md 模板）、回复大号流量池列举；运营层 `#ClaudeCode` 标签与 CC 长尾搜索词保留但降位（流量真实存在）。产品名 The Agent Team Playbook 无 CC 字样、`product_id: Team-Playbook-v3` 均不变（定位微调非本体变化）。下游 ProductProducerAgent TODO 的 CLAUDE.md 引用均为素材源路径（事实层），无需同步。

### 变更（v3.2 团队规模 14 → 20 全文同步：文案数字与仓库事实对齐）

- **为什么改**：用户 2026-09-14 指出系统持续迭代、团队已从 14 个 agent 扩至 20 个（全局注册表三小组 + 直属岗位结构成型），报告通篇仍写 14。数字是卖点核心资产（「规模感由数字传达」）、且买家漏斗以「对照 GitHub 验证」为核心机制——文案数字与仓库事实不一致即信任折损（同 2026-08-21 fleet → team 改名逻辑）；产品未生产、营销未发，此刻同步成本最低。
- **改了什么**（2026-09-14）：`docs/product/hot-trend-ai-agent-money-system.md`——① §0 新增「团队规模同步（v3.2）」块：数字维护规则（以全局注册表为准、扩员后同步、英文文案用精确数字不用「20+」）、叙事资产（14 → 20 且组织不乱是方法论有效的活证明，「grew from 14 to 20」可作内容钩子）、素材增量（三小组结构成为模块 1 / 4 新底料）；② 正文现行措辞 12 处 14 → 20（§0 本体描述、§1 证据、§3 过程证明、§4 模块 4 组织学 / 英文标题 / 封面视觉、§5 拆解帖与 DSH 桥接帖及英文首发文案、§7 风险）；③ 头部生成日期行标注 v3.2 增补。
- **边界**：头部版本沿革行「v3 换产品本体：14-agent team」与同步块内「生成时为 14 个 / 14 人时代」属历史事实陈述，保留不改；product_id `Team-Playbook-v3` 不变（数字快照更新非产品本体变化，追溯链稳定）；下游 ProductProducerAgent TODO 无「14」引用（已 grep 确认），无需同步。

### 变更（报告两处 available-channels.md 历史叙述补现行位置括注；跨仓漏网引用一并修正）

- **为什么改**：9/13 删除 `.claude/rules/` 并入 CLAUDE.md 时，报告 §3 / §4 两处「两次渠道踩坑 → available-channels.md」按「历史事实陈述」保留原样；但该报告是 Wright 生产模块 3 的活文档输入，读者会按文件名去仓里找现行版而落空。用户 2026-09-13 指示处理全部不一致，补括注指明现行位置，历史事实与新架构两头都不误导。另发现同批清理漏网的跨仓活引用：ProductProducerAgent TODO T1 素材源仍指向已删文件。
- **改了什么**：`docs/product/hot-trend-ai-agent-money-system.md` §3「能力证明」与 §4 模块 3 两处各追加括注（「历史文件名，该规则现为本仓 CLAUDE.md『## 你的约束』章节，独立文件 2026-09-13 已并入」）；同步修正 ProductProducerAgent TODO T1 素材源为指向本仓 CLAUDE.md 对应章节（其 CHANGELOG 已另记）。

### 变更（规则文件并入 CLAUDE.md，删除 .claude/rules/ 目录）

- **为什么改**：用户 2026-09-13 要求把 `.claude/rules/` 下的内容全部并入 CLAUDE.md 并删除该目录。全局规则已明确 `.claude/rules/` 没有按文件名自动加载的机制、文件进入上下文的唯一途径是进某个 CLAUDE.md，独立规则文件存在「引用漏加载」风险，并入后单文件自包含、不再依赖 @ 引用。
- **改了什么**（2026-09-13）：
  - `CLAUDE.md`：「## 你的约束（见 .claude/rules/）」一节改为「## 你的约束」，原两行文件引用替换为两份规则全文（《聚焦被动收入》《可用销售与引流渠道》，内容逐字保留、仅列表格式排版）；
  - 删除 `.claude/rules/`（含 `passive-income-only.md`、`available-channels.md`）；
  - 同步清理残留活引用：`.claude/skills/hot-trend/SKILL.md` 2 处、`docs/product/hot-trend-ai-agent-money-system.md` 2 处，由「遵守 available-channels / passive-income-only 规则」改为「遵守 CLAUDE.md 渠道 / 被动收入约束」，避免指向已删文件的 dangling 引用。
- **边界**：docs 报告中 2 处历史案例叙述（「两次踩坑 → available-channels.md」的沉淀故事）保留原样，属过去事实的陈述、不指向现行文件；CHANGELOG 历史条目中的文件名同样保留（历史记录不改）。本仓无子项目（超集同步不适用）。

### 变更（CLAUDE.md 删去「由 Claude Code 自动加载」说明句）

- **为什么改**：用户 2026-09-12 要求 CLAUDE.md 不再强调本文由 Claude Code 加载，团队全部项目的 CLAUDE.md 统一清理此类语句。
- **改了什么**（2026-09-12）：`.claude/CLAUDE.md` 开头角色定位行删去句尾「本文件由 Claude Code 在每次会话开头自动加载。」，角色描述本身保留。

### 变更（assets/logo.svg 副标题去中文）

- **为什么改**：全局规则新增「Logo / 图标资产文字一律用英文」（2026-09-12 用户立，起因 Swing 仓库 logo 副标题混入中文被指出）：logo 是面向全球读者的视觉标识，中文受众已有 README_cn.md 双语通道；且 SVG 中文依赖查看环境的字体回退，渲染不可控。本次为按新规批量清理存量。
- **改了什么**：`assets/logo.svg` 副标题「Product Strategist · 选品策略师」→「Product Strategist」。

### 修复（TODO / MEMO 编号加粗脚本截断事故：批量脚本切片 bug 把条目正文截空，从多恢复源全量重建）

- **为什么改**：上一条「全量补编号」执行时，第二步「编号加粗」脚本存在切片 bug（`m.group(0)[m.end(3)+1:]` 起点算错），把所有被匹配条目的正文截成空壳（只剩 `- [ ] **Tn** `），共波及 1 个文件 2 条。发现后立即启动恢复（无 Time Machine / APFS 快照可用）。
- **改了什么**：多恢复源重建并回写——① git 暂存区 / HEAD 旧版（MEMO.md）；② Claude Code file-history 检查点（Edit 前快照，MEMO.md（转写重放重建））；③ 会话转写重放（按时间序重放历史 Edit / heredoc 写入，补齐检查点之后的新增条目，如 DayTradingAgent 今晚新增的 5 条活跃待办与「2026-08-21 批量处理」4 条归档）。重建后统一按规则加粗编号（**Tn** / **Mn**），DayTradingAgent 连续 T1~T115、DayTradingAgent-win 连续 T1~T44，正文经抽样与恢复源逐字一致。受损壳快照留存本机 tmp（/tmp/todo-damage-backup/）。
- **边界**：恢复目标是「截断事故前的状态」（即编号未加粗、但已编号的正文完整版）；编号加粗为规则要求的新格式。git 未提交的其它改动不受影响。

### 变更（TODO / MEMO 条目全量补编号：按新立待办编号规则一次性补齐存量）

- **为什么改**：2026-08-21 用户新立全局规则「每条待办必须有唯一待办编号」（格式 T+序号 / M+序号，如 T11 / M11，连写、项目内递增、永不复用、归档保留），并指示存量待办与归档待办全部补上编号——编号用于用户与 AI 针对性沟通（「T11 处理了吗」），避免复述长正文。
- **改了什么**：MEMO.md 2 条备忘补编号（M1~M2）；TODO 两文件当前 0 条目，无需处理。正文内容零改动（只插入编号，不改写、不重排、时间戳不变）；编号顺序 = 活跃文件在前、归档在后、文件内按行序。

### 变更（产品定名 The Agent Team Playbook：v3.1 报告改名 + product_id 追溯链同步，趁未生产一次改净）

- **为什么改**：待产旗舰产品原拟名「Fleet Playbook」（`product_id: Fleet-Playbook-v3`）与刚完成的 fleet → team 全量措辞统一（2026-08-21）冲突——产品漏斗以真实仓库为证据（X 帖晒架构图 → bio 挂仓库 → 买家对照 GitHub 各仓 README），各仓已统一自称 team，产品名再叫 Fleet 会把两套自称带回买家视角；且「team playbook」是英语地道搭配（源自球队战术手册）、「fleet playbook」是混搭，产品价值主张（"a Company That Runs Itself"）也是组织 / 公司隐喻而非舰队隐喻。用户 2026-08-21 裁定立即改名；产品尚未生产（仍在 Wright TODO），此刻改名成本最低、零外部影响。
- **改了什么**：
  - `docs/product/hot-trend-ai-agent-money-system.md`（v3.1 报告，17 处）：标题「Agent Fleet Playbook（智能体军团作战手册）」→「Agent Team Playbook（智能体团队作战手册）」；§0 新增「产品名定名（2026-08-21）」决策块（定名 + 三条理由 + 旧名弃用说明）；§1/§4/§5/§7 正文 fleet → team（含 14-agent fleet → team、模块 1「The Fleet Method」→「The Team Method」、案例走读与封面视觉的 fleet 措辞、教程 thread 文案 `contracts → a fleet` → `a team`、「军团」→「团队」）；成品样例文件夹树 `agent-fleet-playbook/` → `agent-team-playbook/`、`01-fleet-method/` → `01-team-method/`、`fleet-diagram.svg` → `team-diagram.svg`；英文标题 `The Agent Fleet Playbook` → `The Agent Team Playbook`；§9 `product_id: Fleet-Playbook-v3` → `Team-Playbook-v3`（括注旧值留痕）。
  - `MEMO.md`：DSH 跟踪条目「强化 Fleet Playbook 卖点」→「Team Playbook」，时间戳同步更新。
  - **下游追溯链同步**：ProductProducerAgent `TODO.md` 生产任务条目（产品名、product_id、报告定位说明）同步改，其 CHANGELOG 已另记——保证 Echo 归因链（product_id）不断。
- **边界**：产品未生产、未上架、无营销内容已发布（X 帖未发、Payloadz 未上），改名零外部迁移成本；报告内保留的「Fleet」字样仅存在于定名决策块与 product_id 括注中的历史引用（说明旧名为何弃用），非现行措辞。

### 变更（措辞统一 fleet → team：`.commit-cache.md` 缓存标记跟随全局统一）

- **为什么改**：用户 2026-08-16 已把 xhqing 主页 README 的自称从「舰队 / fleet」改为「团队 / team」，全局元规范与 commit skill 已同步改（2026-08-21，记录见 CapabilityManagerAgent CHANGELOG），本仓 `.commit-cache.md` 缓存标记里的「fleet Visitors 徽章」是同一批存量；2026-08-21 用户裁定全量存量一次清零、统一为团队 / team。
- **改了什么**：`.commit-cache.md` 1 处缓存标记「fleet Visitors 徽章属允许例外」→「团队 Visitors 徽章属允许例外」。仅改措辞，检测逻辑、徽章均不变。（`MEMO.md` 里的「Fleet Playbook」是待产产品的 `product_id` 追溯标识（`Fleet-Playbook-v3`），非自称措辞，不改。）

### 变更（v3.1 报告交接方式落定：生产任务直接写入 Wright 项目 TODO.md）

- **为什么改**：用户裁定（2026-08-20）——比起在报告里附交接清单、等用户开 Wright 会话时手动指路，把生产任务直接写进 ProductProducerAgent 的 TODO.md 更方便：Wright 会话开工时读自己的 TODO 即获得完整生产指令，用户无需当信使复述。原「artifacts/ 交接版 + §10 交接清单」方案作废（报告位置即唯一权威输入，`docs/product/` 路径直接写入任务）。
- **改了什么**：ProductProducerAgent 项目根新建 `TODO.md`（绿色紧急度「流水线任务」：Fleet Playbook 生产任务全文——报告绝对路径、7 模块产品形态与文件夹结构、三个素材源仓库路径与各自用途、验收线「每个模板真实可用」、产物进 artifacts/ 且必带 `product_id: Fleet-Playbook-v3`、规格冲突回 Scout 会话提）与 `TODO-archive.md`（空初始化），其 CHANGELOG 同步记录。本项目不改报告（交接信息在 Wright 侧 TODO，职责反转：不是 Scout 报告里夹生产指令，而是 Wright TODO 指回 Scout 报告）。

### 变更（README 徽章组合合规：移除 Last Commit 动态徽章 + 补 Version 徽章）

- **为什么改**：commit skill 第 9l 步检测（2026-08-20）发现两版 README 徽章行含 `Last Commit` 动态徽章（URL 为 `github/last-commit/`，属规范禁用的 GitHub 动态时间徽章），且标准三枚（License / Version / Type）中缺 Version 徽章，与「标准徽章固定三枚、不含动态徽章」规范不符。
- **改了什么**：README（EN/CN）徽章区删除 `Last Commit` 动态徽章行，新增 `Version-1.0.0` 静态徽章（版本号取自 VERSION 文件）；Visitors 访问量徽章（指向 xhqing traffic/badges/ 的 endpoint 形态）属 fleet 允许例外，保留不动。

### 变更（选品方案 v3.1 增补：蹭 DSH 热点——桥接内容钩子 + 跨 harness 模块 + 版本节点跟踪）

- **为什么改**：用户问「最近 dsh 好像很热，要不要趁这个热点」，经查证（2026-08-20）：DSH = DeepSeek Harness，2026-08-13 发布并开源（MIT，developer preview），两天破 95k-112k GitHub stars（刷新 OpenClaw 纪录）、插件生态首日 100+ 次日破千、微博 / HN / Reddit / Medium / YouTube 多平台共振，热度属实且与目标人群（Claude Code / agent 组织讨论者）高度重合。决策：**只蹭流量层，不动产品本体**——① DSH 把「插件多到装不完」放大到极致，恰好强化本产品「组织 > 囤积」价值主张，是零产品成本的流量机会；② 不做 DSH 品牌付费产品（developer preview 官方已预告破坏性变更、社区对付费 DSH 内容的割韭菜警惕已拉满、插件商业化低客单价高维护成本与被动收入约束冲突）；③ 加一节跨 harness 内容作低成本增量。
- **改了什么**：报告 4 处增补——§1 加 DSH 热点条目与处置决策（含「蹭流量不碰地基」边界与一句话理由收口）；§4 内容大纲加第 7 模块「Cross-Harness Portability」（随 Wright 生产一并做）；§5 引流钩子加第 6 条「DSH 桥接帖」（含英文草稿、当前「攒关注不带货」打法、错峰备选）并将首发 3 帖扩为 4 帖；§9 product_id 标注 v3.1。另：MEMO.md 新增「持续跟踪 `deepseek-ai/deepseek-harness` 版本节点」备忘条目（三类节点：正式版 / 插件生态里程碑 / 破坏性变更，每波节点都是桥接内容流量窗口，与 x-algorithm 同批顺手查）。

### 变更（x-algorithm 跟踪条目从 TODO.md 移入 MEMO.md 备忘录）

- **为什么改**：用户指正（2026-08-20）——持续跟踪 `xai-org/x-algorithm` 是无明确完成时点的超低频持续事项（每周顺手查、长期跟进），不设排期压力，按「备忘录 MEMO.md」定位（超低频备忘放 MEMO、TODO 只放要尽快清空的待办）应放 MEMO.md，不该进 TODO.md 占住待办清单。
- **改了什么**：新建项目根 `MEMO.md`（头部功能定位说明 + 跟踪条目整体迁入，补触发场景「每次做选品 / 引流 / 运营相关会话时顺手查一次」与「勿用 2023 旧仓库」提示）；TODO.md 清空该条目（保留文件头，注明超低频备忘放 MEMO.md）。

### 新增（选品方案 v3：产品本体换为 Agent Fleet Playbook + X 算法运营手册）

- **为什么改**：用户指出 v2 方案（拼装的 7-skill 包）不如自己已开源、真实在跑的 14-agent 智能体团队（同主打智能体变现系统逻辑），经多轮决策对齐后推翻 v2：v2 卖拼装概念（自己没跑过、真实性缺口），v3 卖真实系统 + 组织方法论（过程证明取代结果证明，规避无盈利证明的转化困境）；渠道经用户六点论证（语言非障碍 / 小红书受众错配 / X 有推荐机制 / 跨境收款无摩擦 / CC 国内口碑差反衬 X 优势 / 两边均有现成号）定回 X 首发；开源与付费边界定 open core（开源仓库不删不锁，付费层为新增量的手册 / 模板 / 整合包）。
- **改了什么**：`docs/product/hot-trend-ai-agent-money-system.md` 全文重写为 v3——产品换为「Agent Fleet Playbook」三合一（手册 + 模板包 + clone 即得整合包，$49 / 首周 $35 早鸟，全英文）；卖点定「过程证明 + 能力证明」（14 仓库可查证），不碰结果承诺；新增 §3.5「X 推荐算法情报」（基于 `xai-org/x-algorithm` 开源代码分析：互动权重序、外链惩罚、6 小时半衰期、30 分钟 / 10 回复触发点、TweepCred 信誉分、情感信号、thread 完成率、主题一致性、长尾判定与 Starter Packs 通道）并固化为 §5 六条运营铁律；交易方向定为第二产品线（需 3-6 个月真实业绩解锁）；窗口期放宽至 2026-10。

### 新增（X 推荐算法开源仓库持续跟进机制）

- **为什么改**：用户指令（2026-08-18）——`xai-org/x-algorithm`（X 于 2026-08-13 release 公开打分权重与可见性过滤）需持续跟进，一有更新立即分析、反哺产品定位与运营方案。注意：该项目 2026 年 1 月首次开源、8 月 13 日最新 release，此前的旧仓库为 2023 年的 `twitter/the-algorithm`（已过时）。
- **改了什么**：新建项目根 `TODO.md`（活跃待办，含上述持续跟进条目，绿色紧急度）与 `TODO-archive.md`（归档空初始化）；报告 §9 写入跟进机制（跟踪 release / commit，每周一次，分析结果同步更新 §3.5 与运营手册）。

### 变更（Visitors 徽章更名 Visits/day (14d)：alt 文本与 xhqing 集中统计新 label 对齐）

- **为什么改**：用户要求（2026-08-17）访问量徽章名需表达「最近半月日均访问量」口径——xhqing 集中统计侧的 badge JSON label 已从 `Visitors` 改为 `Visits/day (14d)`（`Visits/day` 是 shields.io 表达日均的惯例写法、`(14d)` 标注 14 天滚动窗口），各仓 README 的徽章 alt 文本同步对齐，避免 alt 与徽章实际显示文字脱节。
- **改了什么**：README 徽章区 `alt="Visitors"` → `alt="Visits/day (14d)"`，仅改 alt 文本，endpoint URL、数据源、徽章口径均不变（口径改动记 xhqing 仓库 CHANGELOG，本仓只改 alt）。

## [1.0.0] - 2026-08-07

### 变更（Visitors 徽章 alt 文本首字母大写：README 访问量徽章命名统一）

- **为什么改**：用户指令（2026-08-16）「Visitors 徽章全局统一，首字母大写」——配合全局 `~/.claude/CLAUDE.md`「徽章英文首字母必须大写」新规，集中统计上线时挂的访问量徽章 `alt="visitors"` 为小写存量，与 badge JSON label（`Visits/day`）及大写规范不一致，本次一次收口。
- **改了什么**：README（EN/CN）徽章区 visitors 徽章 `alt="visitors"` → `alt="Visitors"`，仅改 alt 显示文本，endpoint URL 与数据源不变。

### 新增（README 访问量徽章——舰队集中式访问统计）

- **为什么改**：全舰队上线集中式「真去重」访问统计（图片徽章方案无法去重，走官方 Traffic API 路线）：统计集中部署在 xhqing 仓库（`scripts/update_traffic.py` + 每日 GitHub Action），各 fleet 仓库只需在 README 挂徽章、零运行负担。
- **改了什么**：README（EN/CN）徽章区新增 visitors 徽章（shields.io endpoint 指向 `xhqing/xhqing` 仓库 `traffic/badges/<repo>.json`，由每日采集的官方 Traffic API 数据更新）。徽章数字含义：按日去重访客的累计（GitHub 只提供每日 uniques，跨天不去重），自 2026-08-16 起累计。

- 初始版本：Scout 选品策略师 Agent 项目。核心职责为产出《机会研判报告》（热点 → 选品 → 市场调研 → 竞品分析 → 盈利模式 → 引流销售渠道建议），作为数字产品销售流水线的研判入口。
- 内置能力：`hot-trend`（全球热点扫描与选品）、`anysearch` / `find-skill`（通用搜索与技能发现）。
- 项目标配：README 中英双语 + LOGO + 徽章 + 版权署名段；MIT 许可证；`VERSION` 1.0.0。
- 移除 `.claude/rules/` 下与全局 `~/.claude/rules/` 逐字节重复的 3 个通用规则文件（file-operation-priority-rules.md、tmp-dir-for-artifacts.md、verify-before-report.md）：这些规则已由全局加载、项目副本属于冗余，删除后仅保留项目专属规则（available-channels.md、passive-income-only.md），避免项目内重复维护。
