<div align="center">

<img src="assets/icon.ico" width="80" alt="Video Downloader Logo">

# 🎬 Video Downloader

**Download videos. Generate subtitles. Read AI summaries. All locally.**

![Status](https://img.shields.io/badge/status-WIP-orange?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Windows-blue?style=flat-square)
![Electron](https://img.shields.io/badge/Electron-30-47848F?style=flat-square&logo=electron)
![Python](https://img.shields.io/badge/Python-3.14-3776AB?style=flat-square&logo=python)
![License](https://img.shields.io/badge/license-ISC-green?style=flat-square)

</div>

---

## ✨ Features

| Feature | Description |
|---|---|
| ⬇️ **Downloading** | YouTube & more via yt-dlp, multi-URL queue with auto-retry |
| 🔐 **Cookie Support** | Access private/age-restricted videos via Firefox, Chrome, Edge, Opera |
| 🎙️ **Subtitles** | Auto-generation via faster-whisper (Base / Small / Turbo / Medium) |
| 🤖 **AI Conspect** | Local LLM (Ollama) generates summaries with timecodes |
| 🎞️ **Built-in Player** | PiP, position saving, multiple themes |
| 📄 **PDF Export** | Export your AI conspect to PDF in one click |
| 🔒 **100% Local** | No cloud, no API keys, no tracking |

---

## 🎯 Who Is This For?

### 🎓 Students & Note-takers
Download a lecture, podcast, or documentary → auto-generate subtitles → let the AI produce a structured summary with timecodes → export to PDF. No subscription, no cloud upload, no one reading your notes but you.

### 🎬 Video Editors
Grab source footage from any supported platform at the best available quality. Use auto-generated subtitles for transcript-based editing or as a starting point for captions. Everything stays on your machine.

### 🔒 Privacy-conscious Users
All processing happens locally — no data leaves your device. No account required, no analytics, no ads. What you download and watch is your business.

### 📺 Casual Viewers
Paste a URL, hit Download, watch in the built-in player. That's it. Works offline after download — no buffering, no algorithm, no autoplay traps.

---

## 📦 Downloads

| File | Description | Size |
|---|---|---|
| **`Video_Downloader.zip`** | **Recommended** — Full installer with setup wizard | ~512 MB |

---

## 🚀 Installation

### Option 1: Installer (Recommended)

1. Download **`Video_Downloader.zip`** from ```Releases```
2. Extract the archive
3. Run **`Video Downloader Setup 1.0.0.exe`**
4. Follow the installation wizard
5. Launch from Start Menu or Desktop shortcut


### Option 2: Install form Google Drive 

1. Download **`Video_Downloader.zip`** from [Install](https://drive.google.com/file/d/1cu-1I4LOCbKU3nBk0v5LGx4UieR9dxD5/view?usp=sharing)
2. Extract the archive
3. Run **`Video Downloader Setup 1.0.0.exe`**
4. Follow the installation wizard
5. Launch from Start Menu or Desktop shortcut


### Option 3: From Source

```bash
# 1. Clone the repository
git clone https://github.com/your-username/video-downloader.git
cd video-downloader

# 2. Install Node dependencies
npm install

# 3. Install Python dependencies
pip install flask faster-whisper yt-dlp

# 4. Run the app
npm start
```

> ⚠️ On first launch, the Flask server starts automatically on port `5000`.

### For AI Summaries (optional)

```bash
# Install Ollama — https://ollama.ai/download

# Pull recommended model (works on 4GB VRAM)
ollama pull gemma3:4b
```

---

## 🎯 How to Use

1. **Launch the application**
2. **Paste a video URL** (YouTube, Vimeo, etc.)
3. **Select save location** (optional — defaults to Videos folder)
4. **Click Download**
5. **Watch the real-time progress bar**

Your video will be saved in MP4 or another format what you want and at the best available quality.

---

## 🏗️ Architecture

```
┌─────────────────────────────────┐
│         Electron (UI)           │
│  index.html / index.js / CSS    │
│  IPC → preload.js               │
└──────────────┬──────────────────┘
               │ HTTP (localhost:5000)
┌──────────────▼──────────────────┐
│       Python Flask Backend      │
│  app.py          yt-dlp         │
│  subtitle_generator.py          │
│  faster-whisper  ffmpeg         │
│  Ollama (local LLM inference)   │
└─────────────────────────────────┘
```

- **Electron** — renders UI and manages windows
- **Flask** — handles downloading, transcription & LLM requests
- **yt-dlp** — extracts video from hundreds of platforms
- **faster-whisper** — local transcription via Whisper
- **Ollama** — local inference, recommended model `gemma3:4b`

---

## ⚙️ System Requirements

| Component | Minimum | Recommended |
|---|---|---|
| OS | Windows 10 x64 | Windows 11 x64 |
| RAM | 4 GB | 16 GB |
| GPU VRAM | — | 6 GB (Turbo/Medium Whisper + Ollama) |
| Disk | ~2 GB | > 10 GB |
| Internet | Required | Required |

---

## 🔒 Privacy & Security

- ✅ **No telemetry** — your data stays on your device
- ✅ **Local processing** — all downloads happen on your machine
- ✅ **Open source** — inspect the code yourself
- ✅ **No ads** — clean, distraction-free experience

---

## 🗺️ Roadmap

- [x] Multi-URL download queue
- [x] Browser cookie support (Firefox, Chrome, Edge, Opera)
- [x] Subtitle generation with SSE progress streaming
- [x] AI conspect with timecodes + PDF export
- [x] Built-in player (PiP, themes, position memory)
- [x] Rezka / KinoGo support
- [x] cinemahd-deaf.org HLS streaming support

---

## 🛟 FAQ & Troubleshooting

Full in-app help is available via the **FAQ & Help Center** button. Below is a quick reference for the most common issues.

---

### 📥 Download Issues

<details>
<summary><strong>Download fails with "Backend error" or connection timeout</strong></summary>

- Port 5000 is blocked or already in use by another app
- Backend crashed — open Debug Console and look for red `[BACKEND ERR]` messages
- Antivirus (e.g. Windows Defender) is blocking `app.exe` or `yt-dlp`
- Invalid URL or unsupported platform

**Fix:** Open Task Manager → end all `app.exe` processes → relaunch. If that doesn't help, temporarily disable antivirus and retry.

</details>

<details>
<summary><strong>Downloaded video quality is lower than selected</strong></summary>

- Source video was uploaded in lower quality (you can't download 1080p from a 720p upload)
- Age-restricted content requires browser cookies for higher quality streams
- Some regions have quality restrictions

**Fix:** Enable browser cookies in Advanced Settings → try "Best Available" instead of a specific resolution.

</details>

<details>
<summary><strong>Download is extremely slow or stalls</strong></summary>

- 4K videos are 5–10× larger than 1080p — they just take longer
- Platform is throttling the download
- Your connection is unstable or shared

**Fix:** Use WebM format (no conversion step), lower quality to 1080p, use wired Ethernet, close other bandwidth-heavy apps.

</details>

<details>
<summary><strong>Downloaded file is corrupted or won't open</strong></summary>

- Connection dropped mid-download
- Disk ran out of space before download finished
- FFmpeg format conversion failed
- Antivirus quarantined the file during download

**Fix:** Delete the corrupted file → check free disk space (need 5 GB+ free) → retry. Check Debug Console for FFmpeg errors.

</details>

<details>
<summary><strong>"File already exists" error</strong></summary>

- A file with the same name and quality tag already exists in the target folder

**Fix (choose one):** Delete or rename the existing file → change save location → select a different quality (changes the filename) → switch format (MP4 ↔ WebM).

</details>

<details>
<summary><strong>Platform not supported or video fails immediately</strong></summary>

- ✅ Fully supported: YouTube, Vimeo, Dailymotion, Twitter/X
- ⚠️ Partially supported: Facebook, Instagram, TikTok (may need cookies)
- ❌ Not supported: Netflix, Disney+, and any DRM-protected or live-streaming content

**Fix:** Paste the URL, check Debug Console for the specific error.

</details>

---

### 🎬 Media Player

<details>
<summary><strong>Black screen or video won't play after download</strong></summary>

- Built-in player is disabled: Settings → Advanced → Enable Built-in Media Player
- File format not supported: MKV and AVI won't play in-app (use VLC instead)
- File is corrupted (see Download Issues above)

**Common error codes:**
- `MEDIA_ERR_SRC_NOT_SUPPORTED` — wrong format or file not found
- `MEDIA_ERR_DECODE` — corrupted file or unsupported codec
- `MEDIA_ERR_NETWORK` — incorrect file path

</details>

<details>
<summary><strong>No audio — video plays silently</strong></summary>

- You downloaded with "Video Only" type — re-download as "Video + Audio"
- System volume muted or wrong output device selected
- Source video has no audio track (some screen recordings, animations)

</details>

<details>
<summary><strong>Video looks pixelated or low quality in the player</strong></summary>

- The player shows exactly what's in the file — it can't enhance quality
- You downloaded 360p or 480p
- Actual quality was lower than requested (check `actual_quality` in Debug Console)

**Fix:** Re-download at 1080p or higher.

</details>

<details>
<summary><strong>Keyboard shortcuts not working</strong></summary>

Shortcuts require no text field to be focused.

| Shortcut | Action |
|---|---|
| `Space` | Play / Pause |
| `←` / `→` | Seek ±1 second |
| `F` | Toggle fullscreen |
| `ESC` | Exit fullscreen |

**Fix:** Click anywhere on the page background to deselect inputs, then try again.

</details>

---

### 🍪 Cookies & Browsers

<details>
<summary><strong>"No browser detected" warning</strong></summary>

- App couldn't find Firefox, Chrome, Edge, Brave, or Opera in default install paths
- Most public YouTube videos still work fine without cookies (up to 2160p via android_vr client)
- Age-restricted, private, or members-only videos require cookies

**Fix:** Settings → Advanced → Browser Paths → Browse to your browser's `.exe` → click "Test All Browser Paths".

</details>

<details>
<summary><strong>Browser path set but still shows "Not found"</strong></summary>

- You selected a shortcut (`.lnk`) instead of the actual `.exe`
- Browser installed in a non-standard location
- Typo or extra space in the path

**Default locations:**
- Firefox: `C:\Program Files\Mozilla Firefox\firefox.exe`
- Chrome: `C:\Program Files\Google\Chrome\Application\chrome.exe`
- Edge: `C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe`

**Fix:** Right-click your browser desktop shortcut → "Open file location" → copy the path.

</details>

<details>
<summary><strong>Cookies found but "unavailable"</strong></summary>

- Browser is currently running and its cookie database is locked
- Insufficient permissions to read browser profile data
- Cookie database is corrupted

**Fix:** Close the browser completely → click "Test All Browser Paths" again.

</details>

---

### ⚙️ Troubleshooting

<details>
<summary><strong>"Port 5000 already in use"</strong></summary>

- App is already running (opened twice)
- A previous instance crashed but the process is still alive
- Another program occupies port 5000

**Fix #1:** `Ctrl + Shift + Esc` → Task Manager → end all `app.exe` processes → relaunch.

**Fix #2 (CMD):**
```
taskkill /F /IM app.exe
```

**Find what's using the port:**
```
netstat -ano | findstr :5000
```
Then kill the process with that PID in Task Manager → Details tab.

</details>

<details>
<summary><strong>App crashes or freezes during download</strong></summary>

- Processing a large 4K file can freeze the UI temporarily — wait 2–3 min before panicking
- Low RAM (< 4 GB free)
- Disk full mid-download
- Network dropped during download

**Fix:** If frozen for 5+ minutes → Task Manager → End Task `app.exe` → delete partial file in Downloads → restart → try 720p first.

**4K requirements:** 8 GB+ RAM, 10 GB+ free disk, 50 Mbps+ stable connection.

</details>

<details>
<summary><strong>Settings not saving between sessions</strong></summary>

- App is opened in incognito/private mode (localStorage is wiped on close)
- Browser cleared cookies and site data
- localStorage disabled in browser privacy settings

**Fix:** Use normal (non-incognito) mode. When clearing browser history, uncheck "Cookies and site data".

**Settings that are saved:** download type, format, quality, browser paths, media player state, recent videos history.

</details>

<details>
<summary><strong>Debug Console error messages explained</strong></summary>

| Message | Meaning | Fix |
|---|---|---|
| `[BACKEND ERR] Port 5000 already in use` | Duplicate instance running | Kill all `app.exe`, relaunch |
| `MEDIA_ERR_SRC_NOT_SUPPORTED` | Unsupported format or missing file | Use MP4/WebM, re-download |
| `MEDIA_ERR_DECODE` | Corrupted file | Delete and re-download |
| `Sign in to confirm you're not a bot` | Need login cookies | Enable browser cookies in Advanced Settings |
| `[WARNING] actual_quality != requested_quality` | Source doesn't have that quality | Try "Best Available" |

**How to use the console effectively:**
- Open it **before** starting a download to catch backend errors early
- After a failure, scroll to the **first** red `ERROR` line — that's the root cause
- Copy the full log output when filing a bug report

</details>

---

### 🐛 Reporting a Bug

**Include in your report:**

1. App version (check Settings or About)
2. Windows version (10/11, build number)
3. What you did step by step
4. Expected vs actual behaviour
5. Full Debug Console output (copy-paste, not a photo)
6. Video URL (if not private)

**Example of a good report:**
```
Version: 1.0.0 | OS: Windows 11 22H2
Issue: All downloads fail immediately
Expected: Download starts
Actual: "Backend error" after 3 seconds
Console: [BACKEND ERR] Port 5000 already in use
Steps: 1) Open app  2) Paste URL  3) Click Download  4) Error
```

→ **[Open an Issue on GitHub](https://github.com/your-username/video-downloader/issues)**

---

## 🐛 Known Issues

- Backend console window may remain open after closing the app *(fix in progress)*
- Some protected content may require browser cookies to be available

---

## 🙏 Acknowledgments

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) — powerful video downloader
- [FFmpeg](https://ffmpeg.org/) — video processing
- [Electron](https://www.electronjs.org/) — cross-platform framework
- [Flask](https://flask.palletsprojects.com/) — Python web framework
- [faster-whisper](https://github.com/SYSTRAN/faster-whisper) — local transcription
- [Ollama](https://ollama.ai) — local LLM inference

---

## 📜 License

ISC © 2026

---

<div align="center">
  <sub>Made with ❤️ by NiceTryJony · If you like this project, give it a ⭐</sub>
  <br>
  <sub>Built with ☕ and ffmpeg-induced suffering</sub>
</div>
