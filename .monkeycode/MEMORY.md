# 用户指令记忆

本文件记录了用户的指令、偏好和教导，用于在未来的交互中提供参考。

## 格式

### 用户指令条目
用户指令条目应遵循以下格式：

[用户指令摘要]
- Date: [YYYY-MM-DD]
- Context: [提及的场景或时间]
- Instructions:
  - [用户教导或指示的内容，逐行描述]

### 项目知识条目
Agent 在任务执行过程中发现的条目应遵循以下格式：

[项目知识摘要]
- Date: [YYYY-MM-DD]
- Context: Agent 在执行 [具体任务描述] 时发现
- Category: [代码结构|代码模式|代码生成|构建方法|测试方法|依赖关系|环境配置]
- Instructions:
  - [具体的知识点，逐行描述]

## 去重策略
- 添加新条目前，检查是否存在相似或相同的指令
- 若发现重复，跳过新条目或与已有条目合并
- 合并时，更新上下文或日期信息
- 这有助于避免冗余条目，保持记忆文件整洁

## 条目

[置顶窗口功能结构]
- Date: 2026-04-20
- Context: Agent 在执行“排查置顶快捷键对企业微信不生效”时发现
- Category: 代码结构
- Instructions:
  - 置顶快捷键入口在 `main.aardio`，通过 `app.topmost.registerHotkey(mainForm)` 注册全局热键。
  - 具体置顶逻辑集中在 `lib/app/topmost.aardio`，包括前台窗口识别、置顶切换和热键注册。

[内存清理功能结构]
- Date: 2026-04-20
- Context: Agent 在执行“排查内存清理无明显效果”时发现
- Category: 代码结构
- Instructions:
  - 内存清理入口在 `main.aardio` 的 `btnMemReduce.oncommand`，执行后立即刷新界面并弹窗反馈结果。
  - 实际清理逻辑集中在 `lib/app/memReduce.aardio`，通过 `process.emptyWorkingSet()` 整理当前进程或遍历其他进程工作集。

[微信置顶弹层维护方式]
- Date: 2026-04-21
- Context: Agent 在执行“修复微信表情面板在置顶聊天窗下无法弹出”时发现
- Category: 代码模式
- Instructions:
  - 微信相关的置顶兼容逻辑集中在 `lib/app/topmost.aardio` 的维护定时器，而不是单次切换置顶时一次性处理。
  - 仅跟踪前台窗口不足以覆盖微信表情面板，这类弹层需要按 `owner` 或 `GA_ROOTOWNER` 与聊天窗的关系做周期性扫描和同步置顶。

[置顶弹层匹配与标记兼容性]
- Date: 2026-04-21
- Context: Agent 在执行“修复微信表情面板与企业微信置顶回归问题”时发现
- Category: 代码模式
- Instructions:
  - 仅按 `GA_ROOTOWNER` 扩大扫描范围过于宽泛，容易误伤企业微信中的普通同链路窗口；需要结合 `WS_POPUP`、`WS_CHILD` 和 `owner` 一起过滤。
  - `lib/app/topmostOverlay.aardio` 的置顶标记应使用保守文本，避免 emoji 在部分窗口标题栏字体里退化成方框。
