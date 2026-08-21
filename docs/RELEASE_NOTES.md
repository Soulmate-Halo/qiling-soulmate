# 内容热更新发布说明 / Content Hot Update Release Note

## v2.3.22 (2026-08-21)

- 修复渠道 Key 面板「验证」按钮点第一次像没反应：验证结果原先只靠 toast 提示，且拿到结果后会立刻整行重建列表，把刚更新过的按钮状态一并抹掉。
- 验证按钮旁新增常驻状态标记：点击立即进入等待态，通过显示绿色对勾、失败显示红色叉，失败原因挂在标记的 title 上，结果不再被列表重建冲掉。
- 修复填入 Cursor API Key 后模型库仍然显示 0：openChan 与 ensureQlChanModels 把空数组也当成有效缓存，只要在没有 Key 时打开过一次模型菜单，之后永远不会重新拉取模型清单。
- 添加、验证、删除 Key 之后主动让该渠道的模型缓存失效并立即重拉，验证通过时一并解除该渠道熔断状态并重绘模型菜单。
- 内容版本：内部通道 259；Soulmate 通道保持 272（该线无渠道 Key 面板，不涉及本次改动）。

## v2.3.21 (2026-08-21)

- 修复异地注册/登录输入验证码后误报「登录超时」：客户端请求上限 15 秒与服务端短信通道 15 秒完全撞线，弱网或跨网时客户端必然先行中断，服务端其实已经受理。
- 超时阈值分级放宽：发送验证码 45 秒，登录与注册 40 秒，账号信息与额度查询 20 秒。
- 超时提示改写：显示实际等待秒数，并提醒若短信已收到请重新获取一次验证码再输入（旧验证码可能已被服务端消费）。
- 关闭服务端并未实现的网页登录入口：原先点开的是账号密码控制台页，不会回调桌面端，用户要空等五分钟才看到超时；同时补上被调用却从未定义的 exchangeDesktopCode，消除潜在 TypeError。
- 内容版本：内部通道 258；Soulmate 通道 272。

## v2.3.20 (2026-08-20)

- GLM-5.3 长任务续跑补丁新增验收降级禁令：计划中的实测步骤未执行时，不得用静态推断替代并宣告完成。
- Codex CLI 检测改为即时合并 Windows User/Machine 注册表 PATH 与当前进程 PATH，安装后无需重启小易即可重新发现。
- 补齐 WinGet Links、Volta 与 Scoop shims 常见安装目录；继续排除无法直接 spawn 的 `.ps1`。
- 内部通道 c256 已具备同等检测能力，本次保持不变；Soulmate 通道由 c270 同步到 c271。
- Content versions: internal 256 (unchanged); Soulmate 271.

## v2.3.19 (2026-08-19)

- 修复器灵详情对话界面宽度塌缩导致中文逐字竖排的问题。
- 详情对话改为覆盖聊天栏的单列对话流：任务右对齐，器灵过程和结果左对齐。
- 消息行全宽，气泡采用响应式 `min-width`/`max-width`；240/320/560/960 窗口均能正常换行。
- 详情区使用单滚动容器，打开时定位末尾，事件按顺序秒级追加。
- 内容版本：内部通道 253；Soulmate 通道 269。

## v2.3.18 (2026-08-19)

- System-prompt posture patch for long-running tasks: no fixed step ceiling, strict two-condition turn end, no deciding on behalf of the user, truncated output must be declared and continued.
- 50-step steer reminder: every 50 tool calls the engine injects a continue-or-finish prompt so long tasks do not stall mid-way.
- Empty-reply fallback hint: when the model returns nothing, the UI shows an actionable fallback-model suggestion instead of a blank bubble.
- Content versions: internal channel 252; Soulmate channel 268.

## v2.3.17 (2026-08-19)

- 器灵详情弹层改为聊天流式对话框：任务、过程、终态交付三条气泡，样式对齐主界面消息气泡。
- 器灵工作流探针：运行过程的有界事件流（思考/输出/工具/步骤）落盘，详情弹层实时展示。
- 等待期快照注入：器灵交还控制权时，回执尾部自动附带最近 3 条工作流事件，主模型不盲目等待。
- 内容版本：内部内容通道 250；Soulmate 内容通道 267。

## v2.3.16 (2026-08-19)

