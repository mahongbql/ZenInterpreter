# ZenInterpreter

<p align="center">
  <b>轻量级桌面实时同传</b><br>
  本地语音识别 · 流式 AI 翻译 · 全屏置顶字幕
</p>

<p align="center">
  <a href="./README.md">English</a> • <b>简体中文</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/平台-macOS%20%7C%20Windows-blue" alt="Platform">
  <img src="https://img.shields.io/badge/识别-SenseVoice%20ONNX%20INT8-orange" alt="SenseVoice">
  <img src="https://img.shields.io/badge/推理-ONNX%20Runtime-green" alt="ONNX Runtime">
  <img src="https://img.shields.io/badge/翻译-AI%20%7C%20Google-purple" alt="Translation">
</p>

---

## 下载

**选择你的系统，直接下载安装 ZenInterpreter：**

| 平台 | 下载 |
| :--- | :--- |
| 🪟 **Windows** | [**下载 ZenInterpreter for Windows**](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter_Setup_v1.0.0.exe) |
| 🍎 **macOS** | [**下载 ZenInterpreter for macOS**](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter.dmg) |

> **Windows：** `ZenInterpreter_Setup_v1.0.0.exe`  
> **macOS：** `ZenInterpreter.dmg`

当前版本 **1.1.0**。macOS 也可在 **设置 → 检查更新** 升级程序，不必重新下载语音模型。

---

## 演示

https://github.com/user-attachments/assets/f79f0b52-764a-4a75-8f50-3f55b277cbbd

---

## 简介

**ZenInterpreter** 是一款面向 macOS 和 Windows 的悬浮字幕工具。它监听麦克风或系统音频，在本地完成语音识别，再把译文以流式字幕叠在 Zoom、浏览器、网课和全屏应用之上。

适合需要**实时跟上另一门语言**、又不想安装一整套深度学习环境的人。

**常见场景**

- 国际会议、远程协作
- 网课、讲座、原声视频
- 需要即时字幕的直播
- 客户沟通、跨境销售
- 看原片练听力

---

## 功能要点

### 全屏置顶悬浮窗

无边框半透明字幕窗，始终压在其他应用上面。在 macOS 上还可覆盖全屏应用和其他桌面空间。鼠标移上去唤出工具栏，拖动可移动，拉边缘可缩放，支持多显示器。

首次启动时窗口会先打开，再在后台加载识别引擎（大约十几秒），避免看起来像没启动成功。

### 可回看的字幕记录

字幕不再是闪一下就没的一行，窗口里会留下双语记录：

1. 原文的**实时预览**
2. **定稿原文**，以及逐字填入的**流式译文**
3. 更早的句子留在窗口里——向上滚可以回看，滚回底部后会继续跟着最新一句走

识别修正上一句时，会在原行上改，而不是再堆一行碎片。

### 导出

设置里可将本场记录导出为：

- **Word**（`.docx`）
- **纯文本**（`.txt`）
- **Markdown**（`.md`）

默认保存到桌面。

### 本地语音识别

**SenseVoiceSmall** 通过 **ONNX Runtime（INT8）** 在**独立识别进程**中运行。加载模型和推理时，字幕窗口不会卡住。不依赖 PyTorch。音频不出设备，只有识别出的文本会发给翻译服务。

语气词、切句残片和明显的识别垃圾会在送去翻译前滤掉。

### 双翻译引擎

在设置中随时切换：

| 引擎 | 特点 |
| :--- | :--- |
| **AI Model** | 带上下文的流式同传：纠正识别口误、去掉语气词、译文更自然。适合演讲和对话。 |
| **Google** | 更快、更直译的机器翻译，开销更低。适合更在意速度的场景。 |

Google 不可用时，会自动回退到 AI 引擎。翻译按语义单元调度（而不是整段攒完再翻），长句也能保持低延迟。

### 语种

默认 **英语 → 中文**。两端现在是同一套语种。

| 平台 | 语种支持 |
| :--- | :--- |
| **macOS** | English · 中文 · 日本語 · 한국어 · Español · Français · Deutsch 任意配对，可一键对调 |
| **Windows** | English · 中文 · 日本語 · 한국어 · Español · Français · Deutsch 任意配对，可一键对调 |

翻译方向、引擎和音频设备会记住，下次打开不用重设。

### 独立设置面板

鼠标移到字幕上 → **⚙**。面板贴在字幕窗外侧（优先右侧，空间不够则左侧），不撑高翻译区。

- **音频设备** — 麦克风，或 BlackHole / 立体声混音 捕获系统声音
- **翻译引擎** — AI Model 或 Google
- **翻译方向** — 选源语言 / 目标语言，或点 ⇄ 对调
- **账号** — 试用 / 会员状态、购买卡密、兑换、退出登录
- **导出** — 保存本场记录
- **软件更新** — 当前版本，检查更新

### 应用内更新

