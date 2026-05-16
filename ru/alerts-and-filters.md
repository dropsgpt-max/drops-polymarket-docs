# Настройка алертов Polymarket

## 🔔 Параметры алертов

Polymarket-алерты настраиваются **на уровне отдельного оддса** — у каждого отслеживаемого исхода своя панель. Отдельного глобального экрана настроек Polymarket нет; при добавлении нового оддса применяются дефолтные значения бота, а вы корректируете их индивидуально через watchlist.

## 📝 Панель настроек оддса

Откройте `/polymarket → нажмите ✏️ рядом с нужным оддсом`. Панель редактирования — одна клавиатура из 7 строк, по кнопке на параметр:

| Кнопка | Что делает | Тип значения |
|---|---|---|
| **🔈 Notifications** | Мастер ON/OFF для оддса. Иконка кодирует состояние: 🔈 = включено, 🔇 = выключено. | Toggle |
| **📉 Price Change** | Срабатывает, когда цена оддса сдвигается на заданный процент. | Процент (например, 5%) |
| **🚨 Price Target** | Срабатывает, когда цена пересекает абсолютное значение. | Центы (например, 50¢) |
| **♻️ Swaps Alert** | Срабатывает на share-swap-сделках на рынке. | Toggle / порог |
| **📊 Volume Target** | Срабатывает, когда совокупный объём пересекает заданный USD-порог. | USD (например, $5 000) |
| **🗑 Delete** | Прекращает трекинг этого оддса. | Действие |
| **↩ Back** | Назад к watchlist. | Действие |

Тап по любой кнопке-порогу открывает value picker; текущее значение видно прямо в подписи кнопки после двоеточия (например, `📉 Price Change: 5%`).

> [!NOTE]
> У каждого оддса **свой независимый набор настроек**. Если трекаете несколько исходов одного события, можно для каждого выставить свои пороги — например, пинговать только на движение цены `France YES`, но смотреть объём по `Spain YES`.

## 🎚️ Маршрутизация Telegram-уведомлений

**Личный чат**

По умолчанию все Polymarket-алерты приходят в ваш приватный чат с Drops Bot — туда же, где остальные уведомления.

**Группа / канал**

Подключите профиль к Telegram-группе или каналу через [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels). Можно маршрутизировать Polymarket-алерты только в эту группу, оставив другие события в личном чате.

**Расписание тишины**

Задайте тихие часы в `Settings → Notifications`, чтобы подавлять все алерты (включая Polymarket) в определённое время. Полезно для сна или фокус-блоков.

## 🧪 Готовые наборы порогов

Три отправные точки для панели оддса. Дальше тюньте под конкретный рынок.

**🪶 Наблюдение / низкий шум**

| Параметр | Значение |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | `10%` |
| 🚨 Price Target | не задавать |
| ♻️ Swaps Alert | OFF |
| 📊 Volume Target | `$10 000` |

Несколько пингов в день на ликвидном рынке — в основном крупные всплески объёма и большие движения цены.

**⚡ Активный трейдер**

| Параметр | Значение |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | `3%` |
| 🚨 Price Target | выставить уровень, который вам важен |
| ♻️ Swaps Alert | ON |
| 📊 Volume Target | `$1 000` |

Частые пинги — для рынков, на которых вы активно играете.

**🐳 Охотник за китами**

| Параметр | Значение |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | OFF (или очень высоко, например `25%`) |
| 🚨 Price Target | не задавать |
| ♻️ Swaps Alert | ON |
| 📊 Volume Target | `$25 000` |

Приходит только крупный объём, независимо от движения цены.

> [!WARNING]
> **Высоколиквидные рынки могут затопить чат на низких порогах.** Крупные выборы могут генерировать десятки срабатываний `Volume Target: $1 000` в час. Начинайте с консервативного набора и ослабляйте постепенно.

## ❓ FAQ

<details>
<summary>Почему нет алертов, хотя рынок двигается?</summary>

Чаще всего движение не пересекло заданный процент **Price Change**, либо сделки не пересекли **Volume Target**. Откройте ✏️ панель оддса и снизьте нужный порог, либо включите **Swaps Alert**, если хотите уведомления на каждую сделку.

</details>

<details>
<summary>Можно ли полностью отключить Polymarket-алерты, не удаляя трекаемые оддсы?</summary>

Да — переведите **🔈 Notifications** в выкл (🔇) на каждом нужном оддсе. Трекинг сохраняется; бот просто перестаёт пинговать по этим оддсам.

</details>

<details>
<summary>Применяются ли тихие часы к Polymarket-алертам?</summary>

Telegram-wide mute schedule в `Settings → Notifications` подавляет все алерты Drops Bot в заданное окно, включая Polymarket.

</details>

<details>
<summary>Сохраняются ли мои пороги, когда я добавляю ещё оддсы к тому же событию?</summary>

Нет — каждый оддс стартует с дефолтных значений бота. Настраивайте индивидуально после добавления.

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| Никаких алертов | На всех оддсах **🔈 Notifications** выключены (🔇) | Включить в ✏️ панели каждого оддса |
| Часть оддсов алертит, часть — нет | Пороги разные — тихим нужны более жёсткие | Снизить **Price Change** / **Volume Target** в ✏️ панели тихого оддса |
| Слишком много алертов | Низкие пороги или включён **Swaps Alert** на активном рынке | Поднять **Price Change** / **Volume Target**, выключить **Swaps Alert** |
| Алерты во время тихих часов | Telegram-side mute не применён / несовпадение часового пояса | Проверить `Settings → Notifications` и таймзону устройства |

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
