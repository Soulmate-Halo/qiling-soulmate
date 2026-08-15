<p align="center">
  <img src="assets/soulmate-logo.png" alt="器灵 Soulmate" width="180" />
</p>

<h1 align="center">器灵 Soulmate</h1>

<p align="center">
  <strong>强模型做大脑，弱模型做手脚；多家 Agent CLI，收进同一个工作台。</strong><br />
  三选一：要么快，要么准，要么省。
</p>

<p align="center">
  <a href="README.md">English</a> | <strong>简体中文</strong>
</p>

<p align="center">
  <a href="https://webcon.swcbg.com/qiling-soulmate-beta-update/QilingSoulmate-PublicBeta-Setup-latest.exe"><img alt="下载 Windows 安装包 / 最新公测版" src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD%20Windows%20%E5%AE%89%E8%A3%85%E5%8C%85-%E6%9C%80%E6%96%B0%E5%85%AC%E6%B5%8B%E7%89%88-0078D4?style=for-the-badge&amp;logo=windows11&amp;logoColor=white" /></a><br />
  <a href="https://webcon.swcbg.com/qiling-soulmate-beta-update/latest.yml">Windows 最新公测版</a>
</p>

<p align="center">
  <a href="https://qiling.swcbg.com">官方网站</a> ·
  <a href="docs/ROADMAP.md">路线图</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/issues">Issues</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/discussions">Discussions</a>
</p>

---

## 创作者手记

我是一个独立开发者。AI 时代的到来给了我很多灵感，也让开发变得前所未有地高效；但高昂的订阅费和 API 成本，也一直困扰着我。每当一个新模型出现，我几乎都要再订阅一家服务，原来的订阅很快就被闲置。我也在本地部署过许多模型，可除了免费，它们在真正的开发工作中很难发挥作用。

为此，我一直在拆解强模型和弱模型在工具调用、文件读取等各项指标上的差异。最后，我得出一个结论：**让强模型做大脑，负责拆解任务、判断方向和最终验收；让弱模型做手脚，承担文件读取、资料检索、重复执行和大量输出。**于是，我做了这个 Agent CLI。经过无数次测试和规则修正，这套协作方式终于真正跑通。

借助我设计的压缩规则——我把它称为器灵压缩——主模型与协作模型的组合，可以在大幅减少主模型消耗的同时保持精度；在部分任务里，速度和结果质量甚至能超过主模型单独执行。我还把常用 CLI 接入同一个工作台，在获得协同收益的同时，也保留原来的使用习惯。如果你也是 AI Agent 的深度用户，欢迎加入我，养一只属于你自己的器灵。

## 这是什么

器灵 Soulmate 是一款**本地优先**的 AI 编程助手产品。它不是在单线程里逐个使用助手，而是把多家 Agent CLI 收进同一个工作台：统一选择、调度和观察，分渠道隔离，一条挂了不牵连其余。

它的核心理念很简单：**强模型做大脑，弱模型做手脚。**强模型负责拆解任务、判断方向和最终验收；弱模型承担文件读取、资料检索、重复执行和大量输出。配合专门的压缩层，在大幅减少主模型消耗的同时保持精度。

器灵 Soulmate 以桌面应用形态运行，直接在本机干活，并支持 CDP / Selenium / Playwright 等浏览器自动化能力。

## 三选一：快 · 准 · 省

> **每个任务只选一条技术路线。** 快、准、省是三种可选的首要目标，不是同时启用，也不是依次全跑。

| 路线 | 什么时候选 | 首要目标 |
| --- | --- | --- |
| **快** | 任务耗时太长 | 更快完成 |
| **准** | 结果必须可靠 | 提高质量 |
| **省** | 模型成本太高 | 降低消耗 |

先确定当前任务的第一优先级，再做一次**三选一**。下面的数字都是**官网示例中的产品测算**，不是客户实证，也不是普遍保证。

### 快 —— 大仓库先探路，强模型再动手

在陌生仓库里先拆解探路范围，多个协作模型并行检索，强模型拿到整理后的关键证据再动手改。

- 官网示例测算：4 路任务并行，耗时从 **18 分钟降到 7 分钟**，约 **2.6 倍**提速。

### 准 —— 分路找反例，贵模型只做裁决

高要求交付前分路核对证据、收集反例，最终由强模型基于机器验收（PASS/FAIL）做共识裁决。

