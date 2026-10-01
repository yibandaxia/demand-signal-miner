# 需求挖掘机 / Demand Signal Miner

[中文](#中文) · [English](#english)

## 中文

**需求挖掘机**是一个 Codex Skill，用于从公开社区讨论、产品评论、GitHub Issues 和用户反馈中发现真实、反复出现的产品需求。它先研究用户正在完成的任务、现有流程和 workaround，再判断是否存在值得进一步验证的产品机会。

适合领域痛点研究、从论坛或应用评论寻找机会、验证一个产品想法，以及定期追踪需求变化。它不用于单纯的创意脑暴、市场规模预测或功能清单生成。

### 安装

在支持 `SKILL.md` 的 Codex 环境中，将仓库克隆到 Skills 目录：

```bash
git clone https://github.com/yibandaxia/demand-signal-miner.git "${CODEX_HOME:-$HOME/.codex}/skills/demand-signal-miner"
```

其他支持 Skill 文件的 Agent 可以读取仓库根目录的 [`SKILL.md`](SKILL.md)，并按其自身的 Skill 加载方式安装。研究时，Agent 还需要能够访问相关公开资料；本仓库不提供爬虫或付费数据源。

### 使用示例

可以明确调用 `$demand-signal-miner`，例如：

> 使用 $demand-signal-miner，调查过去 12 个月 NAS 用户在照片管理方面反复遇到的问题。给出原始讨论链接、workaround、反证和最值得继续验证的需求。

> 使用 $demand-signal-miner，验证“为自由职业者做自动发票整理工具”是否对应真实需求。先查用户现有流程和替代方案，再判断是否值得做 MVP。

### 研究方式与输出

1. 优先研究垂直社区和产品反馈，再补充泛社区；只把可核查、日期明确的近期讨论计入核心证据。
2. 区分实际行为、重复痛点与口头愿望；把同一底层问题跨帖子聚类，统计独立用户、讨论和来源。
3. 对候选需求寻找现有方案和反证，分别给出 45 分制排序与证据置信度。证据不足时明确说明，不凑候选数量。
4. 报告包含研究范围、问题地图、来源链接、候选机会、反证和意外发现。只有周期性研究才输出需求雷达。

只使用正常公开访问、正式公开 API、用户提供或已授权的资料。遇到访问限制应停止该路径；报告聚焦问题，不建立个人档案。

### 文件

- [`SKILL.md`](SKILL.md)：触发范围、核心流程与约束。
- [`references/research-method.md`](references/research-method.md)：检索、证据记录、信号分级与评分。
- [`references/report-format.md`](references/report-format.md)：报告结构与周期性需求雷达。
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 界面显示名。

许可证：[MIT](LICENSE)。

## English

**Demand Signal Miner** is a Codex Skill for finding recurring product needs in public community discussions, app reviews, GitHub Issues, and user feedback. It examines what people are trying to do, how they do it today, and the workarounds they already use before suggesting product opportunities.

Use it for pain point research, opportunity discovery from forums or reviews, validation of a product idea, and periodic demand tracking. It is not intended for idea brainstorming alone, market size forecasts, or feature list generation.

### Install

In a Codex environment that supports `SKILL.md`, clone the repository into the Skills directory:

```bash
git clone https://github.com/yibandaxia/demand-signal-miner.git "${CODEX_HOME:-$HOME/.codex}/skills/demand-signal-miner"
```

Other agents that support Skill files can load the repository's [`SKILL.md`](SKILL.md) using their own installation mechanism. The agent also needs access to relevant public sources to conduct research. This repository does not include a scraper or paid data access.

### Example prompts

Invoke `$demand-signal-miner` explicitly when useful:

> Use $demand-signal-miner to investigate recurring photo management problems among NAS users over the last 12 months. Include links to original discussions, workarounds, contradictory evidence, and the needs worth validating next.

> Use $demand-signal-miner to test whether freelancers have a real need for automated invoice organization. Examine their current workflows and alternatives before recommending an MVP.

### Method and deliverables

1. Start with focused communities and product feedback, then broaden to general communities. Count only verifiable, dated, recent discussions as core evidence.
2. Separate observed behavior and recurring friction from hypothetical wishes. Cluster the same underlying problem across posts and count independent users, discussions, and sources.
3. Check existing solutions and contradictory evidence. Rank candidates on a 45-point scale alongside a separate evidence confidence level. Report the actual number of supported candidates.
4. Deliver research scope, a problem map, source links, ranked opportunities, evidence against, and unexpected findings. Add a demand radar only for periodic studies.

Use only normally accessible public content, official public APIs, user-provided material, or authorized sources. Stop when access restrictions block a source. Focus on problems without building profiles of individual users.

### Files

- [`SKILL.md`](SKILL.md): invocation scope, core workflow, and constraints.
- [`references/research-method.md`](references/research-method.md): search, evidence records, signal tiers, and scoring.
- [`references/report-format.md`](references/report-format.md): report structure and periodic demand radar.
- [`agents/openai.yaml`](agents/openai.yaml): Codex display name.

License: [MIT](LICENSE).
