# discord-openclaw-robots-workflow

Three composable OpenClaw-style skills that work together so two Discord bots (hosted online) can turn a text idea into a finished video.

```
Discord idea prompt
    └─ YaraBot / script-director (Bot A)
          └─ structured scene plan (YAML/JSON)
                └─ JennyBot / video-generation (Bot B)
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

1. **YaraBot** receives idea text in Discord and outputs a structured scene plan.
2. **JennyBot** renders assets and assembles final video from that plan.
3. The orchestrator relays progress and final deliverables in configured Discord channels.

## Workspace isolation and relay rule

- YaraBot and JennyBot run in separate workspaces.
- They cannot directly read each other's files or generation progress.
- A relay/orchestrator layer must pass plan content and job status between bots.
- Shared context must be transferred through Discord payloads or structured job specs.

The workflow spec and operating notes are in [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md).

## Deployment

The bots are hosted online and operate entirely within Discord. No local runtime is required for normal use.

If you self-host the bots, configure secrets locally:

```bash
cp .env.example .env
```

Then fill in your Discord and OpenClaw credentials in `.env`.

## Group Members & Contributions

| Member | Role | Responsibility |
|---|---|---|
| Ma Jiayin | Anchor Artist | Generate anchor/character pictures |
| iu Yifei | Script Writer | Generate video scripts and scene plans |
| Meng Yayuan | Audio Producer | Generate audio, voiceovers, and music |
| Chen Yingwen | Video Editor | Generate video clips and final assembly |

## Repository layout

- [skills/](skills/) - composable skill modules
- [workflow/](workflow/) - operating guide
- [Characters/](Characters/) - character definitions
- [code/](code/) - implementation scripts
- [assets/](assets/) - generated outputs
- [docs/](docs/) - supporting notes

## Usage

### Prerequisites

- Python 3.10+
- Discord bot tokens (configured in `.env`)
- OpenClaw API credentials

### Setup

```bash
# Clone the repository
git clone <repo-url>
cd Non-human-Livestream

# Install dependencies
pip install -r requirements.txt

# Configure environment variables
cp .env.example .env
# Then fill in your Discord and OpenClaw credentials in .env
```

### Running the Workflow

1. **Start YaraBot** (script-director) in its workspace:
   ```bash
   python code/yara_bot.py
   ```
2. **Start JennyBot** (video-generation) in its workspace:
   ```bash
   python code/jenny_bot.py
   ```
3. **Start the orchestrator** (discord-workflow):
   ```bash
   python code/orchestrator.py
   ```

The bots will listen for idea prompts in configured Discord channels and process them through the full pipeline automatically.

### Workflow Pipeline

```
User submits idea in Discord
    │
    ▼
YaraBot (script-director)
    - Generates structured scene plan (YAML)
    │
    ▼
JennyBot (video-generation)
    - Generates key images (anchor pictures)
    - Generates script and audio (TTS/voiceover)
    - Generates video clips
    - Assembles final .mp4
    │
    ▼
Discord orchestrator (discord-workflow)
    - Uploads final video and metadata back to Discord
```

### Output

Generated videos and assets are saved to the [assets/](assets/) directory.

## Security

- Never commit real tokens or API keys.
- Keep secrets in `.env` only.
- `.env.example` contains the required key names.
