---
name: instagram-notion-reels-references
description: "Notion reference-Reels table under the Instagram project (where it lives, columns, first 8 refs) and Artur's rule to always mix talking-head Reels with visual/reference-format ones"
metadata:
  node_type: memory
  type: project
  originSessionId: 4b85ca48-fdff-4c19-9f0d-50d7c6f5a1c8
  modified: 2026-09-24T23:11:22.135Z
---

On 2026-09-25 Artur sent 8 Instagram Reels as formats worth reproducing and asked for them in Notion under the **Instagram** project (Personal Dashboard / 🚀 Projects / Instagram, page id `3e058af3-598f-80de-a941-f953ecf8bb48`). Built: sub-page **🎬 Референси Reels** (`3e558af3-598f-819e-a452-fc68813babaa`) holding an inline database **Таблиця референсів** (data source `79ec3619-226d-4f1d-a913-4a45346a74d4`). Columns: Референс, Посилання, Автор, Опис, Формат (Візуальний / Мем-монтаж / Розмовний), Складність, Релевантність, Пріоритет (1 · Зараз / 2 · Далі / 3 · Потім), Чому такий пріоритет, Як адаптувати для Artur, Перегляди, Лайки, Секунд, Статус.

First-pass priorities: 1 = overthynker "Imagine how proud you'll feel" (one static desk shot + text) and lifeatzooplus AI-prompts bubbles; 2 = "how are you managing it all" meme cut, "Don't stop" B-roll montage, office-POV (template already built, see [[reel-template-swap-workflow]]); 3 = "I always win" (tone = success theater, only with inversion), "Bad news for Claude… I woke up", Beat It lyric montage (too many locations).

**Rule from Artur (explicit, "дуже важливо"):** mix talking-head/spoken Reels with these visual reference formats — never only the latter. All 8 first references are visual; there are zero talking-format references yet, so he was asked to send 3–5 to add with Формат = «Розмовний».

**Why:** visual formats give reach but don't build trust; talking videos build trust/follows. Fits the 2–4 h/week budget in [[instagram-artur-realist-brand]] (~3 Reels/week: 1–2 talking + 1–2 visual, max two visual in a row).

**How to apply:** when planning a content week or adding references, keep the mix visible (Формат column) and flag if the plan drifts to all-visual. Adapt hooks in Ukrainian and in the self-ironic, non-flexing tone from [[artur-derda-creator-voice]] / [[reel-hook-pacing-trendy]].

**Gotchas:** Artur said he had already created his own page inside Instagram for this table, but Notion search/fetch could not see it (only "Ідеї Reels на вибір" and "Англійська під тебе" were children), so I created my own — he may have a duplicate to delete. Notion workspace has no AI search (plan), use `notion-search`. Apify `apify/instagram-reel-scraper` with several direct URLs reports 1 item right after the run but the dataset ends up with all of them; signed video URLs must be copied character-exact or the download returns a 22-byte error.
