# Non-Human Livestream

AI-powered livestream content workspace for managing characters, generation workflows, automation, and documentation.

## Overview

This repository organizes the assets and processes used to build non-human livestream content. It separates character definitions, media workflows, scripts, and project documentation so each part can evolve independently.

The main workflow guide is [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md), which documents the current AI video generation pipeline.

## Repository Layout

- [Characters/](Characters/) - YAML character profiles and behavior definitions
- [workflow/](workflow/) - Generation workflows, prompts, and execution notes
- [code/](code/) - Scripts, automation, and integration code
- [docs/](docs/) - Process notes, reflections, and technical documentation
- [presentation/](presentation/) - Slides, exports, and presentation materials
- [assets/](assets/) - Images, audio, models, and other generated or source assets
- [tuan-tuan-red-panda.yaml](tuan-tuan-red-panda.yaml) - Project configuration

## Characters

Character definitions live in [Characters/](Characters/):

- [Fennie.yaml](Characters/Fennie.yaml)
- [Johnny.yaml](Characters/Johnny.yaml)
- [Tuan Tuan.yaml](Characters/Tuan%20Tuan.yaml)

## Workflow

Use [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md) as the primary operating guide.

Typical flow:

1. Read the prompt or content request.
2. Convert it into a structured story prompt.
3. Generate image, video, and audio assets.
4. Merge the outputs into a final video.
5. Store outputs under [assets/](assets/) and record notes in [docs/](docs/).

## Quick Start

1. Review [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md).
2. Check [tuan-tuan-red-panda.yaml](tuan-tuan-red-panda.yaml) for project settings.
3. Inspect the character files in [Characters/](Characters/).
4. Put implementation code in [code/](code/) and generated media in [assets/](assets/).

## Recommended Practices

- Keep character logic in YAML rather than embedding it in scripts.
- Store reusable generation steps in [workflow/](workflow/).
- Log progress and decisions in [docs/](docs/).
- Keep media outputs organized by task or date under [assets/](assets/).

## Notes

- API keys and service credentials should be managed through your local environment or config files, not hard-coded.
- Some generation steps depend on external tools such as Higgsfield, Seedance 2.0, ElevenLabs, ffmpeg, or moviepy.

## Next Steps

If you are continuing development, the most useful starting points are [workflow/DAILY_WORKFLOW.md](workflow/DAILY_WORKFLOW.md) and the character files in [Characters/](Characters/).
