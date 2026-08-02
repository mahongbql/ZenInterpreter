# ZenInterpreter 🚀

<p align="center">
  <b>AI 驱动的轻量级桌面端实时同声传译与语音翻译软件</b>
</p>

<p align="center">
  <a href="./README.md">English</a> • <b>简体中文</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Windows-blue" alt="Platform">
  <img src="https://img.shields.io/badge/Inference-ONNX%20Runtime-green" alt="ONNX Runtime">
  <img src="https://img.shields.io/badge/Model-SenseVoice-orange" alt="SenseVoice">
</p>

---

## 📽️ 效果演示

https://github.com/user-attachments/assets/6c25eafe-14c0-4ddc-ab72-29915665fd6c

---

## ✨ 产品介绍

**ZenInterpreter** 是一款 AI 驱动的实时同声翻译软件。它能够实时监听语音输入，将语音快速转换为文本，并结合 AI 翻译能力，实现自然流畅的跨语言交流体验。

**适用于：**
- 🌎 **国际会议**：跨国团队与远程协同沟通
- 🎓 **在线学习**：无字幕外文网课与学术讲座
- 🎤 **演讲直播**：实时生成并翻译字幕
- 💼 **商务沟通**：线上客户洽谈与外贸交流
- ✈️ **海外交流**：实时语音与听力辅助

ZenInterpreter 致力于提供**更快、更轻、更私密**的 AI 翻译体验。

---

## 🚀 核心特点

### ⚡ 实时语音识别
采用高性能 SenseVoiceSmall 结合 ONNX Runtime 推理引擎，实现极致低延迟的语音理解与出字体验。

### 🪶 轻量化 AI 架构
放弃繁重的深度学习运行环境，极大幅度精简软件体积与内存占用：
- ❌ **无需** 安装 PyTorch 或庞大的深度学习框架
- ✅ **ONNX** 高效引擎直接推理
- ✅ 更小体积、更低 CPU/内存占用、秒级启动速度

### 🔒 隐私优先
支持本地 AI 模型推理，音频数据无需强制上传至云端服务器，保障私密会议与敏感商务交流的安全。

---

## 💻 平台支持与下载

你可以从 [GitHub Releases/Tags](https://github.com/mahongbql/ZenInterpreter/tags) 下载最新编译好的安装包。

| 操作系统 | 状态 | 备注 |
| :--- | :---: | :--- |
| **macOS** | ✅ 已支持 | 支持 macOS 12+ (Apple Silicon / Intel) |
| **Windows** | ✅ 已支持 | 编译安装包已发布 |
| **APP** | 🚧 计划中 | 正在适配中 |

---

## 🛠️ 技术栈

| 模块 | 使用技术 |
| :--- | :--- |
| **UI 框架** | PyQt6 |
| **音频采集** | PyAudio |
| **语音识别** | SenseVoiceSmall (ONNX) |
| **推理引擎** | ONNX Runtime |
| **打包分发** | PyInstaller / Inno Setup |

---

## 💳 购买与激活

您可以购买 ZenInterpreter 兑换码以解锁完整功能：

* 🛒 **购买地址**：[爱发电 (Afdian)](https://afdian.com/a/mikema)

> ⚠️ **重点提示**
> 目前库存**仅有 1 个月期限**的兑换码。购买时请**务必只选择 1 个月**，**切勿选择其他月份**，以免造成无法正常兑换或发放失败。
> 
> <img width="355" alt="购买提示" src="https://github.com/user-attachments/assets/e0ca6552-b9ad-42ad-a3f9-6a4f1b445cf0" />

---

## 📅 路线图 (Roadmap)

- [x] 集成 SenseVoiceSmall ONNX 模型
- [x] 优化实时低延迟语音识别与 AI 翻译流
- [x] 发布 macOS 应用与 Windows 安装包
- [ ] 支持更多语言模型拓展
- [ ] 进一步降低 推理/翻译 延迟
- [ ] UI / UX 视觉与交互重构

---

## ⭐ 支持项目

如果 ZenInterpreter 对你有帮助，欢迎：
* 点一个 **Star ⭐** 给予鼓励！
* 在 [Issues](https://github.com/mahongbql/ZenInterpreter/issues) 中反馈 Bug 或提出建议。
* 分享给身边需要实时同传与翻译的朋友！