- 官网示例测算：独立复核加机器验收后，评分从 **86 分升到 94 分**。

### 省 —— 机械步骤外包，贵模型少重放

把检索、扫描、整理、草稿和测试等机械步骤交给成本更低的协作模型，让强模型少重复读取上下文、少执行工具调用。

- 官网示例测算：成本从 **100 降到 41 成本单位**，节省 **59%**。

对话基线方面，官网测算的节省区间为：短对话（1–3 有效轮）**8–25%**，多轮对话（4–14 有效轮）**35–64%**，长对话（15+ 有效轮）**51–82%**。以上均为固定假设下的产品测算，不是效果承诺；实际结果会随模型、价格、缓存和任务结构变化。

无论选择哪条，都要坚持：**一个任务只选一条主路线**。不要三条同时开，也不要在同一个任务里依次跑完三条。

## 工作方式

```mermaid
flowchart LR
  A[你描述任务] --> B[拆解为子任务]
  B --> C[路由到空闲执行端]
  C --> D[执行端并行干活]
  D --> E[机器验收]
  E --> F[强模型交付结果]
```

以上描述的是产品的工作理念。编排策略的内部实现保持闭源。

## 开始使用

器灵 Soulmate 是闭源商业桌面产品——本仓库是它的社区与运营入口，不是源码分发处。

- **下载 Windows 安装包**：获取[最新公测版安装程序](https://webcon.swcbg.com/qiling-soulmate-beta-update/QilingSoulmate-PublicBeta-Setup-latest.exe)
- **了解产品**：访问官方网站 <https://qiling.swcbg.com>
- **了解边界**：阅读 [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) 查看本仓库开放什么、不开放什么
- **查看公开路线图**：阅读 [docs/ROADMAP.md](./docs/ROADMAP.md)
- **反馈 Bug 或提交需求**：使用 [Bug 模板](./.github/ISSUE_TEMPLATE/bug_report.yml) 或 [需求建议模板](./.github/ISSUE_TEMPLATE/feature_request.yml)
- **报告安全漏洞**：请走 GitHub 私密报告渠道，切勿在公开 Issue 中透露漏洞细节（见 [SECURITY.md](./SECURITY.md)）

## 仓库边界

本仓库是器灵 Soulmate 的**社区与运营入口**。**它不是开源软件仓库，也未随仓库发布产品源码。** 桌面端核心运行时、编排策略、商业服务端与生产配置保持**闭源**。

| 开放（Open） | 闭源（Closed） |
| --- | --- |
| 产品定位与使用理念 | 桌面端核心运行时 |
| 公开路线图 | 编排策略与内部实现 |
| 问题反馈与社区协作 | 商业服务端 |
| 社区讨论 | 生产配置与部署细节 |

完整边界见 [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md)。

## 发布守则 / Release Policy

器灵 Soulmate 的每次发布是**四端发布事务**，坚持**唯一版本源**与**固定顺序**（本地 → 国内官网 → GitHub → 国外官网）：前一步必须通过**机器验收**才能进入下一步，任一失败按端点**回滚**——完整公开摘要见 [docs/RELEASE_POLICY.md](./docs/RELEASE_POLICY.md)。国外官网当前为 **SKIPPED_NOT_OPEN / 未开放**，开放前不执行、不模拟、不占位任何发布动作。

## 社区

欢迎文档改进、问题反馈与协作参与——但请留意上面的边界。

- **Issues**：通过模板报告 Bug、提交需求建议
- **Discussions**：分享使用经验、讨论方向
- **Pull Requests**：提交前请先阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)，并使用 [PR 模板](./.github/PULL_REQUEST_TEMPLATE.md)

请勿在本仓库提交产品核心源码、密钥、凭据、内部服务器信息或未经核验的第三方下载链接。

## 相关链接

| 链接 | 用途 |
| --- | --- |
| <https://qiling.swcbg.com> | 官方网站 |
| [docs/ROADMAP.md](./docs/ROADMAP.md) | 公开路线图 |
| [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) | 开源范围与边界说明 |
| [SECURITY.md](./SECURITY.md) | 安全政策 |
| [CONTRIBUTING.md](./CONTRIBUTING.md) | 贡献指南 |
| [NOTICE.md](./NOTICE.md) | 版权与商标声明 |
