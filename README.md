# IᵐTⁱᵖ 智能桌面助手

ImTip 是一个轻量、独立、可扩展的 Windows 桌面助手。

- 独立 EXE，无外部依赖
- 兼容 XP、Vista、Win7、Win8、Win10、Win11
- 同时覆盖输入状态提示、超级热键、AI 助手和桌面效率工具

下载地址：<https://imtip.aardio.com/update/ImTip.7z>

![ImTip 主界面](./screenshots/ImTip.jpg)

## 目录

- [核心特性](#核心特性)
- [快速开始](#快速开始)
- [常用功能](#常用功能)
- [托盘与快捷操作](#托盘与快捷操作)
- [兼容性与常见问题](#兼容性与常见问题)
- [启动参数](#启动参数)
- [重置数据](#重置数据)
- [相关链接](#相关链接)

## 核心特性

### 输入状态跟踪

ImTip 会在输入光标附近显示简洁的状态提示，用更少的视觉干扰提供更多信息：

- 中英输入状态
- 中英标点
- 全角/半角
- 大小写
- 多语言键盘布局

![通用输入法状态跟踪提示](./screenshots/ime-state.gif)

它的目标不是只告诉您“现在是中文还是英文”，而是尽量在不打断输入节奏的前提下，把常见输入状态一次说明白。

- 切换到新的输入位置时会及时提示
- 支持自定义显示时长、位置和外观
- 可以关闭输入法自带状态栏，让桌面更干净

![输入法自带状态栏](./screenshots/ime.png)

外观支持可视化调整，也支持方案导入导出。

- 可将外观方案拖到 `ImTip.exe` 或设置窗口中导入
- 支持通过剪贴板直接复制粘贴配置代码

![调色](./screenshots/color.gif)

![复制配置方案](./screenshots/copy.gif)

### 超级热键

ImTip 提供可编程扩展的超级热键系统，所有热键逻辑都由 [aardio](https://aardio.com) 编写，可按需修改、扩展或交给 AI 辅助生成。

默认已提供以下热键：

- <kbd>Ctrl+#</kbd> 极速版：全局翻译 + 查单词
- <kbd>Ctrl+@</kbd> AI 增强版：全局翻译 + 查单词
- <kbd>Ctrl+$</kbd> 打开财务大写、日期时间大写、数学运算工具

相关文档：

- 快速开始：<https://imtip.aardio.com/#help-hotkey>
- 开发指南：<https://www.aardio.com/zh-cn/doc/?q=library-guide%2Fstd%2Fkey%2Fhotkey.html>

### AI 助手

ImTip 内置可配置的 AI 桌面助手，可以快速把大模型 API 接入成桌面可用工具。

- 支持多个 AI 助手配置
- 同一会话中可切换不同模型
- 支持数学公式渲染、代码高亮、一键分享截长屏、联网读取文档等能力
- 也可通过超级热键直接调用 AI 会话

![AI 助手](./screenshots/ai.gif)

启用方式：

1. 在主界面勾选启用超级热键。
2. 点击“编辑超级热键”。
3. 在配置中填入 AI 接口参数并保存。

参考文档：<https://imtip.aardio.com/#help-dict>

### 桌面效率工具

除输入提示和热键外，ImTip 还内置了一组偏实用型的小工具：

- 窗口置顶
- 空格预览文件
- 内存清理
- 托盘快捷操作

这类功能更偏向“拿来就用”，适合日常桌面工作流中的零散高频动作。

## 快速开始

1. 下载并解压 `ImTip.7z`。
2. 运行 `ImTip.exe`。
3. 根据需要启用输入状态提示、超级热键和 AI 助手。
4. 如需开机静默运行，可在程序内启用开机启动。

如果您主要想先体验输入状态提示，只需要直接运行程序即可。

如果您主要想用 AI 或超级热键，建议先打开超级热键配置页，检查默认热键和模型参数。

## 常用功能

### 输入状态提示

ImTip 默认强调低打扰、低资源占用。

CPU 占用可以通过“跟踪检测速度”调节：

![跟踪检测速度](./screenshots/cpu.png)

默认存在轻微延迟，这是主动做的资源优化；如果您更追求跟手感，可以适当提高检测速度。

### 超级热键与翻译

超级热键既可以做轻量操作，也可以承载复杂工作流，比如：

- 划词翻译
- 单词查询
- AI 解释与扩展
- 唤起会话窗口

### 文件预览、窗口置顶与内存清理

这些功能主要通过主界面和托盘菜单使用：

- 置顶当前工作窗口，适合文档、聊天和对照场景
- 用空格快速预览资源管理器中的图片、视频和 PDF
- 图片使用 ImTip 自带的无边框预览窗口，视频和 PDF 复用资源管理器预览窗格
- 需要时手动执行一次内存清理

## 托盘与快捷操作

托盘菜单提供了一组高频操作入口：

- 快速打开设置
- 启用或暂停输入跟踪提示
- 启用英文键盘、微软拼音、微软五笔
- 执行内存清理
- 开关空格预览文件
- 置顶当前窗口和管理已置顶窗口

![托盘菜单](./screenshots/menu.png)

托盘快捷操作：

- 按住 <kbd>Shift</kbd> 点击托盘图标：打开 AI 助手
- 按住 <kbd>Ctrl</kbd> 点击托盘图标：启用或禁用输入跟踪提示

输入法常用快捷键：

- <kbd>Shift</kbd>：切换中英输入
- <kbd>Ctrl+.</kbd>：切换中英标点
- <kbd>Shift+空格</kbd>：切换全角/半角
- <kbd>Alt+Shift</kbd>：切换语言

## 兼容性与常见问题

### 关于英文键盘

部分第三方输入法会安装“中文美式键盘”，容易引发状态错乱。这个键盘在新版本 Windows 中意义不大，建议改为“英语美式键盘”。

Win7、Win10、Win11 用户通常可通过托盘菜单禁用再启用一次“英语键盘”完成修复。

### 管理权限窗口

ImTip 默认以普通权限启动。若您希望它对管理权限窗口也生效，需要以管理员身份启动 `ImTip.exe`。

如果以管理员身份启动后重新勾选“允许开机启动”，则之后也会以管理员权限开机运行。

### 文件预览能力

空格预览功能目前依赖两套能力：

- 图片由 ImTip 自己直接显示
- 视频和 PDF 依赖 Windows 资源管理器的预览窗格与系统已安装的预览处理器

如果某些视频或 PDF 在资源管理器中本来就不能预览，那么 ImTip 里按空格通常也无法获得完整预览。

### 窗口兼容性

ImTip 使用多种接口获取输入位置。少数窗口如果都不支持，会退化为读取鼠标输入位置。

对于 Java 程序窗口：

- 可以在设置中勾选“启用 java.accessBridge 扩展”
- 这通常可自动支持 JetBrains 等 Java 应用

如果勾选后自动取消，并显示“未启用 java.accessBridge 扩展”，通常是因为当前系统无法联网下载所需扩展。也可以自行在 aardio 中运行：

```aardio
import java.accessBridge;
print( java.accessBridge.switch(true) );
```

更多兼容配置说明：<https://www.aardio.com/zh-cn/doc/library-guide/std/key/ime.stateBar.html#editorClasses>

说明：ImTip 仅在检测到输入框时显示输入状态。即使关闭“仅切换输入目标或状态后显示”，对于检测不到输入目标的窗口仍不会显示提示，除非您为该窗口配置兼容类名。

### 输入法兼容性

原理说明：<https://www.aardio.com/zh-cn/doc/?q=library-guide/std/key/imeState.html>

兼容性要点：

- 主流输入法基本都可支持 ImTip
- 微软自带输入法支持最好
- 小小输入法通常可正常工作，异常时可借助 [IMY](https://github.com/aardio/IMY) 卸载重装
- 小狼毫建议使用最新 nightly build
- 微信输入法、手心输入法、讯飞输入法需要勾选对应“怪异模式”
- 个别老旧输入法可能会干扰其他输入法状态

### 微信与常见聊天软件

微信 4.0 已可良好支持 ImTip，无需额外设置。

如果个别聊天软件中输入位置识别不理想，优先检查：

- 是否启用了兼容窗口类名
- 是否存在输入法自身悬浮条干扰
- 是否在管理员权限窗口中使用普通权限的 ImTip

## 启动参数

### `ImTip.exe *.aardio`

加载配置方案，也可以直接把配置文件拖到 `ImTip.exe` 上。

### `ImTip.exe`

无参数启动。如果 ImTip 已运行，则会打开配置窗口。

### `ImTip.exe /chat 配置名称 /q 需要立即发送的问题`

启动 AI 聊天助手窗口。配置名称和 `/q` 参数都可以省略。

如果要在代码里调用，可参考：<https://www.aardio.com/zh-cn/doc/library-guide/std/key/hotkey.html#imtip-ai-chat>

### `ImTip.exe /sys`

启动时不显示主界面。勾选开机启动时会使用这个参数。

## 重置数据

先退出 ImTip，然后按 <kbd>Ctrl+R</kbd> 打开“运行”，执行以下命令：

```bat
cmd /c rd /s /q %localappdata%\aardio\std\ImTip
```

删除完成后重新运行 ImTip，即可恢复到最新默认配置。

## 相关链接

- 官方站点：<https://imtip.aardio.com/>
- aardio 官网：<https://aardio.com>
- 超级热键文档：<https://www.aardio.com/zh-cn/doc/?q=library-guide%2Fstd%2Fkey%2Fhotkey.html>
- 输入状态原理：<https://www.aardio.com/zh-cn/doc/?q=library-guide/std/key/imeState.html>

本页中的动画主要使用开源免费录屏软件 [Gif123](https://gif123.aardio.com/) 录制。
