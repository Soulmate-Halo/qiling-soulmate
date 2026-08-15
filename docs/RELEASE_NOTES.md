# 内容热更新发布说明 / Content Hot Update Release Note

> 内容版本 / Content versions: 内部内容通道 227（本次未变更 / unchanged）· Soulmate 内容通道 249

## 中文

- 修复自行添加的自定义模型在调用时返回 401 的问题：客户端此前会把用户填写的 API Key 误替换为登录令牌，现在一律使用用户自己保存的 Key。
- 自定义模型未填写 Key 时给出明确的错误提示，不再静默改用其它凭据。
- 鉴权请求头去重，避免出现重复的 `Bearer` 前缀导致鉴权失败。
- 本次修改只涉及公开版独有的鉴权分档模块，内部内容通道不存在对应文件，因此按发布铁律新增的「单包适用变更」规则登记为不适用，并已机器验证该通道内容版本保持 227 未变；不使用发布无变化版本的方式凑同步。
- 本次更新的三渠道固定顺序为：**内部内容通道 → Soulmate 内容通道 → GitHub 公开仓库**；GitHub 保留此公开发布说明。

## English

- Fixed a 401 failure when calling a user-added custom model: the client used to replace the user-supplied API key with the login token, and now always uses the key saved by the user.
- A custom model without a key now reports an explicit error instead of silently falling back to another credential.
- Authorization headers are de-duplicated so a repeated `Bearer` prefix can no longer break authentication.
- This change only touches the authentication-tier module that exists in the public build; the internal content channel has no counterpart file, so it is recorded as not applicable under the newly added "single-package change" release rule, with machine verification that the channel stays at content version 227. No no-op release is published just to pair the channels.
- This update follows the fixed three-channel order: **internal content channel → Soulmate content channel → public GitHub repository**, with this public release note retained on GitHub.

## 历史版本 / Previous

### 内部内容通道 227 · Soulmate 内容通道 248

- 修复 Cursor 渠道填入自己的 API Key 之后模型列表仍然为空的问题；本地配置只保存部分字段时不再整组覆盖随包默认值；渠道开关仅在显式关闭时生效；修复子代理被判定停滞时可能中断整次调用的问题。
- Fixed the empty model list on the Cursor channel after supplying a personal API key; a partially saved configuration group no longer replaces the whole shipped default group; a channel is disabled only when explicitly turned off; fixed a subagent run flagged as stalled aborting the whole call.

### 内部内容通道 226 · Soulmate 内容通道 247

- 解除了器灵引擎的模型锁定；自定义模型恢复为可选、可调用；内置器灵货架精简为仅保留 `Auto` 一项。
- The Qiling engine is no longer locked to a single model; custom models can be selected and invoked again; the built-in catalog is streamlined to the single `Auto` option.
