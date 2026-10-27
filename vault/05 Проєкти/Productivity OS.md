---
type: project-note
project_id: artur-second-brain
status: active
confidence: confirmed
as_of: 2026-08-26
updated: 2026-08-26
review_after: 2026-09-09
source: "[[Сесії ChatGPT/2026/08/2026-08-26-productivity-os-prd-build]]"
tags:
  - project
  - productivity
  - project-management
  - english
  - personal-os
---

# Productivity OS

## Коротко

Productivity OS — приватний персональний вебзастосунок Артура, який перетворює один 90-денний North Star на адаптивні щоденні дії з урахуванням енергії, часу й реального навантаження.

Робоча версія: [artur-productivity-os.derdaartyr.chatgpt.site](https://artur-productivity-os.derdaartyr.chatgpt.site).

## Джерело даних

За явним рішенням Артура від 26 серпня 2026, Google Calendar має бути єдиним джерелом задач і планувального контексту. Застосунок не повинен показувати демонстраційні задачі або заздалегідь вигаданий North Star.

## Реалізовано 26 серпня 2026

- ранковий check-in: сон, енергія, настрій, доступний час;
- Top 3 і визначення успішного дня;
- Goals, milestones, tasks/backlog;
- Focus Mode із таймером і focus telemetry;
- XP, рівні, streak, heatmap і skill activity XP;
- Freeze My Day із лімітом дві заморозки на місяць;
- Finance і Content Studio;
- контекстний AI Coach;
- правила календарних класів `Locked`, `AI-managed`, `Flexible personal`;
- приватне платформне збереження стану.

Після першого перегляду застосунок скинуто до чистого стану:

- level 0;
- XP 0;
- streak 0;
- порожні Top 3, tasks, finance, content і analytics;
- старий демонстраційний seed більше не завантажується навіть із раніше збереженого стану.

## Чесні обмеження поточної версії

- Google Calendar доступний Codex, але окремий сайт ще не має прямого live bridge до цього конектора.
- Для автоматичного refresh при відкритті сайту потрібно реалізувати Google OAuth або керований sync через Codex.
- AI Coach працює на контекстних правилах усередині застосунку; зовнішня генеративна модель і voice не підключені.
- Фонові push-сповіщення не реалізовано.

## Product principle

Система має оптимізувати не кількість задач, а значущий прогрес без вигорання. XP не знімається, невдалий день веде до навчання й перепланування, а не до сорому.

## Відкрите архітектурне питання

Відношення до [[HabitForest]] і [[Ninety Days to the Chair]] поки не визначено. Не слід автоматично вважати Productivity OS заміною будь-якого з цих проєктів без окремого рішення Артура.