| 平台 | 行为 |
| :--- | :--- |
| **macOS** | 设置 → **检查更新** 只下程序包，语音模型仍用本机已有文件；下载中断可**断点续传**，完成后点 **重启安装**。请先把 App 放到 **应用程序** 文件夹，否则目录不可写。 |
| **Windows** | 检查更新会打开 GitHub 发布页，目前请在那里重新安装。 |

### 音频输入

在设置中选择任意输入设备。若系统里有 **BlackHole**（macOS）或 **立体声混音**（Windows），会自动选中，用来给系统声音上字幕——Zoom、YouTube、本地视频，而不只是麦克风。

### 账号

- GitHub / Google 一键登录
- 每台设备每天 **3 小时游客试用**
- 在设置里兑换卡密；会员到期后仍可留在应用内续期，不必重新登录

---

## 快速开始

1. 下载对应系统的安装包：
   - **Windows：** [ZenInterpreter_Setup_v1.0.0.exe](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter_Setup_v1.0.0.exe)
   - **macOS：** [ZenInterpreter.dmg](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter.dmg)
2. 打开应用，用 GitHub、Google 登录，或开启游客体验。
3. 鼠标移到字幕窗上 → **⚙ 设置**：
   - **音频设备** — 麦克风，或 BlackHole / 立体声混音 捕获系统声音
   - **翻译引擎** — AI Model 或 Google
   - **翻译方向** — 选源语言 / 目标语言，或点 ⇄ 对调
4. 开始播放或说话，字幕会出现在悬浮窗里。向上滚可回看，结束后可在设置里导出。

### 在 macOS 上捕获系统音频

若要翻译 Zoom / 浏览器 / 本地视频，而不是麦克风：

1. 安装 [BlackHole 2ch](https://existential.audio/blackhole/)。
2. 打开 **音频 MIDI 设置**，新建一个**多输出设备**，同时勾选扬声器和 BlackHole。
3. 把系统输出切到这个多输出设备。
4. 在 ZenInterpreter 里选择 **BlackHole** 作为输入（检测到时会自动选中）。

Windows 请在声音控制面板中打开 **立体声混音**（或同类回环设备），再在设置里选为输入。

---

## 平台

| 平台 | 状态 | 说明 |
| :--- | :---: | :--- |
| **macOS** | 已发布 | 12+，Apple Silicon 与 Intel · 7 语种配对 · 应用内更新 |
| **Windows** | 已发布 | 提供安装包 · 同样 7 语种配对 · 更新暂走 GitHub |
| **移动端** | 规划中 | — |

---

## 技术栈

| 层级 | 技术 |
| :--- | :--- |
| 界面 | PyQt6 · macOS 使用 AppKit 悬浮（NSPanel / 屏保级窗口） |
| 音频 | PyAudio · Core Audio（macOS）/ WASAPI（Windows） |
| 语音识别 | SenseVoiceSmall · funasr_onnx · ONNX Runtime INT8 · 独立识别进程 |
| 翻译 | 流式 LLM（Qwen2.5）或 Google，经托管 API |
| 登录 / 计费 | Supabase · GitHub / Google OAuth · 爱发电卡密 |
| 更新 | GitHub Releases · macOS 仅更新程序包，支持断点续传 |
| 打包 | PyInstaller · dmgbuild（macOS）/ Inno Setup（Windows） |

语音识别完全本地。翻译文本会按所选引擎发到网络服务。

---

## 购买与激活

在 [爱发电](https://afdian.com/a/mikema) 购买卡密，然后到 **设置 → 兑换激活码** 激活。

> 目前货架上只有 **1 个月** 卡密。下单请选择 **1 Month**，否则可能无法生成激活码。

<img width="355" alt="购买须知" src="https://github.com/user-attachments/assets/e0ca6552-b9ad-42ad-a3f9-6a4f1b445cf0" />

---

## 路线图

- [x] SenseVoiceSmall ONNX INT8 本地识别
- [x] 独立识别进程，窗口不再卡住
- [x] 语义单元调度的流式翻译
- [x] 双引擎（AI Model / Google）及自动回退
- [x] macOS / Windows：7 语种配对、对调、偏好记忆
- [x] 可回看的字幕记录，以及就地改写上一句
- [x] 导出 Word / TXT / Markdown
- [x] 独立设置面板
- [x] macOS 全屏悬浮
- [x] OAuth 登录、游客试用、应用内兑换
- [x] macOS 应用内更新（只更程序，支持续传）
- [ ] Windows 应用内更新
- [ ] 更多语种
- [ ] 进一步压延迟、提升识别质量

---

## 支持

如果 ZenInterpreter 对你有用：

- 给仓库点一颗 Star
- 问题与建议请到 [GitHub Issues](https://github.com/mahongbql/ZenInterpreter/issues)
- 转给同样需要桌面实时翻译的朋友
