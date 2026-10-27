---
type: claude-session
source: "Claude"
date: 2026-09-27
session_id: "13623ce7-2fbe-4ad0-b052-02e5966de031"
project: "Instagram"
cwd: "C:\\Users\\derda\\Instagram"
messages: 4
imported: 2026-10-21
tags:
  - ai-session
  - claude
---

# Hyperframes промпт та RealClone

> Імпортовано з Claude. Лише текст розмови: виклики інструментів, виводи команд і приховані міркування не включено. Секрети замасковано.

## Артур

Дай промпт зі встановленням всіх Hyperframes і так далі для того, щоб інша AIка могла почати теж редагувати відео.

І також дай детальне пояснення RealClone.

## Claude

Швидке уточнення: «RealClone» у моєму записнику не існує — найближче за змістом це скіл **`reel-clone`**, який ми будували 2026-09-25. Нижче — пояснення саме по ньому, і окремо промпт для встановлення HyperFrames-кіта.

## 1. Промпт для іншої AI (встановлення HyperFrames + все, що треба для монтажу)

Розрахований на те, що інша AI (інший інстанс Claude Code, або на іншому пристрої з доступом до цього ж репозиторію `C:\Users\derda\Instagram`) має підняти те саме середовище. Скопіюй і встав їй:

```
Задача: підняти середовище для монтажу відео/Reels в цьому проєкті так само, як воно вже налаштоване в C:\Users\derda\Instagram\video-editing\.

1. Переконайся, що встановлено: Node.js 22+, Git, FFmpeg (з ffprobe), Chrome/Chromium.
   На Windows FFmpeg можна поставити так: winget install Gyan.FFmpeg

2. Якщо папки video-editing/ ще немає в проєкті — склонуй кіт:
   git clone https://github.com/nateherkai/hyperframes-student-kit.git video-editing
   Якщо папка вже є (синхронізована через git/Drive з іншим пристроєм) — просто перейди в неї.

3. У video-editing/:
   npm ci
   npm run setup
   npx hyperframes browser ensure   (ставить headless Chrome для рендеру)
   npm test                          (має пройти 11/11)

4. Транскрипція: НЕ використовуй дефолтний ElevenLabs (немає підписки).
   Використовуй OpenAI Whisper. Постав OPENAI_API_KEY у video-editing/.env
   (скопіюй з .env.example, файл гітігнорений — секрети не комітити).

5. Синхронізуй скіли для Claude Code:
   npm run sync:skills
   Це мірить усі 14 скілів у .claude/skills/ (edit-video, short-form-edit,
   cut-silences, cut-mistakes, video-storytelling, hyperframes-video-beats,
   style-library, hyperframes, hyperframes-cli, gsap, hyperframes-registry,
   make-a-video, website-to-hyperframes, short-form-video).

6. Перевір, що кастомний скіл reel-clone теж на місці:
   C:\Users\derda\Instagram\.claude\skills\reel-clone\
   Це НЕ частина офіційного кіта — він написаний під цей акаунт вручну
   (SKILL.md + scripts/analyze-reference.mjs, measure-text.mjs, fetch-drive.mjs,
   prepare-footage.mjs, build-reel.mjs, verify-render.mjs). Якщо його немає —
   попроси файли з основного репозиторію, не намагайся відтворити з нуля.

7. Перевір демо-рендер:
   npm run demo
   cd video-projects/demo
   npx hyperframes lint
   npx hyperframes preview     (Ctrl+C щоб зупинити)
   npx hyperframes render --quality draft --output renders/demo.mp4

8. Правила роботи (з CLAUDE.md кіта):
   - Кожен відео-проєкт живе у video-editing/video-projects/<slug>/ зі своїми
     сирими файлами, транскриптом, композицією і рендерами разом.
   - HyperFrames-команди запускай з директорії конкретного проєкту.
   - Перед креативною роботою читай MOTION_PHILOSOPHY.md і DESIGN.md проєкту.
   - Ніколи не публікуй / не вивантажуй готове відео без явного дозволу
     користувача.
   - Особисті відзняті матеріали, транскрипти й рендери — гітігноряться,
     не комітити в репозиторій.

Після цього все середовище ідентичне і можна працювати через скіли
/edit-video, /short-form-edit або напряму reel-clone для клонування рілсів.
```

## 2. Що таке `reel-clone` (детально)

Це кастомний скіл (не частина офіційного HyperFrames-кіта), написаний під конкретний запит: *«дай референс-рілс → я знімаю своїми руками → ти монтуєш ідентичний»*.

**Локація:** [reel-clone/](Instagram/.claude/skills/reel-clone) у корені Instagram-проєкту (окремо від `video-editing/`, хоча спирається на HyperFrames-кіт для рендеру).

**Двоетапний процес:**

