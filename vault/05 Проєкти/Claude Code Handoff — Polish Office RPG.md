---
type: implementation-handoff
status: ready-for-review
updated: 2026-10-08
---

# Handoff — Polish Office RPG

Read [[Polish Office RPG — PRD 0.1]] before changing code. This brief is for the coding agent; the product is still early, so preserve distinctions between confirmed requirements and proposed assumptions in the PRD.

## User intent

Build a free-to-play, browser-first 2D RPG that helps Ukrainian-speaking learners practise Polish for work in Poland. The game should feel substantial from its first public version: the user wants several weeks of content and initially mentioned around 100 NPCs, with a much larger world as a later ambition. Do not silently replace that goal with a two-hour demo or a tiny cast. If production estimates make the requested scope unrealistic, show the tradeoff and propose a staged content plan while preserving the product vision.

The user and product assistant will shape the world, scenarios, and requirements. Claude Code is responsible for implementing the game.

## Confirmed requirements

- Cozy, warm, top-down pixel art with an original office, map, cast, and UI. Artur approved a specific generated concept-art board for the office and character look. Treat it as the exact art source for the playable office and sprites; crop/reuse pixels from it rather than redraw or replace them. Do not use the complete concept board as a flat game map.
- The player controls a visible hero/avatar walking through a traversable 2D top-down office. NPCs and office objects appear in the room; interactions require proximity. Room transitions must be visually marked and match the collision map. Show a clear first-time guide, current objective, and next-step prompts; update the objective after dialogue.
- A small Polish creative company; the main character is a new employee.
- Approximately half dialogue and meetings, half office exploration and interactive tasks.
- Workplace humor with an ensemble cast and short post-scene comments to the player. Use broad comedy traits only; do not reproduce characters, scenes, or dialogue from The Office. Do not use Stardew Valley assets.
- RPG progression: start at level 1, earn experience through tasks, and unlock duties, areas, and harder conversations.
- Polish is the default language for all UI, tasks, and dialogue. A button reveals a full Ukrainian translation of the current line.
- Dialogue uses prepared answer choices. They must be visible buttons in the in-game conversation panel; a single mouse click selects a choice, even while the NPC line is still typing. Keyboard shortcuts are optional. No voice input or live AI generation is required for the initial version.
- AI-generated stories and branches are prepared before release and reviewed for natural Polish.
- Add subtle procedural Web Audio effects for footsteps, door crossings, interaction/dialogue, answer selection, XP and quest completion. Unlock AudioContext after the first user gesture; add a visible mute toggle and M shortcut. Keep all sound local, with no paid APIs, external services, or background music.
- Free player access; no paid account or purchased custom domain is required.
- Installable PWA is the leading platform hypothesis. Avoid a required paid runtime service.

## Working assumptions to challenge, not hide

- The new employee is a junior marketing coordinator.
- The client campaign is for opening a neighbourhood cafe.
- The first season spans four in-game work weeks, about 20 episodes of 30–45 minutes each.
- Aim for about 100 NPCs, with roughly 12–15 recurring characters and the rest episodic. Keep names, dialogue, quests, and relationships data-driven so content can grow.
- Roughly three main quests may grant one level; test pacing before locking it.
- Save progress locally first; no account or cross-device sync in the initial release.

## Implementation expectations

1. Start with a short architecture and milestone plan based on the PRD. Keep the game static/client-side unless a concrete feature needs a backend.
2. Build the navigation, dialogue choice flow, Ukrainian full-line hint, office interactions, quest state, XP/levels, local save, and PWA shell as the core loop.
3. Store dialogue, quests, NPC metadata, level requirements, and translations as structured content so writers can expand the campaign without code edits.
4. Use the user-approved concept artwork as the source of the playable location and character sprite crops. Do not redraw or replace the approved look. Do not download or reuse copyrighted game/show sprites, maps, characters, logos, or dialogue.
5. Do not add paid APIs, runtime LLM calls, accounts, or voice features to the first version.
6. Keep the full multi-week campaign and ~100 NPC as the product target. A vertical slice may validate the loop, but it is an implementation phase, not a replacement scope.
7. Document how to run the game locally and what still needs authored content. Do not publish or buy a domain.

## Handoff status

Claude Code is running with Claude Pro sign-in, using Sonnet 5.5 at Artur’s request. The earliest drafts had movement and dialogue UI problems; Artur rejected the early look, then approved the newer rich office scene and current game appearance. A browser playtest confirmed the in-game dialogue panel shows the NPC, Polish line, visible reply buttons, and UA control; one mouse click works during or after the typewriter, advances the dialogue/objective, awards XP once, and UA reveals the full Ukrainian translation. A separate browser playtest confirmed the foyer-to-kitchen route, fridge interaction, and return to foyer without teleportation; the doorway is a reversible overlay aligned to the shared kitchen/foyer wall. Headless Chromium verified local Web Audio triggers for steps, door crossing, dialogue open/type/close, choice, XP and quest updates; mute sets master gain to zero and M restores playback; no console errors were observed. Actual speaker audibility has not been assessed. Do not alter the approved scene art while continuing gameplay work; the small kitchen label could be made more readable because a plant partly overlaps it.