- 上下文窗口修复：自定义模型端点声明 1,000,000 token 上下文，界面不再错误回退显示 203K。
- 引擎侧同步受益：上下文压缩阈值随真实容量放大，长会话不再提前触发压缩。
- 内容版本：内部内容通道 249；Soulmate 内容通道 266。

## v2.3.15 (2026-08-19)

- 进程可见：点开 Soulmates 人员卡片，可查看 run 状态、实时执行步骤、思考流与最终交付。
- 手动关闭：运行中器灵增加“关闭器灵”按钮，关闭后立即回执主模型并记入会话收件箱。
- 日志与稳定性：会话菜单增加器灵日志查看入口，同步修复 Windows 下 Codex 只读探针被策略误拦截的问题。
- 内容版本：内部内容通道 248；Soulmate 内容通道 265。

## v2.3.14 (2026-08-18)

- 视觉：工作台侧栏的历史任务、项目分组和项目内会话统一采用低对比度半透明灰阶。
- 交互：悬停、当前选中、按下依次为 4%、6%、9% 黑色透明度，层级清晰但不再出现大块深灰实底。
- 一致性：上段最近任务与下段项目树使用同一组交互状态，滚动条及其他区域保持不变。
- 内容版本：内部内容通道 247；Soulmate 内容通道 264。

## v2.3.13 (2026-08-18)

- 修复：点击「立即升级」后，安装向导会保持可见，不再出现应用退出但向导未显示、重开后版本不变的问题。
- 稳定性：客户端仅在确认安装器已启动并持续存活后退出；启动失败时会保留当前版本并重新下载。
- 兼容性：升级前的进程清理不再触碰主程序或安装器，清理异常也不会阻断安装向导启动。
- 内容版本：内部内容通道 246；Soulmate 内容通道 263。

## v2.3.12 (2026-08-18)

- 修复：新建或切换会话后，「Soulmates」集合区只显示当前会话所属的器灵，不再残留其他会话累计的旧图标。
- 修复：会话归属不明确的历史运行记录不再进入集合区，避免旧记录被误归到新会话。
- 保留：当前会话中的运行中图标、任务结束状态与详情入口继续正常展示。
- 内容版本：Soulmate 内容通道 262；内部内容通道保持 245（本次公测专属修复不适用，未改动）。

## v2.3.11 (2026-08-18)

- 发布：提供全新的 Windows 公测安装包，首次启动即包含截至 v2.3.10 的全部修复与体验优化。
- 修复：后台任务停止与接回、内容更新后的子任务加载、终端输出持续回传等稳定性改进已纳入安装包。
- 优化：侧边栏信息密度、交互状态和全应用滚动条样式已统一更新。
- 下载：https://qiling.swcbg.com/download/QilingSoulmate-PublicBeta-Setup-2.3.11.exe

## v2.3.10 (2026-08-18)

- 优化：侧边栏项目分组与展开会话改为默认透明的无痕样式，仅在悬停、按下和当前选中时显示轻量圆角底色。
- 优化：压缩项目层级缩进、图标间距、行内边距和数量徽标，操作按钮仅在悬停时出现，同宽侧栏可显示更多标题文字。
- 优化：全应用滚动条统一为 5px 透明轨道与全圆角滑块，平时隐身、悬停滚动区域后显现，并适配深浅配色。
- 内容版本：内部内容通道 241（远端 240 已被既有发布占用后顺延） · Soulmate 内容通道 261。

## v2.3.9 (2026-08-17)

- 修复：暂停或停止后台任务后会复查整棵进程树，未确认停止时继续安全兜底，避免任务失联后继续运行。
- 修复：内容更新中的子任务脚本会优先从当前内容版本加载，确保更新后的能力立即生效。
- 修复：工作台终端会持续回传子任务输出，并以真实退出状态收尾。
- 内容版本：Soulmate 内容包 260，内部内容包 239。
## v259 (2026-08-17)

- 修复：任务执行异常、命令行进程崩溃或未取得完整结果时，保留“继续任务”检查点并标记为异常中断；正常完成仍会清除检查点，截断自动续跑链保持不变。
- 修复：未完成任务检查点完整保留停止原因、停止状态、自动续跑次数以及未来扩展字段，旧格式数据仍可正常重载。
- 修复：接回后台任务时会等待进程号登记竞态，并继续跟随仍有输出活动的孤儿状态；没有结果文件时只读返回明确状态和产物位置，以退出码 3 收尾。
## v258 (2026-08-17)

