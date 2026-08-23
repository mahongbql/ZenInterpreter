# ZenInterpreter

<p align="center">
  <b>Lightweight real-time desktop interpreter</b><br>
  Local speech recognition · Streaming AI translation · Always-on-top overlay
</p>

<p align="center">
  <b>English</b> • <a href="./README_ZH.md">简体中文</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Windows-blue" alt="Platform">
  <img src="https://img.shields.io/badge/ASR-SenseVoice%20ONNX%20INT8-orange" alt="SenseVoice">
  <img src="https://img.shields.io/badge/Inference-ONNX%20Runtime-green" alt="ONNX Runtime">
  <img src="https://img.shields.io/badge/Translate-AI%20%7C%20Google-purple" alt="Translation">
</p>

---

## Demo

https://github.com/user-attachments/assets/f79f0b52-764a-4a75-8f50-3f55b277cbbd

---

## Overview

**ZenInterpreter** is a floating subtitle window for macOS and Windows. It listens to your microphone or system audio, transcribes speech on-device, and streams a live translation on top of Zoom, browsers, lectures, and fullscreen apps.

Built for people who need to **follow another language in real time**, without installing a heavyweight AI stack.

**Typical use cases**

- International meetings and remote collaboration
- Online courses, webinars, and raw video
- Live streams that need instant captions
- Client calls and cross-border sales
- Listening practice while watching original-language content

---

## Highlights

### Always-on-top overlay

Frameless, translucent subtitle window that stays above other apps. On macOS it also covers fullscreen apps and other Spaces. Hover to reveal the toolbar; drag to move; pull the edges to resize. Works across multiple displays.

### Local speech recognition

**SenseVoiceSmall** runs locally through **ONNX Runtime (INT8)**. No PyTorch. Audio never leaves your machine — only recognized text is sent out for translation.

### Dual translation engines

Switch anytime in Settings:

| Engine | What it does |
| :--- | :--- |
| **AI Model** | Context-aware streaming interpretation. Corrects ASR slips, drops fillers, and keeps phrasing natural. Best for talks and conversations. |
| **Google** | Fast, literal machine translation with lower overhead. Best when you want speed over fluency. |

If Google is unavailable, the app automatically falls back to the AI engine.

### Live dual-line captions

While you speak (or the meeting plays), the overlay shows:

1. A live **preview** of the original transcript
2. The **final source line**, then a **streaming translation** that fills in word by word

Translation is dispatched in semantic units (not one giant block), so long speech stays low-latency.

### Languages

Default pair is **English → 中文**.

| Platform | Language support |
| :--- | :--- |
| **macOS** | Any pair among English · 中文 · 日本語 · 한국어 · Español · Français · Deutsch, plus a one-click swap |
| **Windows** | English → 中文 only for now |

Your language pair and engine choice are remembered across launches.

### Audio input

Pick any input device in Settings. If **BlackHole** (macOS) or **Stereo Mix** (Windows) is present, it is selected automatically so you can caption system audio — Zoom, YouTube, a local video — not just the microphone.

### Account

- GitHub / Google one-click login
- **30-minute guest trial** per device, per day
- Redeem a license key in Settings; expired members can stay in the app and renew without logging out again

---

## Quick start

1. Download the latest build for your OS from [GitHub Tags](https://github.com/mahongbql/ZenInterpreter/tags).
2. Open the app and sign in with GitHub, Google, or start the guest trial.
3. Hover the overlay → **⚙ Settings**:
   - **Audio device** — microphone, or BlackHole / Stereo Mix for system audio
   - **Engine** — AI Model or Google
   - **Languages** — on macOS, pick source / target or tap ⇄ to swap; on Windows this is fixed to English → 中文
4. Play or speak. Captions appear in the overlay.

### Capture system audio on macOS

To translate Zoom / a browser / a local video instead of the mic:

1. Install [BlackHole 2ch](https://existential.audio/blackhole/).
2. In **Audio MIDI Setup**, create a **Multi-Output Device** that includes both your speakers and BlackHole.
3. Set macOS output to that Multi-Output Device.
4. In ZenInterpreter, choose **BlackHole** as the input (auto-selected when detected).

On Windows, enable **Stereo Mix** (or equivalent loopback) in the sound control panel, then select it as the input in Settings.

---

## Platforms

| Platform | Status | Notes |
| :--- | :---: | :--- |
| **macOS** | Available | 12+, Apple Silicon and Intel · full language pairs |
| **Windows** | Available | Installer available · English → 中文 only |
| **Mobile** | Planned | — |

---

## Tech stack

| Layer | Stack |
| :--- | :--- |
| UI | PyQt6 · AppKit overlay on macOS (NSPanel / screensaver window level) |
| Audio | PyAudio · Core Audio (macOS) / WASAPI (Windows) |
| ASR | SenseVoiceSmall · funasr_onnx · ONNX Runtime INT8 |
| Translation | Streaming LLM (Qwen2.5) or Google, via a hosted API |
| Auth / billing | Supabase · GitHub / Google OAuth · Afdian license keys |
| Packaging | PyInstaller · dmgbuild (macOS) / Inno Setup (Windows) |

Speech recognition is fully local. Translation text is sent to the selected engine over the network.

---

## License

Buy a license key on [Afdian](https://afdian.com/a/mikema), then redeem it in **Settings → 兑换激活码**.

> Currently only **1-Month** keys are in stock. Choose **1 Month** at checkout, otherwise key generation may fail.

<img width="355" alt="Purchase Notice" src="https://github.com/user-attachments/assets/e0ca6552-b9ad-42ad-a3f9-6a4f1b445cf0" />

---

## Roadmap

- [x] SenseVoiceSmall ONNX INT8 on-device ASR
- [x] Streaming translation with semantic-unit scheduling
- [x] Dual engines (AI Model / Google) with auto-fallback
- [x] macOS: 7-language pairs, swap, and preference persistence
- [x] macOS fullscreen overlay and independent settings panel
- [x] Windows build (English → 中文)
- [x] OAuth login, guest trial, and in-app license redeem
- [ ] Windows multilingual pairs
- [ ] More languages
- [ ] Further latency and ASR quality work

---

## Support

If ZenInterpreter helps you:

- Star the repo
- Open an issue on [GitHub Issues](https://github.com/mahongbql/ZenInterpreter/issues)
- Share it with anyone who needs live desktop translation
