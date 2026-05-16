# Polymarket

## 🎯 Что такое Polymarket?

[Polymarket](https://polymarket.com) — это децентрализованный рынок предсказаний в сети **Polygon**. Пользователи покупают и продают **shares** (доли) бинарных исходов — `YES` или `NO` — по реальным событиям: выборы, спорт, цены крипты, погода и т. д.

Цены долей котируются в центах (`0¢–100¢`) и отражают рыночную вероятность исхода. Доля `YES` по `23.4¢` означает, что рынок оценивает шанс события в ≈23.4 %. При разрешении выигрышные доли платят `$1` каждая; проигрышные — `$0`.

> [!NOTE]
> Drops Bot **не торгует** за вас. Он только мониторит активность на Polymarket и шлёт её в Telegram — что делать с этой информацией, решаете вы.

## 📊 Что добавляет Drops Bot

Drops Bot доставляет **мгновенные алерты** об активности Polymarket в Polygon — прямо в Telegram. Не нужен аккаунт Polymarket, не подписываются транзакции, средства не задействуются. Бот читает публичные on-chain данные и доставляет их.

> [!NOTE]
> Polymarket Event Tracking запущен **10 марта 2026** и доступен на всех тарифах. Лимиты зависят от вашего плана — см. [Лимиты тарифов](./plan-limits.md).

<!-- screenshot: раздел Polymarket в меню Tracking -->

## 🔍 Два режима трекинга

| Режим | За чем следит | Как настроить |
|---|---|---|
| 🟦 **Event Tracking** | За одним конкретным рынком, независимо от того, кто торгует | Переслать боту `polymarket.com/event/<slug>` или `/polymarket → Add Event/Wallet` |
| 🔁 **Wallet Polymarket Activity** | За сделками одного кошелька на всех рынках Polymarket | Включить Polymarket в `Filters → Events` кошелька ([детали](./wallet-activity.md)) |

Два режима дополняют друг друга — трекьте напрямую несколько горячих рынков, а мониторинг кошельков подтянет остальное.

## 🧭 Anatomy of `/polymarket`

`/polymarket` — главная команда. Введите её, чтобы открыть watchlist. Ответ принимает одну из трёх форм:

| Состояние | Когда появляется | Тело |
|---|---|---|
| **Empty** | Нет трекаемых оддсов | `"You are not tracking any Polymarket events yet"` плюс клавиатура из 4 кнопок: **Add Event/Wallet**, **Polymarket Wallets**, **Trending Events**, **Back**. |
| **Populated** | Есть хотя бы 1 трекаемый оддс | `"Your Polymarket Events Watchlist"` со списком строк `🟦 Will <outcome>? <price>¢`, у каждой инлайн-deep-links 🗑 (удалить) и ✏️ (редактировать). |
| **Upsell** | Достигнут лимит тарифа | Карточка с единственной кнопкой **Build Custom Plan** — см. [Лимиты тарифов](./plan-limits.md). |

Watchlist также можно открыть через `/menu → Tracking → Polymarket Events`, либо добавить событие, переслав в чат бота любую ссылку `polymarket.com/event/<slug>`.

## 🌐 Покрытие сетей

Polymarket Events в Drops Bot работают только в сети **Polygon**.

> [!WARNING]
> **Только Polygon.** Polymarket работает на Polygon PoS, и весь трекинг идёт там. Активность кошельков в Ethereum, Base, Solana или других сетях **не** приведёт к Polymarket-алертам — даже если тот же адрес одновременно торгует на Polymarket.

## 💼 Сценарии использования

* **Трейдеры** — Ловите резкие движения цен на интересующих рынках раньше, чем отреагирует остальной рынок.
* **Аналитики и исследователи** — Соберите вотчлист определяющих исход событий (выборы, спорт, крипто, макро) и следите за ними прямо из Telegram.
* **Наблюдатели за китами** — Помечайте кошельки с крупными позициями на Polymarket и получайте уведомление сразу, как они двигают объём.
* **Админы сообществ и каналов** — Маршрутизируйте Polymarket-алерты в Telegram-группу через [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) и автоматически держите аудиторию в курсе.

## 📖 Глоссарий

Термины, которые используются по всему разделу:

| Термин | Значение |
|---|---|
| **Event** (событие) | Родительский рынок на Polymarket — один вопрос с одной датой разрешения (например, *«2026 FIFA World Cup Winner»*). |
| **Outcome** (исход) | Конкретная возможность внутри события (например, *«France wins YES»*). Мультиисходные события раскладывают вопрос на множество `YES`/`NO` ставок. |
| **Odd** (оддс) | UI-лейбл бота для отслеживаемого исхода. Каждая строка в `/polymarket` — это один оддс. Каждый оддс редактируется/удаляется независимо. |
| **Share** (доля) | Единица позиции на Polymarket. Доля `YES` платит `$1`, если исход разрешается true; иначе `$0`. |
| **Price (¢)** | Цена за долю в центах. Эквивалентна рыночной вероятности — например, `23.4¢` ≈ 23.4 % шанс. |
| **Resolution** (разрешение) | Момент, когда исход события определён и доли выплачиваются. Трекинг автоматически останавливается при разрешении. |
| **Share-swap** | Сделка, когда доли переходят между пользователями напрямую через order book — источник данных для **♻️ Swaps Alert**. |
| **Volume** (объём) | Кумулятивный USD-объём сделок на рынке. Используется алертом **📊 Volume Target**. |

## 🚀 С чего начать

* 👉 [**Быстрый старт**](./quickstart.md) — Запустить трекинг первого события за 60 секунд.
* 🔁 [**Активность кошельков на Polymarket**](./wallet-activity.md) — Следить за кошельками, которые ставят на Polymarket.
* ❓ [**FAQ и Troubleshooting**](./faq-and-troubleshooting.md) — Ответы на частые вопросы.

Полный список страниц — в [индексе раздела](../README.md).

## ❓ FAQ

<details>
<summary>Нужен ли аккаунт Polymarket для использования?</summary>

Нет. Достаточно **публичной ссылки на событие**. Трекинг работает только на чтение и никогда не трогает ваши средства.

</details>

<details>
<summary>Торгует ли бот на Polymarket за меня?</summary>

Нет. Drops Bot работает **только на наблюдение** — показывает активность, чтобы вы могли отреагировать вручную в своём кошельке или прямо на Polymarket.

</details>

<details>
<summary>Есть ли отдельная плата за трекинг Polymarket?</summary>

Нет. Polymarket Events входят в каждый тариф; различается только **лимит на количество оддсов**. См. [Лимиты тарифов](./plan-limits.md).

</details>

<details>
<summary>В чём разница между event, outcome и odd?</summary>

**Event** — родительский рынок («2026 FIFA World Cup Winner»). Каждый **outcome** — это одна возможность (France YES, Spain YES, …). Когда вы трекаете outcome в боте, эта отслеживаемая строка называется **odd** — см. [Глоссарий](#-глоссарий) выше.

</details>

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