- 修复：子代理刚创建、PID 尚未完成登记时，不再被轮询误判为已中断，超过登记宽限仍无进程的真实孤儿任务继续正常收口。
- 修复：误判为已中断的任务在检测到存活进程或新日志后会恢复为运行中，随后到达的真实完成或失败结果可正确覆盖误判；其余完成态的防回退保护保持不变。

## v257 (2026-08-17)

- 修复：长任务输出达到上限或执行端异常终止时，不再误报为正常完成；系统会保留已有进度并从断点自动续跑，连续失败后显示「继续任务」入口。
- 优化：以计划句结束的疑似未完成回复仅显示手动继续提示，正常编号收尾不受影响。

## v256 (2026-08-17)

- 修复：被手动停止或程序中断的任务，现在会在会话里显示「继续任务」按钮，可从已有进度一键续跑（此前仅崩溃且无任何回复时才显示）。

## v255 (2026-08-17)

- 修复：工作台会话的成本结算现在按会话所选模型档位计价，Auto / GLM / GPT 等档位正确显示美元成本与节省对比；此前部分会话因引擎心跳模型名覆盖所选档位而显示"费率未知"。

> 内容版本 / Content versions: 内部内容通道 230 · Soulmate 内容通道 254
> 发布日期 / Release date: 2026-08-16

## 概要

- 器灵引擎链路的轮末结算改用真实 token 计量:应用层现在读取引擎回合结果携带的会话累计用量(输入/输出/缓存读/缓存写),按会话差分得到本轮用量;个别取不到时回退为只读查询引擎本地数据库,仍取不到才沿用原估算口径。
- 由此,工作台与聊天在器灵引擎上的轮末尾缀也能显示输入拆分(新输入+读缓存+写缓存)、缓存命中率、计价与节省细项,与内部分机同一口径;此前这些内容因该链路只有估算量而整块不显示。

## English

- End-of-turn settlement on the qiling engine path now uses real token usage: the app reads the session-cumulative usage (input / output / cache read / cache write) carried by the engine's turn result and derives per-turn numbers by diffing against the previous cumulative snapshot; when unavailable it falls back to a read-only query of the engine's local database, and only then to the previous estimation.
- As a result, end-of-turn footers in both the workbench and chat now show the input breakdown (fresh input + cache read + cache write), cache hit rate, pricing and the savings breakdown on the qiling engine path, matching the internal methodology. Previously the whole block stayed hidden because that path only produced estimates.

## 历史版本 / Previous

### 内部内容通道 229 · Soulmate 内容通道 253

- 修复新建任务偶发未响应、看似假死的问题：会话工作副本物化、代码检查点快照和轮末三方合并落地这三处重 I/O 操作已改为分片异步执行，主进程消息泵不再被长时间独占。
- 工作台轮末结算已与内部口径完全对齐：即使轮次尚未计价也会显示缓存命中率；命中率统一按「本轮命中缓存输入 ÷ 本轮总输入」计算，并保留节省细项。
- Fixed newly created tasks occasionally becoming unresponsive and appearing frozen. The three heavy-I/O stages—materializing the session worktree, taking code-checkpoint snapshots, and applying the end-of-turn three-way merge—now run asynchronously in chunks, so they no longer monopolize the main-process message pump.
- Workbench end-of-turn accounting now fully matches the internal methodology. Cache hit rate is shown even for turns that have not yet been priced, is calculated consistently as “cached input hit this turn ÷ total input this turn,” and retains the savings breakdown.

### 内部内容通道 228 · Soulmate 内容通道 252

- 修复轮末统计中「节省」信息缺失的问题：此前长任务一轮结束后只显示「本轮输入」与「原方案」两个相同数字，不显示节省文本。原因是「原方案」基线只计入了已归零的思考瘦身，没有计入受控历史替代全量历史重放带来的节省；本次将基线统一为与「对比原版命令行工具」相同口径（包含受控回填），并为估算用量的轮次补上节省细项，同时补齐另一条引擎链路缺失的统计入参。
- Restored the “savings” details in the end-of-turn statistics. After a long turn, “turn input” and “original approach” previously showed the same number and no savings text because the baseline counted only the now-zero reasoning-trimming component and omitted the savings from controlled history replacing full-history replay. The baseline now uses the same methodology as “compared with the original command-line tool,” including controlled backfill; estimated-usage turns also include the savings breakdown, and the missing statistics inputs are now supplied on the other engine path.

