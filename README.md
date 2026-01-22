# 🎬 Video Downloader 

A powerful desktop application for downloading videos from YouTube and other platforms with high-quality output and browser cookie support.

---

## ✨ Features

- 🚀 **Fast & Reliable** - Download videos at maximum speed with automatic retry
- 🎨 **Modern UI** - Clean, intuitive Electron-based interface
- 🔐 **Cookie Support** - Access private/age-restricted videos using browser cookies (Firefox, Chrome, Edge, Opera)
- 🎞️ **High Quality** - Automatic merging of best video + audio tracks using FFmpeg
- 📂 **Custom Save Locations** - Choose where to save your downloads
- 🔄 **Multiple Downloads** - Download multiple videos without restarting the app
- 💻 **Cross-Platform Ready** - Built with Electron for Windows (Linux/Mac support coming soon)

---

## 📦 Downloads

Choose the version that works best for you:

### 🔧 For End Users

| File | Description | Size |
|------|-------------|------|
| **`setup-packed.zip`** | **Recommended** - Full installer with setup wizard | ~906 MB |
| **`setup-unpacked.zip`** | Portable version - No installation required, just extract and run | ~1010 MB |

### 👨‍💻 For Developers

| File | Description |
|------|-------------|
| **`video_downloader.zip`** | Complete source code with all dependencies | |~1080 MB|

---

## 🚀 Quick Start

### Option 1: Installer (Recommended)

1. Download **`setup-packed.zip`**
2. Extract the archive
3. Run **`Video Downloader Setup 1.0.0.exe`**
4. Follow the installation wizard
5. Launch from Start Menu or Desktop shortcut

### Option 2: Portable

1. Download **`setup-unpacked.zip`**
2. Extract to any folder
3. Run **`Video Downloader.exe`**
4. No installation needed!

---

## 🎯 How to Use

1. **Launch the application**
2. **Paste a video URL** (YouTube, Vimeo, etc.)
3. **Select save location** (optional - defaults to Videos folder)
4. **Click Download**
5. **Wait for completion** - Progress shown in real-time

That's it! Your video will be saved in MP4 format with the best available quality.

---

## ⚙️ Technical Details

### Built With

- **Frontend**: Electron 30.5.1 + HTML/CSS/JavaScript
- **Backend**: Python 3.14 + Flask
- **Downloader**: yt-dlp (latest)
- **Video Processing**: FFmpeg
- **JavaScript Runtime**: Deno (for advanced extraction)

### System Requirements

- **OS**: Windows 10/11 (64-bit)
- **RAM**: 4 GB minimum
- **Disk Space**: 5 GB for installation + space for downloads
- **Internet**: Required for downloading videos

---

## 🔒 Privacy & Security

- ✅ **No telemetry** - Your data stays on your device
- ✅ **Local processing** - All downloads happen on your machine
- ✅ **Open source** - Inspect the code yourself
- ✅ **No ads** - Clean, distraction-free experience

---

## 🐛 Known Issues

- Backend console window may remain open after closing the app (fix in progress)
- Some protected content may require browser cookies to be available

---

## 📝 Changelog

### v1.0.0 - Initial Release (January 22, 2026)

**Features:**
- ✨ Initial public release
- 🎬 YouTube video downloading with best quality selection
- 🔐 Browser cookie integration for private videos
- 🎨 Modern, user-friendly interface
- 📂 Custom download location selection
- 🔄 Support for multiple consecutive downloads

**Technical:**
- 🏗️ Electron-based desktop application
- 🐍 Python Flask backend
- 🎞️ FFmpeg integration for video merging
- 📦 NSIS installer for easy setup

---

## 🤝 Support

If you encounter any issues or have suggestions:

1. Star ⭐ the repository if you find it useful!

---

## 📄 License

[Your License Here - e.g., MIT, GPL-3.0, etc.]

---

## 🙏 Acknowledgments

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - Powerful video downloader
- [FFmpeg](https://ffmpeg.org/) - Video processing
- [Electron](https://www.electronjs.org/) - Cross-platform framework
- [Flask](https://flask.palletsprojects.com/) - Python web framework

---

**Made with ❤️ by [NiceTryJony]**

*If you like this project, consider giving it a star ⭐*
