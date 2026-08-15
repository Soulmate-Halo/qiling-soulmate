# 内容热更新发布说明 / Content Hot Update Release Note

> 内容版本 / Content versions: 内部内容通道 227（本次未变更 / unchanged）· Soulmate 内容通道 250

## 中文

- 修复工作台模式下长任务结束后不再显示「本轮节省信息」的问题：当一轮对话超过 10 分钟，界面会先自动解除忙碌状态，此后引擎迟到返回的结果被整个丢弃、会话不再重绘，于是本轮输入输出 token 与节省金额那一整块统计随之消失。
- 现在迟到结果返回后会按当前活动会话做一次幂等重绘，从落库消息重新取回本轮统计，节省信息恢复正常显示；原有的 10 分钟超时提示文案保持不变，不会重复插入气泡，也不会把忙碌状态重新设回；用户已切换到其它会话时不做任何界面操作。
- 本次修改只涉及公开版渲染层，内部内容通道的对应文件不含该超时分支、不存在此缺陷，因此按发布铁律「单包适用变更」登记为不适用，并已机器验证该通道内容版本保持 227、包内 75 个文件逐字节未变；不使用发布无变化版本的方式凑同步。
- 本次更新的三渠道固定顺序为：**内部内容通道 → Soulmate 内容通道 → GitHub 公开仓库**；GitHub 保留此公开发布说明。

## English

- Fixed the missing per-turn savings summary in workbench mode for long turns: when a turn ran past 10 minutes the UI released the busy state first, then discarded the late engine result entirely and never repainted the session, so the block showing this turn's input/output tokens and saved cost disappeared.
- A late result now triggers one idempotent repaint of the active session and reloads the turn statistics from the persisted message, so the savings summary shows up again. The existing 10-minute timeout notice is unchanged, no duplicate bubble is inserted, the busy state is not restored, and nothing is repainted if the user already switched to another session.
- This change only touches the renderer of the public build; the corresponding file in the internal content channel has no such timeout branch and is not affected, so it is recorded as not applicable under the "single-package change" release rule, with machine verification that the channel stays at content version 227 and all 75 packaged files are byte-for-byte unchanged. No no-op release is published just to pair the channels.
- This update follows the fixed three-channel order: **internal content channel → Soulmate content channel → public GitHub repository**, with this public release note retained on GitHub.

## 历史版本 / Previous

### 内部内容通道 227（未变更）· Soulmate 内容通道 249

- 修复自行添加的自定义模型在调用时返回 401 的问题：客户端此前会把用户填写的 API Key 误替换为登录令牌，现在一律使用用户自己保存的 Key；未填写 Key 时给出明确错误提示；鉴权请求头去重，避免重复的 `Bearer` 前缀导致鉴权失败。
- Fixed a 401 failure when calling a user-added custom model: the client used to replace the user-supplied API key with the login token and now always uses the key saved by the user; a model without a key reports an explicit error; authorization headers are de-duplicated so a repeated `Bearer` prefix can no longer break authentication.

### 内部内容通道 227 · Soulmate 内容通道 248

- 修复 Cursor 渠道填入自己的 API Key 之后模型列表仍然为空的问题；本地配置只保存部分字段时不再整组覆盖随包默认值；渠道开关仅在显式关闭时生效；修复子代理被判定停滞时可能中断整次调用的问题。
- Fixed the empty model list on the Cursor channel after supplying a personal API key; a partially saved configuration group no longer replaces the whole shipped default group; a channel is disabled only when explicitly turned off; fixed a subagent run flagged as stalled aborting the whole call.

### 内部内容通道 226 · Soulmate 内容通道 247

- 解除了器灵引擎的模型锁定；自定义模型恢复为可选、可调用；内置器灵货架精简为仅保留 `Auto` 一项。
- The Qiling engine is no longer locked to a single model; custom models can be selected and invoked again; the built-in catalog is streamlined to the single `Auto` option.
