# 发布守则 / Release Policy

> 公开版 / Public version
> 本文件是器灵 Soulmate 发布守则的公开摘要。完整内部执行细则不随本仓库公开。
> This document is the public summary of the Qiling Soulmate release policy. Full internal execution details are not published in this repository.

---

## 四端发布事务 / Four-Endpoint Release Transaction

器灵 Soulmate 的每次版本发布是**一个整体事务**，涉及四个端点，按固定顺序推进：

| 端点 / Endpoint | 状态 / Status | 说明 / Notes |
| --- | --- | --- |
| 本地 / Local | OPEN | 构建产物与内部验证的起点，不对外公开 |
| 国内官网 / CN Website | OPEN | 面向国内用户的产品信息、版本与下载入口 |
| GitHub | OPEN | 社区与运营入口，不发布产品源码 |
| 国外官网 / Overseas Website | **SKIPPED_NOT_OPEN / 未开放** | 尚无域名、账号与部署入口；开放前不执行、不模拟、不占位任何发布动作 |

固定顺序：**本地 → 国内官网 → GitHub → 国外官网**。前一步未通过机器验收，不得进入下一步；顺序不可调换、不可跳跃。

Fixed order: **Local → CN Website → GitHub → Overseas Website**. The next step cannot start until the previous one passes machine verification; the order cannot be swapped or skipped.

## 唯一版本源 / Single Source of Version

- 每次发布只允许一个版本号，所有端点对外展示的版本号来自同一个唯一版本源。
- 禁止临时改号、拼号或复用旧号；同一版本号只能属于一次发布事务。
- Each release carries exactly one version number, sourced from a single version source across all endpoints. No ad-hoc changes, splicing, or reuse of old numbers; the same version number belongs to exactly one release transaction.

## 固定顺序 / Fixed Order

1. **本地 / Local** — 构建并本地校验产物；
2. **国内官网 / CN Website** — 版本与下载入口同步为同一版本；
3. **GitHub** — 同步公开文档（社区与运营信息，不发布产品源码）；
4. **国外官网 / Overseas Website** — 当前固定为 `SKIPPED_NOT_OPEN / 未开放`，如实登记为未开放、跳过。

## 公开边界 / Public Boundary

公开文档（国内官网、GitHub、未来的国外官网）不得包含：本机路径、内网地址、服务器与部署细节、密钥、闭源实现与更新源内部细节。

Public documents must not contain: local machine paths, internal addresses, server or deployment details, credentials, closed-source internals, or update-source internals.

## 验收 / Verification

每个端点推进后必须通过机器验收（不是目测收工）；任一已开放端点失败，本次发布整体视为失败，不对外通知。

Every endpoint must pass machine verification after advancing (no eyeballing). Failure of any open endpoint fails the whole release without public notice.

## 失败回滚 / Rollback

按端点回滚：国内官网按页面、配置、下载别名与更新通道的备份还原；GitHub 仅还原公开文档；国外官网未开放，无回滚动作。回滚动作同样需要登记。

Rollback is per endpoint: CN website restores from page / configuration / download alias / update-channel backups; GitHub restores public documents only; the overseas website has no rollback since it is not open. Rollback actions are also recorded.

## 发布记录 / Release Records

每次发布登记：版本号、时间、操作人、各端点状态、验收结果与回滚记录。没有记录的发布视为未发布。

Each release records: version, time, operator, per-endpoint status, verification results, and rollback notes. A release without a record is not a release.

---

*本公开版不包含任何内部路径、服务器、密钥或闭源实现细节。*
*This public version contains no internal paths, servers, credentials, or closed-source implementation details.*
