# Daily Workflow (Creative-Skills Style)

## Overview

This repository follows a composable-skill pattern:

- `script-director` skill writes a structured production plan
- `video-generation` skill renders scenes and assembles the final video
- `discord-workflow` skill coordinates channels and bot-to-bot handoff

Pipeline: Discord Prompt -> Plan -> Scene Assets -> Render -> Assemble -> Discord Delivery

## Runtime roles

### Hosted Bot A (YaraBot / Script Director Bot)

- Reads prompt from Discord
- Plans and scripts scenes against music/emotional timing
- Generates structured plan
- Publishes plan to render queue

### Hosted Bot B (JennyBot / Video Generation Bot)

- Reads plan from render queue
- Generates scene media with tools such as ComfyUI
- Handles music/audio generation (for example via Suno)
- Assembles final video
- Publishes result

## Isolation model

YaraBot and JennyBot do not share filesystem state or in-memory context. They operate in independent workspaces. All handoff data must be explicitly relayed by the orchestrator.

Required relay payload per job:

- `job_id`
- `origin_channel_id`
- `origin_message_id`
- `spec` (embedded or file link)
- `status`
- `artifact_refs` (optional, append-only)

## Command pattern (self-hosted only)

If you run the bots locally, use a consistent command layout similar to creative-skills:

```bash
python3 code/workflow.py plan <spec.yaml>      # validate and print scene breakdown
python3 code/workflow.py render <spec.yaml>    # render all scenes
python3 code/workflow.py scene <N> <spec.yaml> # render one scene
python3 code/workflow.py assemble <spec.yaml>  # final ffmpeg assembly
python3 code/workflow.py all <spec.yaml>       # end-to-end, restart-safe
python3 code/workflow.py status <spec.yaml>    # list generated artifacts
```

## Suggested Discord channels

- `#idea-input`
- `#script-output`
- `#render-queue`
- `#final-videos`

## Spec format

Use a single YAML spec as the source of truth for one video job.

Reference example:

- [skills/discord-workflow/references/example.yaml](../skills/discord-workflow/references/example.yaml)

## Environment

Only required for self-hosted deployments. Copy `.env.example` to `.env` and configure:

- Discord bot tokens
- Discord channel IDs
- OpenClaw endpoint and API key
- Optional media provider keys
- ffmpeg path

## Operational checklist

1. Start YaraBot on Computer A.
2. Start JennyBot on Computer B.
3. Send one test prompt in `#idea-input`.
4. Confirm plan appears in `#script-output` or `#render-queue`.
5. Confirm final `.mp4` appears in `#final-videos`.

## Reliability rules

- Keep intermediate scene outputs so failed jobs can resume.
- Keep each render job idempotent by job ID.
- Retry network failures with bounded backoff.
- Never store secrets in repository files.
