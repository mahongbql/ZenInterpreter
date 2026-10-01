# ZenInterpreter

<p align="center">
  <b>macOS 与 Windows 桌面实时同声传译</b><br>
  本地语音识别 · 流式翻译 · 置顶双语字幕
</p>

<p align="center">
  <a href="./README.md">English</a> · <b>简体中文</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/平台-macOS%20%7C%20Windows-blue" alt="平台">
  <img src="https://img.shields.io/badge/版本-macOS%201.6.0-blue" alt="版本">
  <img src="https://img.shields.io/badge/语音识别-本地运行-orange" alt="本地语音识别">
  <img src="https://img.shields.io/badge/语种-7-green" alt="7 种语言">
</p>

**ZenInterpreter** 是面向 macOS 和 Windows 的实时同声传译软件。它监听麦克风或系统声音，在本机完成语音识别，再把双语字幕悬浮在会议、网课、浏览器和视频之上。

适合需要跟着另一门语言往下听的场景：国际会议、在线课程、客户沟通、直播，以及原声视频。语音在设备上识别，只有识别出的文本会发送给翻译服务。

---

## 下载

| 平台 | 安装包 |
| :--- | :--- |
| macOS 12 及以上 | [下载 macOS 版](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter.dmg) |
| Windows | [下载 Windows 版](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter_Setup_v1.0.0.exe) |

macOS 当前版本为 **1.6.0**。安装后可在 **Settings → Check for updates** 升级到后续版本。更新只替换程序，本机语音模型会保留；下载中断后可以续传。

