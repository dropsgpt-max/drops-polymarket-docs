# Активность кошельков на Polymarket

## 🔁 Отслеживайте сделки наблюдаемых кошельков на Polymarket

Если [Добавить Polymarket Event](./add-event.md) следит за **одним рынком независимо от того, кто на нём торгует**, то Wallet Polymarket Activity делает обратное — следит за **одним кошельком на всех рынках Polymarket, которые он трогает**. Сочетание двух режимов закрывает оба конца потока.

> [!NOTE]
> Wallet Polymarket Activity — это **per-wallet тоггл** внутри уже существующего флоу трекинга кошельков. Не нужно добавлять кошельки отдельно — вы просто включаете Polymarket как тип события на уже отслеживаемых кошельках.

## 🎯 Как это работает

Drops Bot уже мониторит транзакции Polygon по вашим кошелькам. Когда в фильтре кошелька включён тип события **Polymarket**, бот распознаёт Polymarket-транзакции (покупка/продажа долей, изменение позиций) и присылает специальный алерт вместо обычного лога перевода.

Путь меню:

```
Wallet → Filters → Events → Polymarket
```

Это та же логика `Filters → Events`, что используется для ликвидаций, свопов и других типов событий по кошелькам.

## 🪜 Включить Polymarket на отслеживаемом кошельке

### 1. Откройте список кошельков

`Main Menu → Tracking → Wallets`, нажмите на нужный кошелёк (или используйте `/edit`, если предпочитаете команды).

<!-- screenshot: список кошельков -->

### 2. Перейдите в Filters → Events

Нажмите **Filters**, затем **Events**. Появится список типов событий: Transfers, Swaps, NFT Transfers, Approvals, Polymarket и т.д.

### 3. Включите тоггл Polymarket

Переключите **Polymarket** в положение ON.

> [!NOTE]
> **Состояние по умолчанию.** С релиза 9 апреля 2026 тоггл Polymarket по умолчанию **включён** для новых кошельков. <!-- VERIFY: подтвердить default state -->

### 4. Сохраните и выйдите

Подтвердите изменения. Следующая Polymarket-сделка этого кошелька на Polygon прилетит в Telegram.

> [!TIP]
> **Трекинг активен.** Дополнительная настройка не нужна. Кошелёк теперь будет генерировать Polymarket-алерты в дополнение к остальным включённым событиям.

## 📨 Как выглядит алерт

Типичный Polymarket-алерт по кошельку содержит:

* **Кошелёк** — адрес и присвоенный вами лейбл
* **Действие** — Buy / Sell / Изменение позиции
* **Рынок** — название события и исход (например, "Will X happen by Date? — YES")
* **Размер** — количество долей и эквивалент в USD
* **Цена** — цена исполнения за долю
* **Ссылка** — прямой линк на событие Polymarket

<!-- screenshot: Polymarket-алерт по кошельку в Telegram -->

## 🧰 Советы

* **Чётко именуйте кошельки** перед включением — `vitalik.eth`, `whale-1`, `my-cold-wallet`. Алерты читаются гораздо быстрее, когда у каждого кошелька есть имя.
* **Совместите с [Save Previous Filters](https://etherdrops.gitbook.io/etherdrops-bot/)** — новые кошельки автоматически унаследуют ваш Polymarket-тоггл.
* **Маршрутизация в группу** — направляйте Polymarket-алерты в отдельную Telegram-группу через [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels), если хотите отделить этот поток от остальных уведомлений.

## ❓ FAQ

<details>
<summary>Считается ли Wallet Polymarket Activity в лимит Polymarket Events?</summary>

Нет. Лимит Polymarket Events применяется только к **event-level** трекингу (через ссылку). Активность по кошельку использует ваш **Wallets** квот. Оба лимита — см. [Лимиты тарифов](./plan-limits.md).

</details>

<details>
<summary>Можно ли получать только Polymarket-алерты, без других событий по кошельку?</summary>

Да. В `Filters → Events` отключите всё, кроме **Polymarket**. Кошелёк будет пинговать только при Polymarket-транзакциях.

</details>

<details>
<summary>Почему я получаю Polymarket-алерт по кошельку, который не на Polygon?</summary>

Кошелёк сам по себе не привязан к сети — Drops Bot следит за ним на всех поддерживаемых чейнах. Тоггл Polymarket выделяет конкретно Polymarket-транзакции на **Polygon**, независимо от того, что кошелёк делает в других сетях.

</details>

<details>
<summary>Как ведут себя кошельки, добавленные массово?</summary>

Массово добавленные кошельки получают тот же дефолтный набор фильтров, включая Polymarket. Если включена опция **Save Previous Filters**, они наследуют ваш последний использованный пресет.

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| Алерты по кошельку идут, но Polymarket-«варианта» нет | Тоггл `Filters → Events → Polymarket` ВЫКЛЮЧЕН | Включите |
| Polymarket-алерты приходят, но без деталей рынка | Проблема рендеринга / кэш | Заново зайдите в edit-вид кошелька и сохраните; если повторяется — обратитесь в Help Center |
| Слишком много шума с одного кошелька | Кошелёк очень активен на многих рынках | Тонко настройте per-wallet пороги в `Filters → Events` <!-- VERIFY: гранулярные пороги per event type --> |
| Polymarket-сделки в Ethereum mainnet не репортятся | Polymarket — Polygon-only; mainnet-сделки это не Polymarket | Решение не нужно — это ожидаемое поведение |

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
