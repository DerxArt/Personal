---
name: project-mundus-travel-reels
description: "Ціль — 10 рілсів Mundus з фото подорожей (50 фрагментів Wan 2.2 локально), збір у reels_travel, далі завантаження на Google Drive вручну"
metadata:
  node_type: memory
  type: project
  originSessionId: 0310b1fb-74bb-467a-b11b-3eee613f5a8e
  modified: 2026-10-18T22:03:57.660Z
---

**Ціль:** для кожної з 10 локацій (Amalfi, Bali, Cappadocia, Iceland, Kyoto, Lisbon, Marrakech, Norwegian Fjords, Patagonia, Scottish Highlands) зробити рілс з 5 фрагментів по ~4 с, тобто 50 фрагментів. Монах Mundus на фото, без розмови, з текстом на екрані.

**Стан (19 жовтня 2026, 05:30): ЗАВЕРШЕНО.** 50 фрагментів згенеровано, 10 рілсів зібрано у `Hubprojectsmundus
eels_final` (по 19,4 с, 5 фрагментів у кожному). Фрагменти у `reels_travel`. Залишилось: завантажити папку на Google Drive вручну (користувач).
- Черга 1: `E:\ComfyUI\run_travel_batch.sh` → фото _01 всіх локацій, лог `travel_batch.log`.
- Черга 2: `E:\ComfyUI\run_reel_fragments.sh` → фото _02–_05 (40 промптів), чекає `ALL_TRAVEL_DONE`, лог `reel_fragments.log`.
- Автозбір: після `ALL_FRAGMENTS_DONE` запускається `E:\ComfyUI\collect_reels.sh`, який копіює все у `Hub\projects\mundus\reels_travel\<локація>\` і пише `MANIFEST.txt` (OK/TODO).

**Чому не через MCP Google Drive:** інструмент приймає файли як base64 у запиті, для 50 відео це не підходить. Google Drive для комп'ютера не встановлено. Користувач сам завантажує папку `reels_travel` на Drive.

**Як застосувати:** коли користувач питає про відео, перевіряти `reels_travel\MANIFEST.txt` і `E:\ComfyUI\reel_fragments.log`, а не відповідати з пам'яті. Не публікувати без погодження. Промпти без реальних людей, персонаж — AI-монах.

Пов'язано: [[project-ai-video-no-excuses]] (інший формат відео), [[project-sone-tiktok-videos]].

**Звук (19 жовтня, оновлено):** озвучка Kokoro (голос am_michael, безкоштовно, локально, E:\kokoro_venv) на кожен фрагмент + тиха музика Liborio Conti, вирівняно до -16 LUFS. Скрипти: E:\kokoro_out\make_voice.py, E:\ComfyUIssemble_reels.sh. Попередні рілси без голосу не вважати готовими.

**v3 (19–20 жовтня):** рілси перезібрано: стабілізовані фрагменти (reels_stab, vidstab), 4 дефектні фрагменти перегенеровано (amalfi_01, kyoto_04, lisbon_02, lisbon_04), голос Kokoro bm_george 0.75 (3 цитати на рілс, решта не вміщається в повільний темп), субтитри синхронні з голосом, титул локації, фінальна картка Breathe with the old monk / @mundus.monk. Збірка: E:\ComfyUIuild_reels_v2.py. Усі 10 у reels_final, 1080x1920, 18.6 с.
