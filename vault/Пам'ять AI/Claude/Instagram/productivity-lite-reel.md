---
name: productivity-lite-reel
description: "Reel for the free \"Productivity OS Lite\" (Claude artifact planner): brief, footage location, what was built (2026-10-05)"
metadata:
  node_type: memory
  type: project
  originSessionId: 5e59ea1b-823c-42dd-a365-7dc32e6920fb
  modified: 2026-10-05T11:02:02.203Z
---

Brief (user's own notes, 2026-10-05): one idea "my day has a size set by my energy, not the task list"; show pain (12 tasks / 8 overdue / 4 h sleep), mechanic (tap energy 1-5, day shrinks/expands), relief (missing a day never resets); promote ONLY free Lite, one CTA (link), dry self-ironic tone, no "game-changer"; do not promise that Lite picks tasks or that saving works on free Claude. Reference for style: aliabdaal reel DWO9ZfgAFcv (talking head, pill captions); NOT cloned, because speech is tied to lips.

Footage: IMG_0684-0688.MOV live on his Google Drive (private; he downloaded a ZIP to `Downloads\drive-download-20261005T101957Z-1-001`), Ukrainian voice, phone clips of him + phone-filmed monitor (moire). Whisper multilingual `small` with language `ukrainian` works; the `.en` models do not.

**Done:** `video-editing/video-projects/productivity-lite-reel/`: `build-base.mjs` (phrase cuts snapped to quiet points, HLG tone-map, frame-exact concat, loudnorm), `make-plan.mjs` + `build-reel.mjs` (captions with `*accent*` and `box` pill, whip/punch fx), CUTPLAN.md, PINNED-COMMENT.md. Output `renders/productivity-lite-reel_v1_share.mp4` 57.6 s (94 s of footage cut down). He said "do everything according to what I say in the video", so the spoken CTA "link in the comments" and the on-screen "1 of the last 14 days" were kept (brief said "link in bio" / "11 of 14").

**Why / how to apply:** captions are Whisper-based, so unclear words were guessed: "відмітити" (maybe "відмінити"), "Можете побачити", "позначки", "просте меню". If he corrects any, edit `make-plan.mjs` CH list and rerun `node make-plan.mjs` + build-reel. Related: [[reel-clone-skill]], [[artur-derda-creator-voice]].
