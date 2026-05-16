# Лимиты тарифов Polymarket

## 💳 Сколько событий можно отслеживать

Квота **Polymarket Events** — количество рынков, которые можно отслеживать на event-уровне, — масштабируется вместе с подпиской. Wallet-level Polymarket Activity (см. [Wallet Activity](./wallet-activity.md)) использует отдельную квоту **Wallets** и не подпадает под лимиты ниже.

## 📋 Polymarket Events по тарифам

| Тариф | Polymarket Events |
|---|---|
| **Free / Basic** | 20 |
| **Advanced** | 100 |
| **Pro** | 500 |
| **Wallet Sniper** | 500 |
| **Custom** | Настраивается |

> [!NOTE]
> **Custom-планы** позволяют установить лимит Polymarket Events независимо от остальных квот. Полезно, если вам нужен, например, Free-лимит на кошельки, но Pro-уровень аллокации Polymarket.

<!-- VERIFY: подтвердить точные названия планов. В зеркале значения 20/100/500/500/Configurable; названия реконструированы по контексту. -->

## 📈 Что происходит при достижении лимита

Когда вы упираетесь в лимиты тарифа (кошельки, Polymarket events, монеты, NFT), бот уведомляет и предлагает варианты:

* Удалить старое событие, чтобы освободить слот
* Нажать **Build Custom Plan** на upsell-карточке, которую возвращает бот
* Открыть `/menu` и перейти в раздел Subscription для апгрейда

Существующие события не теряются — просто добавление новых временно блокируется, пока вы не освободите место или не повысите план.

При достижении лимита сам ответ `/polymarket` переключается в **upsell-форму**: вместо watchlist вы увидите карточку с единственной кнопкой **Build Custom Plan**.

## 💳 Путь апгрейда

Самый быстрый путь — кнопка **Build Custom Plan** на upsell-карточке. Она открывает plan-builder, где Polymarket Events, Wallets, Coins и NFT можно настроить независимо друг от друга.

Детальное сравнение тарифов (цена, все квоты, способы оплаты) — в [основной документации Subscription](https://etherdrops.gitbook.io/etherdrops-bot/).

## 🧹 Удаление аккаунта и очистка данных

Удаление аккаунта безвозвратно удаляет ваши **отслеживаемые кошельки и Polymarket Events** вместе со всеми настройками.

> [!WARNING]
> **Очистка Polymarket была исправлена 9 апреля 2026.** Более ранние версии бота оставляли «сиротские» записи Polymarket-событий после удаления аккаунта. Если вы удаляли аккаунт до этой даты и начинаете заново, обратитесь в поддержку — пусть убедятся, что устаревшие записи очищены.

## ❓ FAQ

<details>
<summary>Считаются ли разрешённые события в лимит?</summary>

Разрешённые события перестают генерировать алерты, но могут оставаться в списке как историческая запись. Периодически удаляйте их массово, чтобы освободить слоты. <!-- VERIFY: подтвердить, занимают ли resolved events квоту -->

</details>

<details>
<summary>Считается ли Wallet Polymarket Activity в квоту Polymarket Events?</summary>

Нет. Wallet-level активность учитывается в квоте **Wallets**, а не Polymarket Events. Лимиты независимы.

</details>

<details>
<summary>Можно ли получить больший Polymarket-лимит, не поднимая wallet-лимит?</summary>

Да — переключитесь на **Custom-план**, где каждый квот настраивается отдельно.

</details>

<details>
<summary>Чем Pro отличается от Wallet Sniper для Polymarket?</summary>

Оба тарифа дают одинаковую **500-событийную** аллокацию Polymarket. Различия между ними — в wallet-квотах, фичах алертов и цене, а не в Polymarket. <!-- VERIFY: семантика названий тарифов -->

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| "Limit reached" при добавлении | Достигнут потолок тарифа | Удалите событие или повысьте план |
| Счётчик кажется неправильным | Разрешённые события всё ещё в счёте | Bulk-remove разрешённых событий |
| Апгрейднулись, лимит не изменился | Кэш Telegram | `/menu` для обновления; если всё ещё устарел — перезапустите чат |
| Лимит Custom-плана не применён | Конфигурация плана в процессе | Проверьте `💳 Subscription` на текущие эффективные лимиты |

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
