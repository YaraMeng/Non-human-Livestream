# AI Video Generation Workflow (Lobster Multi-Agent System)

## Overview

This project implements a multi-agent, multimodal content generation pipeline that automatically converts text prompts into fully produced videos with audio.

Pipeline: Text → Story → Image → Video → Audio → Merge → Output

## System Architecture

### 1. Story Agent (YaraBot)

Converts user input into a cinematic scene description.

Output: structured prompt

### 2. Production Agent (JennyBot)

Handles the full media pipeline:

| Step | Tool | Description |
| --- | --- | --- |
| Image | Higgsfield API | Generate keyframe |
| Video | Seedance 2.0 | Animate image |
| Audio | ElevenLabs | Generate sound |
| Merge | ffmpeg + moviepy | Combine video and audio |

### 3. Controller (User / Main Bot)

- Sends prompt
- Orchestrates workflow

## Workflow (Step-by-Step)

### Step 1 — Input

User sends a prompt:

"A robot in a futuristic library touching a glowing book"

### Step 2 — Story Generation (YaraBot)

Output example:

"A lone silver robot stands in a glowing library..."

### Step 3 — Image Generation

Using Higgsfield:

`generate_image(prompt)`

### Step 4 — Video Generation

`generate_video(image_path)`

### Step 5 — Audio Generation

Using ElevenLabs:

`generate_audio(prompt)`

### Step 6 — Merge Video + Audio

```python
from moviepy.editor import VideoFileClip, AudioFileClip

video = VideoFileClip("video.mp4")
audio = AudioFileClip("audio.mp3")

final = video.set_audio(audio)
final.write_videofile("output.mp4")
```

### Step 7 — Output

Final file:

`output.mp4`

## Installation Guide

### 1. Install Python dependencies

Using uv:

```bash
uv pip install moviepy
```

### 2. Install ffmpeg

Mac / Linux:

```bash
brew install ffmpeg
```

Ubuntu:

```bash
sudo apt install ffmpeg
```

Windows:

Download from:

https://ffmpeg.org/download.html

### 3. Verify installation

```bash
ffmpeg -version
```

## Project Structure

```text
project/
│
├── agents/
│   ├── yarabot.py
│   ├── jennybot.py
│
├── scripts/
│   ├── merge.py
│
├── output/
│   ├── video.mp4
│   ├── audio.mp3
│   └── final.mp4
│
└── README.md
```

## Full Automation Logic

Pseudo flow:

```python
def run_pipeline(user_input):
    story = yarabot.generate_story(user_input)

    image = generate_image(story)
    video = generate_video(image)
    audio = generate_audio(story)

    final = merge(video, audio)

    return final
```

## Example Usage

```bash
python main.py "A cyberpunk city at night with flying cars"
```

## Notes

- Higgsfield API key required
- ElevenLabs API key required
- ffmpeg must be installed
- Discord upload size limits may apply

## Future Improvements

- Subtitle generation using Whisper
- Multi-scene video stitching
- Character voice acting
- Real-time generation pipeline

## Key Concept

This system demonstrates:

- Multi-agent collaboration
- Multimodal AI generation
- Automated content production pipeline
