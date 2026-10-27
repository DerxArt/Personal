---
name: reel-template-swap-workflow
description: "Recurring request \"given a reference reel, make an identical one with the same audio/texts but a different stock background\" — pipeline, tooling and lessons from the first run (office POV reel)"
metadata:
  node_type: memory
  type: project
  originSessionId: 916b09d4-e3d7-4930-9572-ca06402ff890
  modified: 2026-09-24T23:01:44.964Z
---

When the user hands over an Instagram reel link as a template ("якщо дають відосок"), the job is to reproduce it 1:1 — same audio, same on-screen texts/timings/colours — and change ONLY the background video, using a real **stock** clip (Pexels etc.), never AI-generated footage.

**First run (2026-09-25):** reference https://www.instagram.com/reel/DdDgbDlyj2v/ (@radha_mogallapalli_, 6.17 s "POV office" meme: yellow serif "This part of my life is called" typed, then red "Ahhhh…" pop-in over a scream sound). Built in `C:\Users\derda\Instagram\video-editing\video-projects\reel-swap-office-pov\` (HyperFrames project, has README.md with the full recipe). Output `renders/office-pov-swap_v1.mp4` + `_muted.mp4`. Background = Pexels #7989854 (Mikhail Nilov). Text boxes matched the reference within 1–2 px at 360×640; audio waveform correlation 1.0000.

**Why:** the user runs this as a repeatable content trick for the account; the value is fidelity to the template (timing, layout), so measure it rather than eyeball it.

**How to apply next time (fast path):**
- Reuse the project: `node swap-bg.mjs <stock mp4/url> --start <s> --out <name> --muted` for a new background on the SAME template. For a NEW reference reel, copy the project and follow the "Новий шаблон" section of its README.
- Get the reel: Apify `apify/instagram-reel-scraper` (direct reel URL) returns `videoUrl` + `audioUrl` (~$0.004/reel, skip the paid add-ons). Instagram's logged-out web player is not enough (blob stream, login wall). Python is NOT installed on this machine — use node/ffmpeg only.
- Eyeballing frames misses text that appears after the first frames: scan the whole clip (10 fps contact sheets) and run `tools/measure-text.mjs` over raw 360×640 frames to get typing/fade/pop timings and ink boxes; detect cuts with ffmpeg `select='gt(scene,0.25)'`.
- The reference had 3 hard cuts (3.23 s, 4.23 s); the swap uses one continuous stock clip. Offer multi-shot if the user wants cut-for-cut fidelity.
- Stock: search Pexels in the built-in browser with `?orientation=portrait`, grab `videos.pexels.com/video-files/<id>/...` preview URLs, build a contact sheet, pick by composition/light behind the text zone (centre of frame). Yellow text over bright monitor glare was unreadable → a very soft dark text-shadow was added.
- Fonts: HyperFrames lint rejects non-listed fonts without `@font-face`; download the TTF locally. Reference serif ≈ Instrument Serif + 1.6 px same-colour stroke (heavier than the regular weight); red text is Arial.
- Audio: baked-in audio would become "original audio" on Instagram; the `_muted` file lets the user attach the same sound in-app for attribution.

Related: [[video-editing-hyperframes-kit]], [[instagram-artur-realist-brand]].
