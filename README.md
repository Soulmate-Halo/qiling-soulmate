# 器灵 Soulmate

> 多个 AI CLI 协同、任务拆解、动态路由、上下文治理与成本优化 —— 器灵 Soulmate 帮助你把 AI 编程助手变成一支真正会分头干活的本地团队。

**Qiling Soulmate** coordinates multiple AI CLIs, decomposes tasks, routes them dynamically, governs context, and optimizes cost — helping you turn your AI coding assistants into a local team that actually works in parallel.

[简体中文](#简介) · [English](#introduction)

---

## 仓库说明 / What This Repository Is

`qiling-soulmate` 是 **器灵 Soulmate** 的社区与运营入口（与主流 AI 工具的官方公开仓库定位相同）。

本仓库公开的是：

- 产品定位与使用理念
- 公开路线图（Roadmap）
- 问题反馈（Bug / Feature Request）
- 社区协作入口（Issues / Pull Requests / Discussions）

**本仓库不是开源软件仓库，也未随仓库发布产品源码。** 请勿将本仓库当作「可以自行构建运行的开源项目」使用。

器灵 Soulmate 的**桌面端核心运行时、编排策略、商业服务端与生产配置保持闭源**。如需获取产品与下载信息，请访问官方网站：<https://qiling.swcbg.com>。

## 简介

器灵 Soulmate 是一个**本地优先**的 AI 编程助手产品，聚焦于：

- **多 AI CLI 协同**：在一个会话里编排多个 AI 编程工具，让它们既分工又协作；
- **任务拆解**：把大需求拆成可独立执行、可机器验收的小任务；
- **动态路由**：根据任务类型、依赖与并发上限，把任务动态分配给空闲的执行端；
- **上下文治理**：控制哪些正文进入上下文、按需读取大文件，避免把海量 token 灌进每次对话；
- **成本优化**：把可外包的探索与写码整包派给子代理执行，用机器验收代替人眼复读，显著降低单位成本。

产品形态为桌面端应用，支持跨本机直接执行、浏览器自动化（CDP / Selenium / Playwright）等真实落地能力。

## 开始使用 / Getting Started

### 了解产品

- 官方文档与介绍：<https://qiling.swcbg.com>
- 阅读 [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) 了解本项目开放范围的边界
- 阅读 [docs/ROADMAP.md](./docs/ROADMAP.md) 了解公开路线图

### 反馈问题

- 报告 Bug：使用 [Bug 模板](./.github/ISSUE_TEMPLATE/bug_report.yml)
- 提出建议：使用 [需求建议模板](./.github/ISSUE_TEMPLATE/feature_request.yml)
- 报告安全漏洞：请走 GitHub 私密报告渠道（见 [SECURITY.md](./SECURITY.md)），不要在公开 Issue 中透露漏洞细节

### 参与协作

欢迎通过提交 Issue、Pull Request 或参与 Discussions 的方式贡献。请先阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)。

## 定位边界 / Scope

| 开放（Open） | 闭源（Closed） |
| --- | --- |
| 产品信息与使用理念 | 桌面端核心运行时 |
| 公开路线图 | 编排策略与内部实现 |
| 问题反馈与社区协作 | 商业服务端 |
| 社区讨论 | 生产配置与部署细节 |

详细边界见 [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md)。

## 发布守则 / Release Policy

- 阅读 [docs/RELEASE_POLICY.md](./docs/RELEASE_POLICY.md) 了解四端发布事务、唯一版本源、固定顺序、公开边界、验收与回滚（双语）。
- 每个版本只有一个版本号；本地、国内官网、GitHub、国外官网按固定顺序作为一次事务推进；国外官网当前状态为 `SKIPPED_NOT_OPEN / 未开放`。

## 相关链接 / Links

- 官方网站：<https://qiling.swcbg.com>
- 安全政策：[SECURITY.md](./SECURITY.md)
- 贡献指南：[CONTRIBUTING.md](./CONTRIBUTING.md)
- 版权与商标声明：[NOTICE.md](./NOTICE.md)

---

## Introduction

Qiling Soulmate is a **local-first** AI programming assistant that:

- **Orchestrates multiple AI CLIs** — coordinates several AI coding tools within one session;
- **Decomposes tasks** — breaks large requirements into independent, machine-verifiable sub-tasks;
- **Routes dynamically** — assigns tasks to idle executors based on type, dependencies, and concurrency limits;
- **Governs context** — controls what goes into the context and reads large files on demand;
- **Optimizes cost** — delegates exploration and coding to sub-agents, relying on machine verification instead of manual re-reading.

This repository is the **community and operations entry point** for Qiling Soulmate. It is **not** an open-source software repository and does not ship product source code. The desktop core runtime, orchestration strategy, commercial server-side, and production configuration remain **closed source**.

**Official website:** <https://qiling.swcbg.com>

请通过 [Issues](https://github.com) 或官方网站与我们联系。