**Етап 1 — аналіз референсу → список кадрів**
- `analyze-reference.mjs` скачує рілс (через Apify `instagram-reel-scraper`, ~$0.004/рілс — прямий лінк на пост, повертає `videoUrl`+`audioUrl`; логаут-плеєр Instagram не годиться, бо там blob-стрім і login wall).
- Розбиває відео на кадри (10 fps контакт-шіти), знаходить жорсткі різи (ffmpeg `select='gt(scene,0.25)'`).
- `measure-text.mjs` вимірює текстові написи: піксельні бокси, час появи/зникнення, шрифт (кегль, трекінг, товщина обводки) — порівнюючи кандидатів шрифтів пряме на референс-кадр.
- Результат — `SHOT-LIST.md`: чіткий перелік, які кадри тобі треба зняти (тривалість, ракурс, композиція), і `plan.json` зі статусом `awaiting-footage`.

**Етап 2 — твої кадри → готовий рілс**
- Ти скидаєш Google Drive-лінк (папка має бути "Anyone with the link – Viewer", бо `download_file_content` конектора повертає лише base64 — для відео непридатно) або кладеш файл локально (`Downloads/`).
- `fetch-drive.mjs` качає матеріал, `prepare-footage.mjs` готує його (включно з HDR→SDR тон-мапінгом для iPhone HLG-кліпів).
- `build-reel.mjs` монтує — той самий таймінг різів, ті самі текстові написи (шрифт/колір/позиція copy-paste з референсу), той самий аудіотрек референсу (як є, без обробки).
- `verify-render.mjs` перевіряє результат об'єктивно: збіг таймінгу різів, піксельне зіставлення текстових боксів (зазвичай у межах 1-3 px при 360×640), кореляцію аудіохвилі з оригіналом (мета — ~1.0).
- Видається `<slug>_v1.mp4` + `<slug>_v1_muted.mp4` — другий файл без звуку, бо аудіо референсу після рендеру стане "original audio" в Instagram; замучену версію користувач накладає своїм голосом/треком через кнопку "Use audio" в застосунку, щоб не приховувати авторство музики.

**Важливі нюанси, які скіл враховує (з практики 5 виконаних проєктів):**
- Якщо референс — суто анімаційна графіка без знімальних кадрів (напр. екран-рекординг з озвучкою автора), reel-clone не застосовний — скіл зупиняється на етапі 1 і питає, що робити далі.
- Якщо в референсі є чужі мем-кліпи (не сам автор), їх можна лишити як є (`fixed: true` в plan.json, кадр не перезнімається) — переробляється тільки авторський кадр.
- Шрифт завжди виміряний, не вгаданий "на око" — теплі/жовті фони спотворюють колірну маску, тому вимір робиться з допуском кольору й виключенням проблемних ділянок.
- Є "динамічна" версія (`v2`) з biт-синхронізованими нарізками й ефектами (punch/shake/whip), коли базовий монтаж "занадто сухий".

Пов'язана логіка: [reel-template-swap-workflow.md](../../.claude/projects/C--Users-derda-Instagram/memory/reel-template-swap-workflow.md) — окремий, простіший варіант того самого пайплайна, де змінюється тільки фон (стокове відео), а не власні зйомки.

## Артур

Ще дай йому доступ до всіх даних цього проєкту Instagram. Типу напиши, що де знаходиться, додай це теж до промту

## Claude

Ось доповнений промпт — тепер з повною картою даних проєкту, щоб інша AI розуміла не лише як підняти монтажне середовище, а й де взагалі що лежить.

