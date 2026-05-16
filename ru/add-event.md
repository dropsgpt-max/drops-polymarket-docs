# Добавить Polymarket Event

## 📋 Содержание

* [Трекинг конкретного события](#-трекинг-конкретного-события)
* [Пошаговый гайд](#-пошаговый-гайд)
* [Массовое добавление](#-массовое-добавление)
* [Какая ссылка считается валидной](#-какая-ссылка-считается-валидной)
* [FAQ](#-faq)
* [Troubleshooting](#-troubleshooting)

## ➕ Трекинг конкретного события

Добавление Polymarket-события говорит боту следить за **одним конкретным рынком** и уведомлять о значимых событиях — сдвигах цен, крупных сделках, всплесках объёма. Это самый прямой способ следить за рынками, которые вам уже интересны.

> [!NOTE]
> **Две эквивалентные точки входа.** Можно либо переслать ссылку на событие в чат бота, либо пройти через `Main Menu → Tracking → Polymarket Events → ➕ Add Event`. В обоих случаях вы окажетесь в одном месте.

## 🪜 Пошаговый гайд

### 1. Выберите рынок

Откройте на Polymarket событие, за которым хотите следить. Подойдёт бинарный рынок, мультиэйт-рынок или производный — главное, чтобы URL указывал на одно событие.

![Страница мультиисходного события Polymarket в браузере](../../../media/screenshots/polymarket/event-page.png)

### 2. Скопируйте ссылку

Скопируйте полный URL из адресной строки. На мобильном работает «Copy Link» из системного share-меню.

### 3. Отправьте ссылку в Drops Bot

Откройте чат с Drops Bot в Telegram и вставьте ссылку. Бот распознаёт домен Polymarket и пришлёт **экран выбора оддсов**:

* Заголовок события в теле сообщения
* Строка `Expires:` — дата разрешения
* Заголовок `Select ✅ Odds to Track:`
* По одной строке на исход в формате `🟦 Will <outcome>? <price>¢`
* Кнопки действий: **Select All Yes**, **Select All No**, **Back**
* Если у события больше 10 исходов — появляется строка пагинации: `⏪ ⬅️ 1 ➡️ ⏩` (по 10 оддсов на страницу)

<!-- screenshot: превью события от бота -->

### 4. Подтвердите

Выберите отдельные исходы тапом по строке либо нажмите **Select All Yes** / **Select All No**, чтобы трекать все исходы сразу. Выбранные оддсы помечаются ✅. **Back** — отменить выбор.

> [!TIP]
> **Трекинг активен.** Алерты начинают приходить сразу, исходя из ваших текущих [настроек](./alerts-and-filters.md). Дефолтные пороги консервативные — при желании можно сделать чувствительнее.

### 5. (Опционально) Настройки по событию

Откройте событие через `Polymarket Events → Edit` и настройте:

* Частоту алертов для этого события
* Минимальное движение цены для price-алерта
* Минимальный размер сделки для whale-алерта
<!-- VERIFY: точные названия настроек по событию -->

Полный справочник параметров — в [Настройке алертов Polymarket](./alerts-and-filters.md).

## 📦 Массовое добавление

<!-- VERIFY: подтвердить, поддерживается ли bulk-add через TXT/CSV для Polymarket events (по аналогии с wallets / coins) -->

Если у вас есть список событий для трекинга, ожидается та же логика bulk-add, что используется для кошельков и монет — вставить несколько ссылок через перевод строки или загрузить TXT-файл с одной ссылкой в строке. Уточните точный формат во flow `➕ Add Event`, прежде чем полагаться на это.

## 🔍 Какая ссылка считается валидной

Бот принимает любой прямой URL **события** на `polymarket.com`. Примеры рабочих ссылок:

```
https://polymarket.com/event/<event-slug>
https://polymarket.com/event/<event-slug>?<query-params>
```

Примеры, которые **не подойдут**:

* Категории и листинги (`polymarket.com/markets`, `polymarket.com/sports`)
* Главная Polymarket
* Сокращённые/share-ссылки, которые не разрешаются в канонический URL события

## ❓ FAQ

<details>
<summary>Что происходит, когда событие разрешается?</summary>

Трекинг автоматически останавливается. Событие остаётся в списке как историческая запись, но больше не считается так же, как активное. <!-- VERIFY: точное поведение после resolve -->

</details>

<details>
<summary>Можно ли отслеживать несколько исходов одного события?</summary>

Да. Экран выбора оддсов позволяет отметить исходы по одному либо нажать **Select All Yes** / **Select All No**, чтобы трекать все сразу. Каждый отслеживаемый **оддс** — отдельная строка в `/polymarket`, его можно редактировать (✏️) или удалять (🗑) независимо.

> Каждый оддс занимает **один слот** вашей квоты Polymarket Events. Событие на 12 исходов через `Select All Yes` использует 12 слотов, а не 1 — см. [Лимиты тарифов](./plan-limits.md).

</details>

<details>
<summary>Стоит ли это газа или какой-то on-chain транзакции?</summary>

Нет. Трекинг — чисто off-chain на стороне бота. Кошелёк не задействован, никаких подписей.

</details>

<details>
<summary>Чем это отличается от Wallet Polymarket Activity?</summary>

**Add Event** наблюдает за одним рынком независимо от того, кто на нём торгует.<br>**[Wallet Activity](./wallet-activity.md)** наблюдает за одним кошельком на всех рынках Polymarket, где он торгует. Это дополняющие друг друга режимы, не альтернативы.

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| "Invalid Polymarket link" | URL ведёт на листинг, а не на конкретное событие | Откройте само событие и скопируйте его URL |
| "Limit reached" | Достигнут тарифный лимит на Polymarket Events | Удалите ненужные или [обновите план](./plan-limits.md) |
| Бот принял ссылку, но пишет "event not found" | Polymarket снял событие с публикации | Выберите другое, активное событие |
| Нет алертов после добавления | Слишком высокие пороги или нет активности на рынке | Снизьте пороги в [Alerts & Filters](./alerts-and-filters.md) |

## 📚 Связанные страницы

* [Быстрый старт](./quickstart.md) — короткая 4-шаговая версия этого гайда
* [Управление событиями](./event-management.md) — просмотр, редактирование, удаление трекаемых оддсов
* [Настройка алертов Polymarket](./alerts-and-filters.md) — настройка порогов per-oddsy
* [Лимиты тарифов](./plan-limits.md) — сколько оддсов поддерживает ваш план

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://etherdrops.gitbook.io/etherdrops-bot/<page-path>.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
