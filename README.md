# discord-openclaw-robots-workflow

Three composable OpenClaw-style skills that work together so two Discord bots (running on two computers) can turn a text idea into a finished video.

```
Discord idea prompt
    └─ script-director (Bot A)
          └─ structured scene plan (YAML/JSON)
                └─ video-generation (Bot B)
                      ├─ key images
                      ├─ animated clips
                      ├─ voice/music/audio
                      └─ final merge -> output.mp4
                            └─ discord-workflow publishes back to Discord
```

## The three skills

### `skills/script-director/` — story and shot planning

Transforms user input into production-ready instructions:

- story beat
- scene list
- visual style hints
- camera/motion hints
- audio direction

See: [skills/script-director/SKILL.md](skills/script-director/SKILL.md)

### `skills/video-generation/` — media generation and rendering

Consumes structured scene instructions and produces media assets:

- image generation
- video generation
- TTS/audio generation
- final video assembly

See: [skills/video-generation/SKILL.md](skills/video-generation/SKILL.md)

### `skills/discord-workflow/` — Discord orchestration

Coordinates message flow across channels and bots:

- read idea prompts
- dispatch to script-director
- dispatch render jobs to video-generation
- upload final assets and metadata

See: [skills/discord-workflow/SKILL.md](skills/discord-workflow/SKILL.md)

## How they compose

1. Bot A receives idea text in Discord and outputs a structured scene plan.
2. Bot B renders assets and assembles final video from that plan.
3. The orchestrator posts progress and final deliverables in configured Discord channels.

The workflow spec and operating notes are in [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md).

## Install

Clone this repository and configure secrets locally:

```bash
cp .env.example .env
```

Then fill in your Discord and OpenClaw credentials in `.env`.

## Repository layout

- [skills/](skills/) - composable skill modules
- [workflow/](workflow/) - operating guide
- [Characters/](Characters/) - character definitions
- [code/](code/) - implementation scripts
- [assets/](assets/) - generated outputs
- [docs/](docs/) - supporting notes

## Security

- Never commit real tokens or API keys.
- Keep secrets in `.env` only.
- `.env.example` contains the required key names.
