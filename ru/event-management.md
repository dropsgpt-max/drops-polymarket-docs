# Управление событиями

## 🛠️ Управление отслеживаемыми событиями

Когда вы добавили несколько Polymarket-событий, нужно одно место, где их можно посмотреть, отредактировать и почистить. Эта страница описывает повседневный flow.

> [!NOTE]
> Управление Polymarket Events построено по той же UX-логике, что и **Coin Management** — список, редактирование одного элемента, массовые операции. Если вы привыкли управлять монетами, это будет ощущаться идентично.

## 👀 Просмотр всех отслеживаемых событий

Введите **`/polymarket`**, чтобы открыть watchlist напрямую. Сообщение озаглавлено **`Your Polymarket Events Watchlist`**. Каждый отслеживаемый оддс — это строка, содержащая:

* Заголовок события и выбранный исход (например, `🟦 Will <outcome>? <price>¢`)
* Инлайн-deep-link 🗑 для удаления одним тапом (за ним стоит `?start=DELpmev_…`)
* Инлайн-deep-link ✏️ для открытия панели редактирования

<!-- screenshot: список Polymarket Events -->

Под сообщением — клавиатура из 4 кнопок: **Add Event/Wallet**, **Polymarket Wallets**, **Trending Events**, **Back**. При большом списке клавиатура автоматически сворачивается.

## ✏️ Редактирование конкретного события

Нажмите ✏️ на строке watchlist. Открывается панель редактирования — клавиатура из 7 строк:

* **🔈 Notifications** — ON/OFF для этого оддса (🔈 on / 🔇 off)
* **📉 Price Change** — порог движения цены в процентах
* **🚨 Price Target** — абсолютный таргет цены (в ¢)
* **♻️ Swaps Alert** — алерты на share-swap-сделки
* **📊 Volume Target** — порог по совокупному объёму
* **🗑 Delete** — прекратить трекинг этого оддса
* **↩ Back** — вернуться к watchlist

Что делает каждый порог — см. [Настройку алертов](./alerts-and-filters.md).

## 📦 Массовое редактирование

Для изменений, применяемых ко всем Polymarket-событиям сразу:

`Polymarket Events → ⚙️ Bulk Edit`

Это применяет одно изменение (например, поднять пороги движения цены до 10 п.п.) ко всему списку за один шаг. Подходит, когда нужно убавить шум глобально без правки каждого события.

> [!WARNING]
> **Bulk edit перезаписывает per-event переопределения.** Если вы тонко настраивали отдельные события, массовое редактирование того же параметра сбросит эти настройки. Подтверждайте дважды, прежде чем применять.

## 🗑️ Удаление события

### Одиночное удаление

В панели редактирования события нажмите **🗑️ Remove**. Подтверждение → **Yes** → событие исчезает из списка.

### Массовое удаление

`Polymarket Events → ⚙️ Bulk → Remove`. Выберите несколько событий или удалите все. Освободившиеся слоты сразу становятся доступными.

> [!WARNING]
> **Разрешённые рынки не удаляются автоматически.** Уже разрешённые рынки остаются в списке как историческая запись. Новые алерты они не генерируют, но могут продолжать занимать слот. Периодически чистите их через bulk-remove. <!-- VERIFY: подтвердить, занимают ли resolved events слот -->

## ⚡ Быстрый доступ

* **`/polymarket`** — открывает watchlist напрямую. Ответ принимает одну из трёх форм:
  * **Empty** — `"You are not tracking any Polymarket events yet"` плюс клавиатура из 4 кнопок.
  * **Populated** — `"Your Polymarket Events Watchlist"` с инлайн-ссылками 🗑 / ✏️ в каждой строке.
  * **Upsell** — появляется при превышении лимита плана, единственная кнопка — **Build Custom Plan**.
* `/menu` → `Tracking` → `Polymarket Events` — то же место, один лишний хоп.
* Пересылка любой ссылки `polymarket.com/event/<slug>` в чат — добавляет новое событие, не выходя из диалога.

## ❓ FAQ

<details>
<summary>Сколько событий можно отредактировать за раз?</summary>

Bulk edit применяет одно изменение ко всему списку Polymarket Events за одну операцию. Отдельного per-batch лимита, не считая общего лимита по тарифу, нет.

</details>

<details>
<summary>Можно ли экспортировать список событий?</summary>

<!-- VERIFY: существует ли экспорт для Polymarket events по аналогии с экспортом кошельков? -->
Экспорт следует той же логике, что и для кошельков и монет, если доступен — проверьте bulk-меню в боте. Если функции нет — она пока не выпущена для Polymarket Events.

</details>

<details>
<summary>Потеряю ли я настройки, если удалю и заново добавлю событие?</summary>

Да. Удаление сбрасывает все per-event переопределения. Повторное добавление стартует с глобальных дефолтов.

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| Кнопка Edit не работает | Устаревшее сообщение Telegram | Откройте событие через список, а не через старое уведомление |
| Массовая операция «зависла» | Большой список, обработка в фоне | Подождите несколько секунд; если нет реакции через 30с — повторите |
| Удалённое событие продолжает алертить | Уведомление было в очереди до удаления | Очистится в течение одного цикла; если нет — обратитесь в Help Center |
| Разрешённые события всё ещё в списке | Они остаются как историческая запись | Bulk-remove для освобождения слотов |

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
