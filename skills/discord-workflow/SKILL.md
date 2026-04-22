# discord-workflow

## Purpose

Orchestrate the two-bot workflow across Discord channels.

Bots:

- YaraBot (`script-director`)
- JennyBot (`video-generation`)

These bots are hosted online and do not require local runtime for standard operation.

## Responsibilities

1. Receive user prompt in `idea-input`.
2. Send prompt to script-director and capture structured plan.
3. Send plan to video-generation render queue.
4. Post progress updates.
5. Publish final video and metadata.

## Recommended channels

- `idea-input`
- `script-output`
- `render-queue`
- `final-videos`

## Message contract

- All bot-to-bot payloads should include:
  - `job_id`
  - `source_message_id`
  - `spec` (or spec file path)
  - `status`
  - `producer_bot` (`yarabot` or `jennybot`)

## Workspace isolation requirement

- Bots do not share files or memory.
- The orchestrator is the source of truth for cross-bot state.
- Every status transition must be posted through relay messages.

## Failure handling

- Retry temporary Discord/API failures.
- Keep one canonical status message per `job_id`.
- Upload final artifact again if initial upload fails.
