# ZenInterpreter

<p align="center">
  <b>Real-time desktop interpreter for macOS and Windows</b><br>
  On-device speech recognition · Streaming translation · Always-on-top bilingual captions
</p>

<p align="center">
  <b>English</b> · <a href="./README_ZH.md">简体中文</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Windows-blue" alt="Platform">
  <img src="https://img.shields.io/badge/Release-macOS%201.6.0-blue" alt="Release">
  <img src="https://img.shields.io/badge/Speech%20recognition-On%20device-orange" alt="On-device speech recognition">
  <img src="https://img.shields.io/badge/Languages-7-green" alt="7 languages">
</p>

**ZenInterpreter** is real-time simultaneous interpretation software for the desktop. It listens to a microphone or to system audio, transcribes speech on the device, and shows live bilingual subtitles in a floating window above meetings, lectures, browsers, and video.

It is built for people who need to follow another language as it is spoken: international meetings, online courses, client calls, livestreams, and original-language video. Speech recognition runs locally. Only the recognized text is sent for translation.

---

## Download

| Platform | Installer |
| :--- | :--- |
| macOS 12+ | [Download ZenInterpreter for macOS](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter.dmg) |
| Windows | [Download ZenInterpreter for Windows](https://zeninterpreter-download.oss-cn-beijing.aliyuncs.com/ZenInterpreter_Setup_v1.0.0.exe) |

The current macOS release is **1.6.0**. After installation, open **Settings → Check for updates** to install later builds. The update replaces the application only and keeps the local speech model. An interrupted download can resume.

Windows updates are published on the [release page](https://github.com/mahongbql/ZenInterpreter/releases).

[Watch a short demo](https://github.com/user-attachments/assets/f79f0b52-764a-4a75-8f50-3f55b277cbbd)

---

## Where it is used

- **Meetings and calls** — live captions over Zoom and other conferencing apps
- **Courses and webinars** — follow a lecture without waiting for uploaded subtitles
- **Video and livestreams** — caption YouTube, local files, and streams from system audio
- **Client conversations** — keep a bilingual record of a cross-language call
- **Listening practice** — read the translation while the original audio continues

---

## Capabilities

### Always-on-top captions

A frameless, translucent subtitle window stays above other applications. On macOS it also covers fullscreen apps and other Spaces. Hover to show the toolbar, drag to move, and resize from the edges. It works across multiple displays.

The window opens immediately on first launch while the recognizer loads, so the application is visible during startup.

### Bilingual transcript

The overlay keeps a running log, not a single line that disappears:

1. A live preview of the original speech
2. The final source line, then a translation that streams in as it is produced
3. Earlier pairs remain in the window — scroll up to reread, and the view follows the latest line again at the bottom

When recognition revises the previous sentence, that line is updated in place.

### On-device speech recognition

**SenseVoiceSmall** runs locally with **ONNX Runtime (INT8)** in a separate process, so the caption window stays responsive while the model loads or decodes. Audio is not uploaded. Filler words, cut-off fragments, and obvious recognition noise are removed before translation.

### Two translation engines

| Engine | Best for |
| :--- | :--- |
| **AI Model** | Talks and conversation. Uses context, corrects recognition slips, and keeps the wording natural. |
| **Google** | Lower latency and a more literal translation. |

If Google is unavailable, ZenInterpreter falls back to the AI engine. Long speech is translated in semantic units, so a sentence does not have to finish before the first words appear.

### Languages

The default pair is **English → Chinese**. Any pair among these languages can be selected, and the direction can be swapped in one click:

English · Chinese · Japanese · Korean · Spanish · French · German

The language pair, engine, and audio device are saved between launches. The same set is available on macOS and Windows.

### Session export

From Settings, export the current session as Word (`.docx`), plain text (`.txt`), or Markdown (`.md`). The default location is the Desktop.

### System audio or microphone

Choose any input device in Settings. When **BlackHole** (macOS) or **Stereo Mix** (Windows) is installed, it is selected automatically so captions follow system audio — a meeting, a browser, or a local video — rather than only the microphone.

### Account

Sign in with GitHub or Google, or start a **3-hour guest trial** per device, per day. Pro is purchased in the application. Checkout opens in the browser and unlocks after payment. Activation codes are issued for organizations, promotions, and support.

---

## Get started

1. Install the package for your system from the [download table](#download).
2. Open ZenInterpreter and sign in, or start the guest trial.
3. Hover the caption window and open **Settings**:
   - **Audio device** — microphone, or BlackHole / Stereo Mix for system audio
   - **Engine** — AI Model or Google
   - **Languages** — source, target, or swap
4. Speak or play audio. Scroll the overlay to review earlier lines, then export the session from Settings.

### Caption system audio on macOS

1. Install [BlackHole 2ch](https://existential.audio/blackhole/).
2. In **Audio MIDI Setup**, create a **Multi-Output Device** that includes your speakers and BlackHole.
3. Set the macOS output to that Multi-Output Device.
4. In ZenInterpreter, select **BlackHole** as the input. It is selected automatically when detected.

On Windows, enable **Stereo Mix** (or another loopback device) in the sound control panel, then select it in Settings.

---

## System requirements

| | macOS | Windows |
| :--- | :--- | :--- |
| Version | macOS 12 or later | Windows 10 or later |
| Processor | Apple Silicon or Intel | 64-bit |
| Display | One or more displays, including fullscreen and multiple Spaces | Standard desktop session |
| Audio | Microphone, or BlackHole for system audio | Microphone, or Stereo Mix for system audio |
| Network | Required for translation and sign-in. Speech recognition does not need a network connection after the model is installed. | Same |

---

## Privacy

| Data | Where it goes |
| :--- | :--- |
| Microphone and system audio | Stays on the device. Recognition runs locally. |
| Recognized text | Sent to the selected translation engine. |
| Account | GitHub or Google sign-in, used to manage the trial and Pro. |

---

## FAQ

**Can it caption a Zoom meeting or a YouTube video?**  
Yes. Capture system audio with BlackHole on macOS or Stereo Mix on Windows, then leave ZenInterpreter above the meeting or the browser.

**Does speech leave the computer?**  
No. Audio is recognized on the device. The text of each utterance is sent for translation.

**Which languages are supported?**  
English, Chinese, Japanese, Korean, Spanish, French, and German, in any direction.

**What is the difference between the two engines?**  
AI Model is a streaming interpreter: it smooths recognition errors and reads more like spoken interpretation. Google is faster and more literal.

**Is there a trial?**  
Yes. Each device includes 3 hours of guest use per day. Pro is available from Settings.

**Will an update download the speech model again?**  
On macOS, no. In-app updates replace the program and keep the model already on the machine.

---

## Plans

| | Guest trial | Pro |
| :--- | :--- | :--- |
| Daily use | 3 hours per device | Unlocked after purchase |
| Captions, export, language pairs | Included | Included |
| How to start | Open the app | **Settings → Upgrade** |

Activation codes are for organizations, promotions, and support. They are redeemed with **Settings → Activate code**.

---

## How it is built

| Layer | Implementation |
| :--- | :--- |
| Interface | PyQt6. On macOS, an AppKit overlay (NSPanel) at screensaver window level |
| Audio | PyAudio, Core Audio on macOS, WASAPI on Windows |
| Speech recognition | SenseVoiceSmall, ONNX Runtime INT8, separate worker process |
| Translation | Streaming language model (Qwen2.5) or Google |
| Sign-in | GitHub and Google |
| Packaging | PyInstaller. macOS disk image, Windows installer |
| Updates | macOS in-app update with resumable download. Windows via the release page |

---

## Platform status

| Platform | Status |
| :--- | :--- |
| macOS | Released. In-app updates. Current release 1.6.0 |
| Windows | Released. Installer available. Updates from the release page |
| Mobile | Not available |

Planned work: Windows in-app updates, additional languages, and further reductions in caption latency.

---

## Support

Questions, defects, and feature requests: [GitHub Issues](https://github.com/mahongbql/ZenInterpreter/issues).

Release history: [GitHub Releases](https://github.com/mahongbql/ZenInterpreter/releases).