Windows 的更新发布在 [版本页](https://github.com/mahongbql/ZenInterpreter/releases)。

[观看简短演示](https://github.com/user-attachments/assets/f79f0b52-764a-4a75-8f50-3f55b277cbbd)

---

## 适用场景

- **会议与通话** — 在 Zoom 等会议软件上显示实时字幕
- **课程与讲座** — 不必等课程上传字幕，听的同时就能看译文
- **视频与直播** — 给 YouTube、本地视频和直播加上系统声音字幕
- **客户沟通** — 保留一场跨语言通话的双语记录
- **听力练习** — 原声继续播放，译文同步出现

---

## 功能

### 置顶悬浮字幕

无边框半透明字幕窗始终位于其他应用之上。在 macOS 上还可以覆盖全屏应用和其他桌面空间。鼠标移入显示工具栏，拖动可移动，拉边缘可调整大小，支持多显示器。

首次启动时窗口会先出现，识别引擎在后台加载，启动过程中应用保持可见。

### 可回看的双语记录

字幕窗口保留整场记录，而不是闪过即消失的一行：

1. 原文的实时预览
2. 定稿原文，以及逐段出现的流式译文
3. 更早的句子留在窗口中。向上滚动可回看，回到底部后继续跟随最新一句

识别修正上一句时，会改写原有那一行。

### 本地语音识别

**SenseVoiceSmall** 通过 **ONNX Runtime（INT8）** 在独立进程中运行。模型加载和识别时，字幕窗口保持可操作。音频不会上传。语气词、残句和明显的识别噪声会在翻译前滤除。

### 两种翻译引擎

| 引擎 | 适合 |
| :--- | :--- |
| **AI Model** | 演讲和对话。结合上下文，修正识别偏差，译文更接近口语同传。 |
| **Google** | 延迟更低，译文更贴近字面。 |

Google 不可用时自动改用 AI 引擎。长段语音按语义单元翻译，不必等整句结束才出现第一批文字。

### 语种

默认方向为 **英语 → 中文**。以下语种可以任意配对，也可以一键对调：

英语 · 中文 · 日语 · 韩语 · 西班牙语 · 法语 · 德语

翻译方向、引擎和音频设备会在下次启动时保留。macOS 与 Windows 使用同一套语种。

### 导出会话

在设置中把本场记录导出为 Word（`.docx`）、纯文本（`.txt`）或 Markdown（`.md`）。默认保存到桌面。

### 系统声音或麦克风

在设置中选择任意输入设备。检测到 **BlackHole**（macOS）或 **立体声混音**（Windows）时会自动选中，从而给会议、浏览器或本地视频加字幕，而不只是麦克风。

### 账号

可使用 GitHub 或 Google 登录，也可以开启每台设备每天 **3 小时**的访客试用。Pro 在应用内购买，结账在浏览器中完成，支付后开通。激活码用于机构、推广和售后。

---

## 开始使用

1. 从[下载表](#下载)安装对应系统的安装包。
2. 打开 ZenInterpreter，登录或开始访客试用。
3. 将鼠标移到字幕窗，打开 **Settings**：
   - **Audio device** — 麦克风，或用 BlackHole / 立体声混音捕获系统声音
   - **Engine** — AI Model 或 Google
   - **Languages** — 选择源语言、目标语言，或对调
4. 开始说话或播放音频。向上滚动可回看，结束后在设置中导出。

### 在 macOS 上捕获系统声音

1. 安装 [BlackHole 2ch](https://existential.audio/blackhole/)。
2. 打开**音频 MIDI 设置**，新建**多输出设备**，同时包含扬声器和 BlackHole。
3. 将 macOS 的输出切换到该多输出设备。
4. 在 ZenInterpreter 中选择 **BlackHole**。检测到时会自动选中。

在 Windows 上，于声音控制面板启用**立体声混音**（或其他环回设备），再在设置中选为输入。

---

## 系统要求

| | macOS | Windows |
| :--- | :--- | :--- |
| 系统 | macOS 12 或更高版本 | Windows 10 或更高版本 |
| 处理器 | Apple Silicon 或 Intel | 64 位 |
| 显示 | 支持多显示器、全屏应用和其他桌面空间 | 标准桌面会话 |
| 音频 | 麦克风；捕获系统声音需安装 BlackHole | 麦克风；捕获系统声音需启用立体声混音 |
| 网络 | 翻译和登录需要网络。语音模型安装完成后，识别本身不依赖网络。 | 相同 |

---

## 隐私

| 数据 | 去向 |
| :--- | :--- |
| 麦克风与系统音频 | 留在本机，识别在本地完成。 |
| 识别出的文本 | 发送到所选翻译引擎。 |
| 账号 | 使用 GitHub 或 Google 登录，用于管理试用和 Pro。 |

---

## 常见问题

**能不能给 Zoom 会议或 YouTube 视频加实时字幕？**  
可以。macOS 用 BlackHole、Windows 用立体声混音捕获系统声音，再让 ZenInterpreter 浮在会议或浏览器上面。

**语音会不会离开这台电脑？**  
不会。音频在本机识别，发出去的是每一句识别后的文本。

**支持哪些语言？**  
英语、中文、日语、韩语、西班牙语、法语、德语，方向可以任意组合。

**两种引擎有什么区别？**  
AI Model 是流式同传：会平滑识别错误，读起来更接近口译。Google 更快，也更贴近字面。

**有没有试用？**  
有。每台设备每天可访客使用 3 小时。Pro 可在设置中购买。

**更新会不会重新下载语音模型？**  
macOS 不会。应用内更新只替换程序，已下载的模型会保留。

---

## 方案

| | 访客试用 | Pro |
| :--- | :--- | :--- |
| 每日时长 | 每台设备 3 小时 | 购买后开通 |
| 字幕、导出、语种 | 包含 | 包含 |
| 如何开始 | 直接打开应用 | **Settings → Upgrade** |

激活码用于机构、推广和售后，在 **Settings → Activate code** 兑换。

---

## 实现方式

| 层级 | 实现 |
| :--- | :--- |
| 界面 | PyQt6。macOS 使用 AppKit 悬浮窗（NSPanel，屏保级窗口层级） |
| 音频 | PyAudio；macOS 为 Core Audio，Windows 为 WASAPI |
| 语音识别 | SenseVoiceSmall，ONNX Runtime INT8，独立识别进程 |
| 翻译 | 流式语言模型（Qwen2.5）或 Google |
| 登录 | GitHub 与 Google |
| 打包 | PyInstaller。macOS 为磁盘映像，Windows 为安装程序 |
| 更新 | macOS 应用内更新，支持断点续传。Windows 通过版本页发布 |

---

## 平台状态

| 平台 | 状态 |
| :--- | :--- |
| macOS | 已发布，支持应用内更新。当前版本 1.6.0 |
| Windows | 已发布，提供安装包。更新通过版本页获取 |
| 移动端 | 暂未提供 |

后续计划：Windows 应用内更新、更多语种，以及进一步降低字幕延迟。

---

## 支持

问题、缺陷和功能建议：[GitHub Issues](https://github.com/mahongbql/ZenInterpreter/issues)。

版本记录：[GitHub Releases](https://github.com/mahongbql/ZenInterpreter/releases)。
