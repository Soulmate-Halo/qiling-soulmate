<p align="center">
  <img src="assets/soulmate-logo.png" alt="器灵 Soulmate" width="180" />
</p>

<h1 align="center">器灵 Soulmate</h1>

<p align="center">
  <strong>把多个 AI 编程助手编排成一支真正会分头干活的本地团队。</strong><br />
  拆解任务、动态路由、治理上下文，让每一步都更省。
</p>

<p align="center">
  <a href="README.md">English</a> | <strong>简体中文</strong>
</p>

<p align="center">
  <a href="https://qiling.swcbg.com">官方网站</a> ·
  <a href="docs/ROADMAP.md">路线图</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/issues">Issues</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/discussions">Discussions</a>
</p>

---

## 这是什么

器灵 Soulmate 是一款**本地优先**的 AI 编程助手产品。它不是在单线程里逐个使用助手，而是在一个会话中编排多个 AI 编程工具：分配任务、观察每个执行端在干什么、把结果汇成一件完成的活。

它围绕四个理念设计：

- **多 AI CLI 协同**：让多个 AI 编程工具在同一会话里既分工又协作；
- **任务拆解**：把一个大需求拆成可独立执行、可机器验收的小任务；
- **动态路由**：按任务类型、依赖与并发上限，把每个子任务分配给空闲的执行端；
- **上下文与成本治理**：只让必要的内容进入上下文、大文件按需读取，把可外包的活整包派给子代理。

器灵 Soulmate 以桌面应用形态运行，直接在本机干活，并支持 CDP / Selenium / Playwright 等浏览器自动化能力。

## 三条路线：快 · 准 · 省

器灵 Soulmate 的编排理念在三件事之间做权衡。它们是设计取向，不是性能承诺：

| 路线 | 实际意味着什么 |
| --- | --- |
| **快（Fast）** | 执行端并行推进而不是排队等待；相互独立的子任务并头进行，而不是串行。 |
| **准（Accurate）** | 任务被拆成可机器验收的小单元，并把正确的内容留在上下文里——结果靠执行验证，而不是靠人眼复读。 |
| **省（Economical）** | 能外包的探索与写码整包派给子代理，一步拿回结论；用机器验收代替人工重读，压低每一步的成本。 |

具体任务可以侧重其中任意一条，器灵 Soulmate 不强推单一模式。

## 工作方式

```mermaid
flowchart LR
  A[你描述任务] --> B[拆解为子任务]
  B --> C[路由到空闲执行端]
  C --> D[执行端并行干活]
  D --> E[机器验收]
  E --> F[交付结果]
```

以上描述的是产品的工作理念。编排策略的内部实现保持闭源。

## 开始使用

器灵 Soulmate 是闭源商业桌面产品——本仓库是它的社区与运营入口，不是源码分发处。

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

## 社区

欢迎文档改进、问题反馈与协作参与——但请留意上面的边界。

- **Issues**：通过模板报告 Bug、提交需求建议
- **Discussions**：分享使用经验、讨论方向
- **Pull Requests**：提交前请先阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)，并使用 [PR 模板](./.github/PULL_REQUEST_TEMPLATE.md)

请勿在本仓库提交产品核心源码、密钥、凭据、内部服务器信息或下载链接。

## 相关链接

| 链接 | 用途 |
| --- | --- |
| <https://qiling.swcbg.com> | 官方网站 |
| [docs/ROADMAP.md](./docs/ROADMAP.md) | 公开路线图 |
| [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) | 开源范围与边界说明 |
| [SECURITY.md](./SECURITY.md) | 安全政策 |
| [CONTRIBUTING.md](./CONTRIBUTING.md) | 贡献指南 |
| [NOTICE.md](./NOTICE.md) | 版权与商标声明 |
