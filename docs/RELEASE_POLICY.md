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

固定顺序：**本地 → 双内容热更新（适用时）→ 国内官网 → GitHub → 国外官网**。热更新是事务内的强制交付轨道，不是第五端；前一步未通过机器验收，不得进入下一步。

Fixed order: **Local → paired content hot update (when applicable) → CN Website → GitHub → Overseas Website**. Hot update is a mandatory delivery track, not a fifth endpoint. The next step cannot start until the previous one passes machine verification.

## 唯一版本源 / Single Source of Version

- 每次整包发布只允许一个对外版本号，所有端点来自同一个唯一版本源。
- 配对内容通道各自维护严格递增的内容版本号，并由同一变更记录关联；数字不要求相同。
- Each full release has one public version from a single source. Paired content channels keep independently increasing content versions linked by one change record; the numbers do not need to match.

## 固定顺序 / Fixed Order

1. **本地 / Local** — 判定交付模式，构建并本地校验产物；
2. **双内容热更新 / Paired content hot update（适用时 / when applicable）** — 同一变更两边发布并机器回读；任一边失败则整体失败并成对回滚；
3. **国内官网 / CN Website** — 版本与下载入口同步为同一版本；
4. **GitHub** — 同步公开文档（社区与运营信息，不发布产品源码）；
5. **国外官网 / Overseas Website** — 当前固定为 `SKIPPED_NOT_OPEN / 未开放`，如实登记为未开放、跳过。

纯文档或官网变更登记 `NOT_APPLICABLE_DOCS_ONLY`，禁止为了凑同步发布空内容包。Documentation-only or website-only changes are recorded as `NOT_APPLICABLE_DOCS_ONLY`; empty update bundles are forbidden.

## 铁律 8：三渠道同步更新 / Iron Rule 8: Three-Channel Synchronized Update

三渠道定义为**内部内容通道**、**Soulmate 内容通道**与 **GitHub 公开仓库**，固定顺序为：**内部内容通道 → Soulmate 内容通道 → GitHub 公开仓库**。任何客户端内容热更新或整包发布都必须在同一事务内推进三条渠道，不得调换或跳过。

The three channels are the **internal content channel**, **Soulmate content channel**, and **public GitHub repository**, in this fixed order: **internal content channel → Soulmate content channel → public GitHub repository**. Every client content hot update or full release advances all three in one transaction without reordering or skipping.

三条渠道全部成功才允许机器断言 `THREE_CHANNEL_SYNC=PASS`；任一渠道失败则整体断言 `THREE_CHANNEL_SYNC=FAIL`，两条内容清单一起回滚，GitHub 公开文档还原上一版，并禁止对外通知。

Only complete success may assert `THREE_CHANNEL_SYNC=PASS`. Any channel failure asserts `THREE_CHANNEL_SYNC=FAIL`, rolls back both content manifests together, restores the previous public GitHub documents, and blocks public notice.

GitHub 必须留下公开发布说明，写明两条内容版本号与面向用户的行为变化。GitHub must retain a public release note stating both content versions and the user-visible behavior changes.

## 公开边界 / Public Boundary

公开文档（国内官网、GitHub、未来的国外官网）不得包含：本机路径、内网地址、服务器与部署细节、密钥、闭源实现与更新源内部细节。

Public documents must not contain: local machine paths, internal addresses, server or deployment details, credentials, closed-source internals, or update-source internals.

## 验收 / Verification

每个端点及适用的双内容热更新都必须通过机器验收（不是目测收工）；任一已开放端点或任一热更新侧失败，本次发布整体视为失败，不对外通知。

Every endpoint and each applicable hot-update side must pass machine verification (no eyeballing). Failure of any open endpoint or either hot-update side fails the whole release without public notice.

## 失败回滚 / Rollback

按端点回滚；双内容热更新必须成对恢复两份清单，禁止只回滚一边；GitHub 仅还原公开文档；国外官网未开放，无回滚动作。回滚动作同样需要登记。

Rollback is per endpoint. Paired hot updates restore both manifests together, never one side only. GitHub restores public documents only; the overseas website has no rollback while closed. Rollback actions are also recorded.

## 发布记录 / Release Records

每次发布登记：交付模式、版本号、配对内容通道状态与清单哈希、时间、操作人、各端点状态、验收结果与回滚记录。没有记录的发布视为未发布。

Each release records: delivery mode, versions, paired-channel status and manifest hashes, time, operator, endpoint states, verification results, and rollback notes. A release without a record is not a release.

---

*本公开版不包含任何内部路径、服务器、密钥或闭源实现细节。*
*This public version contains no internal paths, servers, credentials, or closed-source implementation details.*
