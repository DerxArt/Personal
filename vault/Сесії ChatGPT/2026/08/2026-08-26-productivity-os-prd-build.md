---
type: chatgpt-session
date: 2026-08-26
areas:
  - проєкти
  - цілі
  - навчання
  - фінанси
  - контент
tags:
  - productivity-os
  - web-app
---

# Створення Productivity OS за PRD

## Мета

Перетворити PRD `Productivity_OS_Claude_Cowork_Live_Artifact_PRD.docx` на робочий вебзастосунок, доступний Артуру за приватним посиланням.

## Результат

- Створено й опубліковано приватний застосунок [Productivity OS](https://artur-productivity-os.derdaartyr.chatgpt.site).
- Реалізовано Today, ранковий check-in, Top 3, XP, Focus Mode, Goals, Backlog, Progress, Finance, Content Studio, AI Coach, Freeze Day і Settings/Rules.
- Стан користувача зберігається в платформній базі даних між сесіями.
- Google Calendar не підключено: інтерфейс показує це чесно й не заявляє про виконані календарні зміни.
- AI Coach у цій версії контекстний і rule-based; повноцінний зовнішній AI та voice потребують окремої інтеграції.

## Підтверджені рішення

- Основна мова — українська.
- Візуальний напрям — світлий пастельно-ретро editorial, без corporate SaaS і punishment economy.
- Продукт створено як самостійний приватний вебзастосунок, а не Claude Cowork Live Artifact.
- Усі задачі та планувальні дані мають надходити з реального Google Calendar; демонстраційні задачі заборонені.
- XP, level, streak, skills, finance, content і вся історія мають стартувати з нуля.

## Корекція після першого перегляду

- Артур відхилив seed-задачі й попередньо заповнений прогрес як неправильні.
- Опубліковано нову версію без тестових даних: level 0, XP 0, streak 0, порожні задачі, фінанси, контент і аналітика.
- Підтверджено, що Calendar-конектор Codex бачить реальні календарі Work, Personal, Rituals і Routines.
- Прямий live sync всередині окремого сайту ще потребує безпечного мосту: Google OAuth або керованої синхронізації через Codex.

## Відкрите питання

- Потрібно визначити спосіб live sync календаря: прямий Google OAuth у сайті чи керований sync через Codex.
- Потрібно визначити довгострокове співвідношення між [[HabitForest]], [[Ninety Days to the Chair]] і [[Productivity OS]]: окремі продукти, модулі чи етапи однієї системи.

## Наступні дії

- Пройти перший check-in і перевірити щоденний цикл на реальному дні.
- За потреби підключити справжній Google Calendar та зовнішню AI/voice-модель.
- Після 7 днів використання переглянути, які модулі справді повертають Артура в систему.

## Пов’язано

- [[Productivity OS]]
- [[Ninety Days to the Chair]]
- [[HabitForest]]
