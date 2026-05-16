# Быстрый старт Polymarket

## ⚡ Запустить трекинг первого события за 60 секунд

1. Откройте [polymarket.com](https://polymarket.com) и зайдите на страницу события, которое хотите отслеживать.
2. Скопируйте URL из адресной строки — он должен выглядеть как `https://polymarket.com/event/<slug>`.
3. Вставьте URL в чат с Drops Bot и отправьте.
4. На **экране выбора оддсов**, который пришлёт бот, нажмите **Select All Yes** (или выберите исходы вручную), затем **Back**.

> [!TIP]
> **Готово.** Каждый выбранный исход теперь в вашем watchlist как **оддс**. Бот будет пинговать в Telegram при движениях цены и всплесках объёма по дефолтным порогам. Введите `/polymarket` в любой момент, чтобы открыть watchlist.

![Страница события Polymarket — URL копируем из адресной строки сверху](../../../media/screenshots/polymarket/event-page.png)

> [!NOTE]
> **Что нужно заранее**
> * Активный чат с Drops Bot (`/start` уже отправлен).
> * Не достигнут лимит Polymarket Events по вашему тарифу — см. [Лимиты тарифов](./plan-limits.md).

## ➡️ Что дальше

* ➕ [**Добавить Polymarket Event** — полный гайд](./add-event.md), включая экран выбора оддсов, мультиисходные события и пагинацию.
* 🔔 [Настроить пороги алертов](./alerts-and-filters.md) — `Price Change`, `Price Target`, `Swaps Alert`, `Volume Target`.
* 🔁 [Отслеживать кошельки, которые ставят на Polymarket](./wallet-activity.md) — автоматически ловить китов.
* 🛠️ [Управлять watchlist'ом](./event-management.md) — просмотр, редактирование, удаление.

Что-то не работает? См. [сводный FAQ + Troubleshooting](./faq-and-troubleshooting.md).

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
