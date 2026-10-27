---
name: video-editing-hyperframes-kit
description: "HyperFrames student kit installed for video/Reels editing in Claude Code, its location, transcription choice, and active project"
metadata: 
  node_type: memory
  type: project
  originSessionId: aaeeba10-2b2c-40e9-8fb6-a63c77dd2945
  modified: 2026-09-09T08:16:52.122Z
---

Installed the [hyperframes-student-kit](https://github.com/nateherkai/hyperframes-student-kit) into `C:\Users\derda\Instagram\video-editing\` on 2026-09-09 — a Node.js + Claude Code skill kit for editing talking-head recordings into Reels/Shorts with transcript-driven cuts and 406 motion-graphics cards (HyperFrames + GSAP).

**Why:** the user wants to monter (edit) videos for the Instagram account together with Claude Code, using this specific open-source kit, stored as a subfolder of the main Instagram project (`C:\Users\derda\Instagram\video-editing\`) alongside `content-plan/`, `strategy/`, `social/`.

**Setup done:** FFmpeg (via winget, `Gyan.FFmpeg`), Chrome Headless Shell (`npx hyperframes browser ensure`), `npm ci`, all 14 skills mirrored to `.claude/skills/` (`edit-video`, `short-form-edit`, `cut-silences`, `cut-mistakes`, `video-storytelling`, `hyperframes-video-beats`, `style-library`, `hyperframes`, `hyperframes-cli`, `gsap`, `hyperframes-registry`, `make-a-video`, `website-to-hyperframes`, `short-form-video`). Tests pass (11/11), demo render verified end-to-end.

**Transcription choice:** use `OPENAI_API_KEY` (Whisper) instead of the kit's default ElevenLabs — the user has no ElevenLabs subscription but does have one covering Whisper transcription. Key still needs to be filled into `video-editing/.env` (gitignored).

**How to apply:** for any future Instagram video-editing request, work inside `video-editing/`, use the `/edit-video` or `/short-form-edit` skills (or a single-stage skill like `cut-silences`/`style-library`), and default transcription to Whisper, not ElevenLabs, unless the user says otherwise. See [[instagram-artur-realist-brand]] for the broader account context and [[instagram-knowledge-base-structure]] for how this folder relates to the rest of the Instagram project.

**Active first project:** `video-editing/video-projects/reel-intro/` was scaffolded for the "хто я" Day-1 Reel, whose script and detailed edit brief already exist at `social/2026-09-08-reel-intro-script.md` and `social/2026-09-08-reel-intro-edit-brief.md`. Next step is pending: user needs to download the source footage from the Google Drive folder referenced in that brief into `video-editing/video-projects/reel-intro/assets/` before editing can start.