```
Задача: підняти середовище для монтажу відео/Reels + отримати повний контекст
проєкту @artur.realist в C:\Users\derda\Instagram\.

=== ЧАСТИНА A. Карта даних проєкту (де що лежить) ===

Робоча директорія: C:\Users\derda\Instagram (НЕ git-репозиторій, локальна
файлова структура). Акаунт: @artur.realist, Instagram Артура Дерди, ніша
"реалістичний самороз­виток" (дисципліна, біг, звички, гейміфіковано через
власну XP-систему). Позиціонування: "Не ідеальний - але росту".

Папки верхнього рівня:
- strategy/        — позиціонування, tone of voice, аудит стратегії
                      (2026-09-03-audit-original.md, positioning-and-voice.md,
                      tone-of-voice-linkedin.md)
- research/         — дослідження ніші й алгоритму (не прив'язане до акаунта):
                      instagram-algorithm-2026.md, reels-playbook.md,
                      carousels-playbook.md, growth-and-posting-strategy.md,
                      viral-reels-scripts-and-tz-architecture.md (каталог на
                      100 скриптів), ai-content-workflow-claude.md,
                      self-improvement-niche-notes.md
- competitors/      — аналіз референс-акаунтів і мікро-акаунтів:
                      reference-accounts-analysis.md,
                      micro-accounts-candidates.md, tracker.md
- content-plan/     — контент-план і трекер публікацій: performance-tracker.md
- social/           — готові чернетки постів/рілсів/каруселей, формат
                      YYYY-MM-DD-<slug>.md (скіли linkedin-post,
                      instagram-carousel зберігають сюди)
- content/          — довгі блог-пости (скіл blog-post зберігає сюди; папки
                      ще фізично нема, створюється при першому використанні)
- video-editing/    — HyperFrames-кіт для монтажу (див. частину B)
- .claude/skills/   — кастомні скіли проєкту (зараз: reel-clone)

Зовнішні джерела, пов'язані з цим проєктом:
- Notion: Personal Dashboard → 🚀 Projects → Instagram
  (page id 3e058af3-598f-80de-a941-f953ecf8bb48), підсторінка
  "🎬 Референси Reels" (3e558af3-598f-819e-a452-fc68813babaa) з інлайн-базою
  "Таблиця референсів" — рілси-референси з пріоритетом, форматом
  (Візуальний / Мем-монтаж / Розмовний) і нотатками, як адаптувати під Artur.
  Правило Артура: завжди мішати "розмовні" (talking-head) рілси з візуальними
  форматами, ніколи не робити підряд більше двох візуальних.
- Google Drive: користувач кидає лінки на свої відзняті кадри туди; потрібен
  доступ "Anyone with the link – Viewer" (конектор Drive не вміє качати відео
  бінарно, лише читати base64/метадані).

Ключові правила контенту (не порушувати без явного дозволу):
- Реалістичний бюджет часу на зйомку+монтаж: 2-4 год/тиждень → плануй ~3
  рілси/тиждень, не 5+2 як у першому драфті стратегії.
- Тон: без "success theater", без перфекціонізму-гуру; Артур як тестовий
  суб'єкт, що показує процес, а не готовий результат.
- Скрипти для рілсів мають звучати як усне мовлення, не як написаний текст:
  вільні тези, одна сильна фраза, без "нанизаних" one-liner'ів; хук не
  озвучує риторичний прийом і не перелічує пункти вголос — відкривай
  конкретним образом.
- Ніколи не публікуй і не вивантажуй готове відео/пост без явного дозволу
  користувача.

=== ЧАСТИНА B. Встановлення HyperFrames (монтажне середовище) ===

1. Встанови: Node.js 22+, Git, FFmpeg (з ffprobe), Chrome/Chromium.
   Windows: winget install Gyan.FFmpeg

2. Якщо папки video-editing/ ще немає в проєкті — склонуй кіт:
   git clone https://github.com/nateherkai/hyperframes-student-kit.git video-editing
   Якщо папка вже є (синхронізована з іншим пристроєм) — просто перейди в неї.

3. У video-editing/:
   npm ci
   npm run setup
   npx hyperframes browser ensure
   npm test                          (має пройти 11/11)

4. Транскрипція: НЕ використовуй дефолтний ElevenLabs (немає підписки).
   Використовуй OpenAI Whisper. Постав OPENAI_API_KEY у video-editing/.env
   (скопіюй з .env.example; файл гітігнорений — секрети не комітити).

5. Синхронізуй скіли для Claude Code:
   npm run sync:skills
   Мірить усі 14 скілів у .claude/skills/ (edit-video, short-form-edit,
   cut-silences, cut-mistakes, video-storytelling, hyperframes-video-beats,
   style-library, hyperframes, hyperframes-cli, gsap, hyperframes-registry,
   make-a-video, website-to-hyperframes, short-form-video).

6. Перевір, що кастомний скіл reel-clone на місці:
   C:\Users\derda\Instagram\.claude\skills\reel-clone\
   Це написано вручну під цей акаунт (НЕ частина офіційного кіта):
   SKILL.md + scripts/analyze-reference.mjs, measure-text.mjs, fetch-drive.mjs,
   prepare-footage.mjs, build-reel.mjs, verify-render.mjs. Якщо файлів немає —
   попроси їх з основного репозиторію, не відтворюй з нуля.

7. Перевір демо-рендер:
   npm run demo
   cd video-projects/demo
   npx hyperframes lint
   npx hyperframes preview     (Ctrl+C щоб зупинити)
   npx hyperframes render --quality draft --output renders/demo.mp4

8. Всі відео-проєкти (готові й активні) живуть у
   video-editing/video-projects/<slug>/. Особисті проєкти акаунта:
   reel-intro, reel-swap-office-pov, office-pov-clone, study-motivation-clone,
   ai-prompts-meme-clone, relatable-hustle-clone, ai-reply-voice-reel,
   claude-obsidian-clone. Решта (may-shorts-*, aisoc-*, clickup-demo,
   linear-promo-30s, golden-ratio-demo, hyperframes-sizzle, first-agent-promo,
   chatgpt-codes-clone, claude-edit-intro, demo) — навчальні приклади з
   офіційного кіта, не чіпати без потреби.

9. Правила роботи (з CLAUDE.md кіта):
   - HyperFrames-команди запускай з директорії конкретного проєкту.
   - Перед креативною роботою читай MOTION_PHILOSOPHY.md і DESIGN.md проєкту.
   - Особисті відзняті матеріали, транскрипти й рендери гітігноряться —
     не комітити.
   - Ніколи не публікуй готове відео без явного дозволу.

Після виконання A+B у тебе є повний контекст акаунта і робоче середовище,
ідентичне поточному: можна працювати через /edit-video, /short-form-edit
або напряму скіл reel-clone для клонування рілсів під власні зйомки.
```

