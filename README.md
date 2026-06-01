# 英听学院 English Listening MVP

一个纯前端英语精听 / 跟读练习网站 Demo。

支持上传本地视频或粘贴 YouTube 链接，然后导入字幕文件，进行逐句精听、单句循环、听写、收藏、笔记和跟读录音练习。

## Features

- Upload local video files
- Embed YouTube videos by URL
- Import JSON / SRT / VTT subtitles
- Click subtitle cards to play a specific sentence
- Sentence loop playback
- Playback speed control
- Dictation mode: hide Chinese translation
- Favorite sentences
- Mark sentences as completed
- Add notes for each sentence
- Search subtitles, translations and notes
- Record shadowing practice
- Download recordings
- Export learning progress as JSON
- Dark / light theme toggle
- Responsive layout

## Tech Stack

This project is a single-file frontend demo.

- HTML
- CSS
- JavaScript
- YouTube IFrame Player API
- Browser localStorage
- Browser MediaRecorder API

No backend, database, or build step is required.

## File Structure

```text
english-listening-single/
├── index.html
└── README.md
```

All HTML, CSS and JavaScript are included in `index.html`.

## Subtitle Format

Recommended JSON format:

```json
[
  {
    "id": 1,
    "start": 0,
    "end": 3.2,
    "text": "I'm Singaporean, sir.",
    "translation": "我是新加坡人，先生。"
  }
]
```

SRT and VTT are also supported.

Example SRT:

```text
1
00:00:00,000 --> 00:00:03,200
I'm Singaporean, sir.
我是新加坡人，先生。
```

The first subtitle line is treated as the English sentence. The remaining lines are merged as the Chinese translation.

## YouTube Support

The app supports YouTube video playback by URL.

Supported URL examples:

```text
https://www.youtube.com/watch?v=xxxx
https://youtu.be/xxxx
https://www.youtube.com/shorts/xxxx
https://www.youtube.com/embed/xxxx
```

Note: this frontend-only version does not automatically fetch YouTube captions because of API, CORS and permission limitations.

Please import subtitles manually in JSON, SRT or VTT format.

## How to Use

1. Open `index.html` in a browser.
2. Upload a local video file, or paste a YouTube URL.
3. Import a subtitle file.
4. Click a subtitle card to play that sentence.
5. Use loop, dictation, notes, favorites and recording tools for practice.

## Deploy to Vercel

1. Upload `index.html` and `README.md` to a GitHub repository.
2. Open Vercel.
3. Click `Add New Project`.
4. Import the GitHub repository.
5. Choose `Other` or static site settings.
6. Click `Deploy`.

After deployment, Vercel will provide a public URL like:

```text
https://your-project-name.vercel.app
```

## Limitations

- No user login system yet.
- Learning records are saved in browser localStorage.
- YouTube captions are not automatically fetched.
- Automatic transcription and translation require a backend service.

## Future Improvements

- Add user accounts
- Save progress to a database
- Auto-generate subtitles with Whisper / OpenAI
- Auto-translate subtitles
- Add dictionary lookup
- Add pronunciation scoring
- Add playlist and course management
