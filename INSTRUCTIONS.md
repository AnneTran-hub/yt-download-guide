# Installation and Usage Guide

This guide explains how to install **yt-dlp** and **FFmpeg** on Windows and use them through PowerShell.

> The examples below use drive `D:` to avoid using unnecessary space on the Windows `C:` drive.
>
> You may use another folder if you prefer.

---

## 1. Install yt-dlp

Go to the official yt-dlp releases page:

https://github.com/yt-dlp/yt-dlp/releases/latest

Under **Assets**, find and download:

```text
yt-dlp.exe
```

## 2. Install FFmpeg

Go to the FFmpeg Windows builds page:

https://www.gyan.dev/ffmpeg/builds/

Under **Release builds**, find and download:

```text
ffmpeg-release-essentials.zip
```

## 3. Verify the Installation

Open **PowerShell** and navigate to the yt-dlp folder:

```powershell
cd D:\Programs\yt-dlp
```

### Check yt-dlp

Run:

```powershell
.\yt-dlp.exe --version
```

If yt-dlp is installed correctly, PowerShell will display the installed version number.

For example:

```text
2026.08.19
```

> The version number may be different depending on the latest version you downloaded.

### Check FFmpeg

Run:

```powershell
.\ffmpeg.exe -version
```

If FFmpeg is installed correctly, PowerShell will display information starting with:

```text
ffmpeg version ...
```

For example:

```text
ffmpeg version 9.0.1 ...
```

> The FFmpeg version may be different depending on the version you downloaded.

### Installation Complete

If **both commands display their version information without errors**, yt-dlp and FFmpeg are ready to use.

You can now proceed to the next step to download a video.

## 4. Download a YouTube Video

Copy the URL of the YouTube video you are authorized to download.

Open **PowerShell** and make sure you are in the yt-dlp folder:

```powershell
cd D:\Programs\yt-dlp
```

Run the following command:

```powershell
.\yt-dlp.exe -f "bv*+ba/b" --merge-output-format mp4 "VIDEO_URL"
```

> bv*    = best available video
> ba     = best available audio
> +      = combine video and audio
> /b     = fallback to the best combined format

Replace `VIDEO_URL` with the actual YouTube video URL.

For example:

```powershell
.\yt-dlp.exe -f "bv*+ba/b" --merge-output-format mp4 "https://www.youtube.com/watch?v=xxxxxxxxxxx"
```

yt-dlp will download the video and audio, and FFmpeg will merge them into a single video file.

## 5. Find the Downloaded Video

Once the download is complete, the video will be saved in your yt-dlp folder:

```text
D:\Programs\yt-dlp
```

Open the folder in **File Explorer** to find your downloaded video.

For example:

```text
D:\Programs\yt-dlp\
│
├── yt-dlp.exe
├── ffmpeg.exe
├── ffprobe.exe
├── ffplay.exe
└── downloaded-video.mp4
```

Your video is now ready to play locally.
