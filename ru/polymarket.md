# Polymarket

## 📊 Мониторинг рынков предсказаний в реальном времени

Drops Bot доставляет **мгновенные алерты** об активности на рынках предсказаний Polymarket в сети **Polygon** — прямо в ваш Telegram. Хотите ли вы отслеживать конкретное событие или наблюдать за кошельками китов, которые ставят на Polymarket, бот держит вас в курсе, не заставляя выходить из чата.

> [!NOTE]
> Polymarket Event Tracking запущен **10 марта 2026** и доступен на всех тарифах. Лимиты зависят от вашего плана — см. [Лимиты тарифов](./plan-limits.md).

<!-- screenshot: раздел Polymarket в меню Tracking -->

## 🔍 Что можно отслеживать

Drops Bot поддерживает **два режима трекинга**, под разные сценарии:

* 🟦 **Polymarket Events** — Отслеживайте конкретный рынок, переслав ссылку на событие. Алерт приходит, когда сдвигаются котировки, открываются/закрываются крупные позиции или растёт объём.
* 🔁 **Wallet Polymarket Activity** — Следите за кошельком, и бот покажет каждую его сделку на Polymarket в Polygon — покупки, продажи, изменения позиций — в реальном времени.

Два режима дополняют друг друга: трекьте напрямую несколько горячих рынков, а мониторинг кошельков подтянет остальное.

## 🌐 Покрытие сетей

Polymarket Events в Drops Bot работают только в сети **Polygon**.

> [!WARNING]
> **Только Polygon.** Polymarket работает на Polygon PoS, и весь трекинг идёт там. Активность кошельков в Ethereum, Base, Solana или других сетях **не** приведёт к Polymarket-алертам — даже если тот же адрес одновременно торгует на Polymarket.

## 💼 Сценарии использования

* **Трейдеры** — Ловите резкие движения цен на интересующих рынках раньше, чем отреагирует остальной рынок.
* **Аналитики и исследователи** — Соберите вотчлист определяющих исход событий (выборы, спорт, крипто, макро) и следите за ними прямо из Telegram.
* **Наблюдатели за китами** — Помечайте кошельки с крупными позициями на Polymarket и получайте уведомление сразу, как они двигают объём.
* **Админы сообществ и каналов** — Маршрутизируйте Polymarket-алерты в Telegram-группу через [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) и автоматически держите аудиторию в курсе.

## 🚀 С чего начать

* 👉 [**Быстрый старт Polymarket**](./quickstart.md) — Запустить трекинг первого события за 60 секунд.
* ➕ [Добавить Polymarket Event](./add-event.md) — Полный гайд по трекингу через ссылку.
* 🔁 [Активность кошельков на Polymarket](./wallet-activity.md) — Включить Polymarket-алерты для отслеживаемых кошельков.
* 🛠️ [Управление событиями](./event-management.md) — Просмотр, редактирование, удаление.
* 🔔 [Настройка алертов Polymarket](./alerts-and-filters.md) — Частота и фильтры уведомлений.
* 💳 [Лимиты тарифов](./plan-limits.md) — Сколько событий поддерживает ваш план.
* ❓ [FAQ и Troubleshooting](./faq-and-troubleshooting.md) — Ответы на частые вопросы.

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

Нет. Polymarket Events входят в каждый тариф; различается только **лимит на количество событий**. См. [Лимиты тарифов](./plan-limits.md).

</details>

<details>
<summary>Где найти Polymarket в меню бота?</summary>

Введите **`/polymarket`**, чтобы открыть watchlist напрямую. Также доступ есть через `/menu → Tracking → Polymarket Events`, либо новое событие можно добавить, переслав в чат бота любую ссылку вида `polymarket.com/event/<slug>`.

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
