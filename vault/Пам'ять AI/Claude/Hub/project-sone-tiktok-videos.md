---
name: project-sone-tiktok-videos
description: "Конвеєр відео для TikTok Sone Music AI: формати, де файли, що вже зроблено і що чекає"
metadata:
  node_type: memory
  type: project
  originSessionId: 0310b1fb-74bb-467a-b11b-3eee613f5a8e
  modified: 2026-10-07T17:47:29.872Z
---

Артур просуває iOS-додаток Sone Music AI (TikTok @sone.music.ai). Робимо відео «текст → пісня». Він генерує пісню в Sone і кидає mp3, я пишу оригінальну лірику, транскрибую, ріжу й збираю відео в HyperFrames (`C:\Users\derda\Instagram\video-editing\video-projects\<slug>\`). Публікація тільки після його «ок». Готові файли в `C:\Users\derda\Hub\projects\sone-gospel-video\`.

**Формати:**
- gospel-chat (v1-v4): iMessage-чат на білому тлі, контакт «Bestie 🤍✨».
- gospel-panic (v1): «Panic texts to my roommate», біла панель, поточна бульбашка різка. Чекає мем-картинок: Артур сам генерує по описах із розмови (кот у дверей, ключі, рушник тощо), вставки «вискоком».
- comments-pt1 (v1, v2): формат @sone.music.ai 7680262676425051424: чорний фон, світлий заголовок, біла картка «Reply to X's comment». v2 динамічна: друк коментаря з клацанням, схема Comment→Sone AI→Song, дроп, субтитри по словах, еквалайзер за реальною гучністю, міні-плеєр. Шаблон: `comments-pt1\build_v2.mjs`.

**Уроки:** статичний кадр нудний, потрібен хук за 1 с + рух кожні 3 с; заголовок не більше 2 рядків; емодзі в HyperFrames рендеряться нормально лише деякі; heredoc у Bash ламається на апострофах, використовувати Write.

**Why:** Артур вчиться робити відео, що залітають, на власному продукті.
**How to apply:** нові відео брати за шаблоном v2, нікого не видавати за реальну людину без позначки, не публікувати без «ок».

Пов'язане: [[project-ai-video-no-excuses]]
