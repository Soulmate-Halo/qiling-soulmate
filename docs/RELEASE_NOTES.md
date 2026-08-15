# 内容热更新发布说明 / Content Hot Update Release Note

> 内容版本 / Content versions: 内部内容通道 227 · Soulmate 内容通道 248

## 中文

- 修复 Cursor 渠道填入自己的 API Key 之后模型列表仍然为空的问题。
- 本地配置只保存了某个分组的部分字段时，随包默认设置不再被整组覆盖；缺失的字段回落默认值，空字符串不再顶掉默认值。
- 渠道开关口径收紧：只有显式关闭才停用该渠道，字段缺失不再被当作关闭。
- 修复子代理在被判定停滞时可能直接中断本次调用的问题。
- 本次更新的三渠道固定顺序为：**内部内容通道 → Soulmate 内容通道 → GitHub 公开仓库**；GitHub 保留此公开发布说明。

## English

- Fixed the Cursor channel showing an empty model list after a user supplies their own API key.
- A partially saved local configuration group no longer replaces the whole shipped default group: missing keys fall back to defaults, and empty strings no longer override them.
- Channel activation is now stricter: a channel is disabled only when it is explicitly turned off, never because a key is absent.
- Fixed a subagent failure where a run flagged as stalled could abort the whole call.
- This update follows the fixed three-channel order: **internal content channel → Soulmate content channel → public GitHub repository**, with this public release note retained on GitHub.

## 历史版本 / Previous

### 内部内容通道 226 · Soulmate 内容通道 247

- 解除了器灵引擎的模型锁定；自定义模型恢复为可选、可调用；内置器灵货架精简为仅保留 `Auto` 一项。
- The Qiling engine is no longer locked to a single model; custom models can be selected and invoked again; the built-in catalog is streamlined to the single `Auto` option.
