# video-generation

## Purpose

Turn a structured scene plan into final rendered video deliverables.

## Input

- Structured YAML/JSON plan from script-director
- Optional provider configuration (OpenClaw, image/video/audio tools)

## Output

- Per-scene media artifacts
- Final merged `.mp4`
- Render metadata (duration, resolution, run ID)

## Responsibilities

1. Render scene anchors (image/video).
2. Generate speech/music/effects when requested.
3. Assemble final video with ffmpeg.
4. Preserve intermediates for resume/retry.

## Operational behavior

- Scene-level retries on transient errors.
- Resume from existing scene outputs.
- Consistent output naming by job ID.

## Notes

The orchestrator should invoke this skill using one spec file as the source of truth.
