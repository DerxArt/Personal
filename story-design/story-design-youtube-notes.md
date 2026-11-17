# Нотатки: гайди з YouTube про якісні Instagram Stories і статичні сторіс-реклами

Контекст: серія Otake Pro в `/workspace/shared/marketing/otake-pro-stories/` (1080×1920, справжні скріни з otake.io) виглядає дешево. Нижче — прийоми з транскриптів 9 відео, без вигаданих цитат і цифр.

Метод (17.11.2026, Europe/Warsaw): Firecrawl MCP був недоступний (потрібна авторизація). Транскрипти знято через yt-dlp як субтитри, без завантаження відео чи аудіо. Де є офіційні субтитри, це зазначено; решта — автоматичні підписи YouTube (ASR), у них бувають помилки в словах і іменах. Усі URL нижче відкривались з HTTP 200 того ж дня. Не увійшло: [Instagram Story Animation | Figma Tutorial (Eirene KW)](https://www.youtube.com/watch?v=ErLbeHosf9U) — англійських субтитрів немає; [Modern Instagram Stories in After Effects (Motion Street)](https://www.youtube.com/watch?v=ji7RcbuJtdU) — у транскрипті майже лише механіка After Effects (комп 1080×1920, 30 fps, 10 с), мало дизайнерських порад.

Поточні сторіс Otake (коротко, щоб прив’язати прийоми): кадр 1 — великий хук на синьому полі й колаж із трьох телефонних мокапів плюс декоративні фігури внизу; кадр 2 — широкий «десктопний» віджет бронювання; далі оплата й ціна. Типові слабкі місця відносно гайдів: кілька екранів продукту в одному кадрі, порожнеча без ієрархії, UI не як один чіткий кроп, немає нативного соціального доказу й нативних стікерів.

---

## Відео (перевірені посилання)

1. [Instagram Story Ideas for Business: 6 Proven Formats That Drive Revenue](https://www.youtube.com/watch?v=dVPvEka6r84) — HubSpot Marketing ( Bridget Oor у титрах). Опубліковано 10.04.2025, 16:11. Офіційні субтитри (`en-en`).  
   **Головна думка:** шість форматів сторіс (акція, питання, відгуки, закулісся, туторіал продукту, м’яка рекомендація) + технічний «toolkit»: 1080×1920, текст на кожному кадрі, бо дивляться без звуку, нативні стікери.

2. [My 2025 Instagram Stories Strategy: What I Stopped Doing + What's Working Now](https://www.youtube.com/watch?v=YCDTtEAPO4I) — Natasha Pierre / Shine With Natasha. Опубліковано 14.05.2025, 17:02. Автопідписи.  
   **Головна думка:** статичні кадри з дуже коротким текстом, довгий текст розкладати на кілька слайдів, перший кадр лише зацікавлює, CTA й лінк-стікер — наприкінці й можна повторити.

3. [How to Design Social Media Templates in Figma](https://www.youtube.com/watch?v=zkLKzKSJAGg) — Envato. Опубліковано 03.10.2024, 1:26:35. Офіційні субтитри (`en-en`).  
   **Головна думка:** шаблони сторіс 1080×1920 будуються на шкалі кеглів, ієрархії, контрасті й «повітря»; зверху гайд на 250 px, бо Instagram кладе свій UI; серія з кількох кадрів закінчується CTA.

4. [Design Better Social Media Posts (Full Process)](https://www.youtube.com/watch?v=LEEiSUlfgIo) — GraphiqVibe. Опубліковано 02.07.2026, 13:14. Автопідписи.  
   **Головна думка:** повний процес макета: якісний PNG продукту в центрі, типографіка навколо нього, паперові текстури на тлі, щоб кадр не був пласким.

5. [The Only Static Ads Tutorial You'll Ever Need](https://www.youtube.com/watch?v=tNe7Y9YU1y8) — Alessio Cordeddu. Опубліковано 24.05.2026, 22:30. Автопідписи.  
   **Головна думка:** структура hook → body → CTA; завдання хука — зупинити (він говорить про приблизно дві секунди); далі продає тіло й кнопка; нативні формати (скрін, переписка, відгук) часто сильніші за «задизайнений» банер.

6. [I Tested 500 Static Ads, Here’s What Actually Scales in 2026](https://www.youtube.com/watch?v=TouPE2n7mzo) — Fraser Cottrell. Опубліковано 08.02.2026, 11:47. Автопідписи.  
   **Головна думка:** спершу scroll-stop (колір / впізнаваний образ), соціальний доказ зверху (цитата з реального відгуку в форматі коментаря) + продукт; дизайн тримати простим.

7. [How to Make Static Image Ads That Scale in 2026](https://www.youtube.com/watch?v=wYOayIG15Oc) — Blue Sense Digital. Опубліковано 07.07.2026, 54:07. Автопідписи.  
   **Головна думка:** око йде по кадру шляхом 1–2–3–4; ієрархію контролюють розмір, контраст і білий простір (в ASR: «wide space» / «Whiteside space»). Не починати шлях ока з жорсткого «ми продаємо X».

8. [Every Ad Creative Type EXPLAINED](https://www.youtube.com/watch?v=FWWp6NcVo3Q) — Fraser Cottrell. Опубліковано 30.11.2025, 19:13. Автопідписи.  
   **Головна думка:** статична реклама = чіткий текст + чіткий CTA; відгук поверх продукту, бажано зі зірками або логотипом на кшталт Trustpilot.

9. [Improve Your Instagram Design: Critiques, Tips & Advice PT 1](https://www.youtube.com/watch?v=qjZospdjnS0) — The Futur. Опубліковано 28.10.2020, 42:53. Автопідписи. Старіше за інші, але це розбір типографіки й CTA, не тренд-ролик.  
   **Головна думка:** шрифт не повинен заважати читати повідомлення; багато повітря навколо тексту; на фінальному кадрі просити зробити одну дію, не чотири одразу.

---

## Прийоми з транскриптів (із таймкодами)

### 1. HubSpot — формати й toolkit сторіс
Джерело: офіційні субтитри.

- Формат «flash sale / офер»: скрін продукту на чистий канвас (фото камерою + Draw + колір + long-press), короткий текст про пропозицію, потім link sticker з конкретним підписом на кшталт «get yours now» (бл. 01:28–02:50).
- Відгуки: «it doesn't look like a screenshot it looks like content»; «make your testimonials pretty and easy to digest»; можна додати фото клієнта; на кожен відгук — link sticker (06:03–07:57).
- Туторіал продукту: «choose one product and one specific use case don't try to show everything»; «each step should be a new story slide»; link sticker на останньому кадрі (10:23–11:08).
- М’яка рекомендація: «keep it short aim for two to three slides max» (12:09–12:24).
- Toolkit (13:01–13:37): «Always design in 1080 by 1920 pixels that's a 9x6 or vertical ratio» (так в офіційних субтитрах; імовірно мали на увазі 9:16). «most people watch stories on mute so add text overlays to every frame». Нативні інструменти: polls, countdowns, questions, links.
- Якщо сторіс «провалюється»: не обов’язково видаляти; «update the first slide with a new cover image to grab attention» (14:44–14:57).
- «taps forward too many… means your content might be too long or not engaging enough»; для стікерів — тестувати новий текст CTA або позицію стікера (14:27–14:44).

### 2. Natasha Pierre — візуальна стратегія сторіс 2025
Джерело: автоматичні підписи.

- Візуал: «rarely talking head, basically no graphics»; «mainly just like photos with very, very minimal text» (бл. 06:37).
- Текст, якщо його багато, розкладати на кілька слайдів, а не складати абзацами в один кадр (у підсумку з 15:11: «more static story slides with minimal text»).
- Структура серії: на першому слайді зацікавити, «the next slide or two is really just building on that and maybe ending with a call to action» (10:13).
- Питання-стікер — лише з конкретним запитанням; link sticker з оновленим preview-текстом під конкретну дію (приклад із відео: «Get your ticket for the workshop»). Лінк можна ставити кілька разів; вона каже, що часто більше кліків дає друге чи третє поява стікера (08:29–10:13) — це її спостереження, не загальна статистика.
- Соціальний доказ і нагадування — після того, як уже зачепили увагу (12:29).

### 3. Envato — сітка, тип, safe zone для Stories у Figma
Джерело: офіційні субтитри.

- Принципи на старті: white space («the empty space around objects», 04:36–04:39); «Visual hierarchy is very important because it helps guide the user's attention to the right places» (05:04); «proper contrast between the text and the background» (05:44). Наприкінці: «key design principles: consistency, widespread, hierarchy, and accessibility» (01:25:40) — у субтитрах «widespread»; раніше в уроці цей принцип названо white space.
- Шкала кеглів і інтерліньяж: значення зі шкали (наприклад 61 / 49 / 31 / 25 px), line height 120% або 140% (16:50–17:36, 19:55, 28:12–28:21). «you got to make that text readable. Therefore, we're going to use a bigger font size» (18:16–18:19).
- Текст на фото: або колір із достатнім контрастом, або підкладка (rectangle / box), рівні відступи (26:08 у автодорожці уроку; у офіційних — 20:19, 24:21, 25:59).
- Сторіс-шаблон: чотири кадри 1080×1920; останній — call to action (33:45–34:44, 35:26).
- Safe zone: «I've set this guide a little bit lower to 250 pixels because Instagram usually puts stuff up here on stories» (38:18). Заголовок сторіс у прикладі: uppercase, bold, line height 120, великий кегль (37:56–37:59).
- Однакові кольори, типографіка й патерни через усю серію (35:54, 58:08).

### 4. GraphiqVibe — фактура й подача продукту
Джерело: автоматичні підписи.

- Шукати «paper-like textures which can be used in the background» (01:18); пізніше текстуру реально кладе в макет (10:10).
- Продукт: PNG по центру, «bold text behind giving some typography» (03:21); зображення продукту — якісні, «high quality» (07:04); «product images can be in natural color» (02:14).

### 5. Alessio Cordeddu — hook / body / CTA і «нативність»
Джерело: автоматичні підписи.

- «You've got a hook, a body, and a CTA.» «The hook's only job is to stop» увагу; «Those two seconds» — далі «the body and the CTA do the actual selling» (04:21). У тілі — product shot, у CTA — якір ціни й кнопка shop.
- «The best testimonial cards sound like a person texting a friend about their experience» (05:54).
- Нативні кадри працюють, «because the viewer thinks they're looking at regular content, a meme, a magazine feature, a screenshot, not at a paid ad» (15:39). Приклади: скрін переписки, «literally a screenshot of Google reviews, not a designed testimonial card», notes app, «the classic native ad» з «zero design at all» (16:57).
- Before/after, scarcity («strongest form of social proof» у його формулюванні, 19:15) — як концепції, не як цифри для Otake.

### 6. Fraser Cottrell — 500 static ads
Джерело: автоматичні підписи.

- «recognizable scroll stopping colors» (01:53); іноді весь макет диктує один сильний образ / «bold poppy poster style» (03:17).
- «Social proof is at the heart of any good static»; у розборі переможця «right at the top we have the social proof which is a kind of like fake looking comment. We grabbed one of the reviews off their website» + яскраве фото продукту (04:52–05:40). «Fake looking» тут про стилізацію рамки коментаря, сам текст він бере з реального відгуку на сайті.
- Можна додати UGC-фото як ще один шар доказу (08:15).

### 7. Blue Sense Digital — шлях ока
Джерело: автоматичні підписи, бл. 13:20–15:17.

- Коли людина вперше бачить статичний кадр, «your eyes will snap to one part of the image, they will then snap to the second spot, third spot, fourth spot, and there's a path».
- Якщо ієрархію не продумати, кадр одразу читається як низ воронки: приклад з відео — величезний заголовок «protein powder», око першим бачить «I'm getting sold protein powder».
- «you control the visual hierarchy through three elements. Number one is sizing. Number two is contrast and number three is wide space.» Далі пояснює: мозок іде до найбільшого елемента; око — до того, що виділяється контрастом; білий простір відштовхує погляд до важливих елементів.

### 8. Fraser Cottrell — типи креативів
Джерело: автоматичні підписи.

- Визначення: «Static ads are images with clear copy and a clear CTA on them» (00:00).
- Відгуки: «we literally took a quote from their website of one of the reviews and we put it over a product image»; «Pair it with a star rating or a Trust Pilot logo» (03:16). Не вигадувати цитати — брати наявні.

### 9. The Futur — типографіка й один CTA
Джерело: автоматичні підписи. Відео переважно про каруселі Instagram, але правила набору й фінального кадру прямо переносяться на сторіс.

- Дивиться «typesetting no-nos» і зламані «typography rules» (00:42).
- Декоративний шрифт: «just use the same typeface… or something much simpler because we don't want the legibility of the typeface to interfere with our reading of the message itself» (10:57). Пізніше радить підібрати secondary typeface як доповнення до простого гротеску (у прикладі — Futura), «which is really legible» (42:00).
- Багато повітря: «leaving a lot of white space around it actually makes this very pleasing to look at» (32:46); «I like that you're using a lot of white space» (36:43).
- Фінальний CTA: «this is screaming at me… Comment below, get involved, give us some love… save this for later. There's just way too much going on here… ask the audience to do one thing» (13:10–13:41).
- Стрілки й декор краще з текстурою / «drew that by hand», щоб не випадали зі стилю (35:27).
- Не давати одному зображенню диктувати всі рішення макета (21:04).

---

## Топ-8 прийомів саме для сторіс Otake Pro

Коротко, щоб перезібрати поточну серію (не публікувати як є).

1. **Прибрати UI Instagram з важливого тексту.** У Figma-гайді Envato верхній гайд ставлять на 250 px, бо зверху живуть аватар, прогрес і хрестик. Заголовок «Still taking bookings in DMs?», пігулка «Booking on Otake» і фінальний CTA не повинні сідати в цю смугу чи на нижній reply bar.

2. **Одна думка на кадр, текст короткий.** Natasha радить майже мінімальний текст і розкладати думку на 2–3 слайди: хук → розвиток → CTA. HubSpot для туторіалу: один продукт і один сценарій, кожен крок — окремий кадр; для м’якого продажу — максимум два-три слайди. Зараз у першому кадрі хук і одразу три мокапи — це вже два меседжі.

3. **Ієрархія: розмір, контраст, повітря.** Blue Sense: око йде шляхом 1–2–3–4; найбільше, найбільш контрастне і те, що не в «дірці» порожнечі, читається першим. Envato: текст на фото або контрастний, або на підкладці; інтерліньяж 120–140%, кегль зі шкали, не випадковий. У кадрі 1 багато порожнього синього, зате низ забитий колажем — шлях ока розривається.

4. **Хук у першому кадрі, продаж — далі.** Alessio: hook / body / CTA; хук лише зупиняє (він говорить про ~2 секунди), ціна й кнопка — наприкінці. HubSpot: якщо серія не тримає, міняти обкладинку саме першого слайда. Для Otake лишити біль «бронювання в дірект» на кадрі 1, а календар, Stripe і $19 не дублювати на ньому.

5. **Один живий кроп інтерфейсу, не колаж телефонів.** HubSpot збирає продукт як скрін на чистому канвасі, без зайвої рамки. GraphiqVibe — якісний PNG по центру, не дрібна галерея. Кадр 2 зараз більше схожий на широкий десктопний віджет: краще великий мобільний кроп однієї дії (обраний слот, кнопка оплати, галочка), ніж три зменшені екрани.

6. **Текстура й матеріал замість плоского «шаблонного» градієнта.** GraphiqVibe кладе paper-like текстуру на фон; The Futur хоче ручну / зернисту деталь, щоб декор не випадав зі стилю. Легкий grain або папір на синьому полі Otake зніме враження дешевого шаблону краще, ніж нові геометричні фігури.

7. **Соціальний доказ як контент, не як банер.** Fraser: доказ зверху, текст із реального відгуку (у нього — зі сайту), можна в рамці коментаря, плюс зірки або логотип платформи відгуків. HubSpot: відгук має виглядати як контент, його мають встигнути прочитати; Alessio: «як повідомлення другові», не як штучна картка. Брати лише справжні відгуки Otake, нічого не дописувати. Якщо відгуку в цій серії немає — не вигадувати.

8. **CTA через нативний стікер, одна дія.** HubSpot і Natasha: poll / question / link sticker, підпис лінка конкретний, не «learn more». The Futur: на останньому кадрі просити одну дію, не кілька. Для Pro — місце під poll на кадрі 1 (як і закладалось) і один link sticker на фіналі з ясною фразою про тариф, без другої кнопки-картинки в тій же зоні.

Шрифти: The Futur — не більше одного акцидентного та одного читабельного гротеску; декоративний не повинен перебивати повідомлення. Брати фірмові шрифти Otake зі сайту й тримати їх стабільно через усі 4 кадри (Envato: consistency).