### 内部内容通道 227（未变更）· Soulmate 内容通道 251

- 工作台底部 Soulmates 指示器上的小灵魂图标，改用产品 LOGO 里的灵魂造型：原先是一个通用的幽灵轮廓，与品牌形象不一致；现在的图形直接由 LOGO 矢量化而来，圆头、右上开口缎带、两侧小卷须与菱形眼睛的特征全部保留。
- 图标仍随运行状态变色：进行中为蓝色并保持原有呼吸动画，结束后转为灰色；悬停提示、点击展开详情、键盘可达性与无障碍标签一律不变。
- 新图形按 24 像素画布重绘并补了极细描边，确保在 20 像素的实际显示尺寸下轮廓依然清晰。
- 本次修改只涉及公开版渲染层的图标与其专属样式，内部内容通道的包里不存在这个指示器组件，因此按发布铁律「单包适用变更」登记为不适用，并已机器验证该通道内容版本保持 227、包内 75 个文件逐字节未变；不使用发布无变化版本的方式凑同步。
- 本次更新的三渠道固定顺序为：**内部内容通道 → Soulmate 内容通道 → GitHub 公开仓库**；GitHub 保留此公开发布说明。
- The soul icon on the Soulmates indicator at the bottom of the workbench now uses the soul shape from the product logo. It used to be a generic ghost outline that did not match the brand mark; the new shape is vectorized directly from the logo and keeps the round head, the open ribbon on the upper right, the two side curls and the diamond eyes.
- The icon still reflects run state through color: blue with the existing breathing animation while running, grey once finished. Hover tooltips, click-to-expand details, keyboard access and accessibility labels are all unchanged.
- The new glyph is redrawn on a 24-pixel canvas with a hairline stroke so the outline stays legible at the actual 20-pixel display size.
- This change only touches the icon and its dedicated styles in the renderer of the public build; the internal content channel does not ship this indicator component, so it is recorded as not applicable under the "single-package change" release rule, with machine verification that the channel stays at content version 227 and all 75 packaged files are byte-for-byte unchanged. No no-op release is published just to pair the channels.
- This update follows the fixed three-channel order: **internal content channel → Soulmate content channel → public GitHub repository**, with this public release note retained on GitHub.

### 内部内容通道 227（未变更）· Soulmate 内容通道 250

- 修复工作台模式下长任务结束后不再显示「本轮节省信息」的问题：一轮超过 10 分钟时迟到返回的结果会被整个丢弃、会话不再重绘，现在改为按当前活动会话做一次幂等重绘，统计恢复正常显示。
- Fixed the missing per-turn savings summary in workbench mode for long turns: a result arriving after the 10-minute timeout used to be discarded without repainting the session, and now triggers one idempotent repaint of the active session so the statistics show up again.

### 内部内容通道 227（未变更）· Soulmate 内容通道 249

- 修复自行添加的自定义模型在调用时返回 401 的问题：客户端此前会把用户填写的 API Key 误替换为登录令牌，现在一律使用用户自己保存的 Key；未填写 Key 时给出明确错误提示；鉴权请求头去重，避免重复的 `Bearer` 前缀导致鉴权失败。
- Fixed a 401 failure when calling a user-added custom model: the client used to replace the user-supplied API key with the login token and now always uses the key saved by the user; a model without a key reports an explicit error; authorization headers are de-duplicated so a repeated `Bearer` prefix can no longer break authentication.

### 内部内容通道 227 · Soulmate 内容通道 248

- 修复 Cursor 渠道填入自己的 API Key 之后模型列表仍然为空的问题；本地配置只保存部分字段时不再整组覆盖随包默认值；渠道开关仅在显式关闭时生效；修复子代理被判定停滞时可能中断整次调用的问题。
- Fixed the empty model list on the Cursor channel after supplying a personal API key; a partially saved configuration group no longer replaces the whole shipped default group; a channel is disabled only when explicitly turned off; fixed a subagent run flagged as stalled aborting the whole call.

### 内部内容通道 226 · Soulmate 内容通道 247

- 解除了器灵引擎的模型锁定；自定义模型恢复为可选、可调用；内置器灵货架精简为仅保留 `Auto` 一项。
- The Qiling engine is no longer locked to a single model; custom models can be selected and invoked again; the built-in catalog is streamlined to the single `Auto` option.
