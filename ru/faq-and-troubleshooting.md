# Polymarket FAQ и Troubleshooting

Сводный справочник по частым вопросам и заранее известным проблемам. Page-specific FAQ также есть на каждой странице раздела.

## ❓ Часто задаваемые вопросы

### Общее

<details>
<summary>Какие сети поддерживает трекинг Polymarket?</summary>

**Только Polygon.** Сам Polymarket работает на Polygon PoS, поэтому весь event-трекинг и Wallet Polymarket Activity скоупится на Polygon. Активность кошелька в Ethereum, Base, Solana или других сетях — даже того же адреса — не приведёт к Polymarket-алертам.

</details>

<details>
<summary>Нужен ли аккаунт Polymarket или подключение кошелька?</summary>

Нет. Трекинг работает только на чтение. Вы даёте боту публичные URL событий и/или адреса кошельков для наблюдения; ваши средства никогда не задействуются.

</details>

<details>
<summary>Когда запустили Polymarket Event Tracking?</summary>

**10 марта 2026.** Последующие правки (особенно cleanup-fix 9 апреля 2026) подчистили работу с данными при удалении аккаунта.

</details>

<details>
<summary>Есть ли shortcut-команда для Polymarket?</summary>

Да — **`/polymarket`** открывает watchlist напрямую. Ответ может принять одну из трёх форм:

* **Empty state** — `"You are not tracking any Polymarket events yet"` плюс клавиатура из 4 кнопок: **Add Event/Wallet**, **Polymarket Wallets**, **Trending Events**, **Back**.
* **Populated state** — `"Your Polymarket Events Watchlist"` со списком трекаемых оддсов и инлайн-ссылками 🗑 (удалить) и ✏️ (редактировать) в каждой строке.
* **Upsell state** — появляется при достижении лимита плана. Единственная кнопка — **Build Custom Plan**.

События также можно добавить, переслав в чат бота ссылку вида `polymarket.com/event/<slug>`, либо открыть watchlist через `/menu → Tracking → Polymarket Events`.

</details>

### Трекинг и лимиты

<details>
<summary>В чём разница между event tracking и wallet activity tracking?</summary>

**Event tracking** наблюдает за конкретным рынком Polymarket, кто бы на нём ни торговал. Добавляется пересылкой URL Polymarket.<br>
**Wallet activity tracking** наблюдает за одним кошельком на всех рынках Polymarket, где он торгует. Включается через `Wallet → Filters → Events → Polymarket`.

Два режима дополняют друг друга и используют **независимые квоты** — события считаются в Polymarket Events-лимит; wallet-активность — в Wallets-лимит.

</details>

<details>
<summary>Можно ли отслеживать несколько исходов мультиэйт-рынка?</summary>

Да. Мультиэйт-рынок трекается как одно событие, алерт срабатывает при движении любого исхода.

</details>

<details>
<summary>Считаются ли Polymarket-события в wallet-лимит?</summary>

Нет. У событий своя квота **Polymarket Events** (см. [Лимиты тарифов](./plan-limits.md)).

</details>

<details>
<summary>Что происходит, когда рынок разрешается?</summary>

Трекинг автоматически прекращается. Событие остаётся в списке как историческая запись, но больше не генерирует алерты. Периодически чистите разрешённые события через bulk-remove, чтобы освобождать слоты. <!-- VERIFY: подтвердить, занимают ли resolved events квоту -->

</details>

<details>
<summary>Можно ли получать алерты только по крупным позициям?</summary>

Да. Поставьте **высокий whale-порог** (например, $25 000) и отключите price-move-алерты в [Alerts & Filters](./alerts-and-filters.md). Получите только большие сделки.

</details>

### Уведомления

<details>
<summary>Можно ли маршрутизировать Polymarket-алерты в Telegram-группу вместо личного чата?</summary>

Да. Подключите профиль к группе через [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) и настройте этот профиль на Polymarket-события.

</details>

<details>
<summary>Почему алерты приходят во время тихих часов?</summary>

Расписание тишины учитывает часовой пояс аккаунта. Проверьте тайм-зону в `Settings → Notifications`. Per-event mute независим от глобального расписания.

</details>

<details>
<summary>Можно ли отключить Polymarket-алерты, не удаляя события?</summary>

Да. Поставьте глобальную частоту в **Off** либо замьютьте отдельные события. Трекинг сохраняется; только уведомления прекращаются.

</details>

### Аккаунт и данные

<details>
<summary>Что происходит с Polymarket Events при удалении аккаунта?</summary>

Все отслеживаемые Polymarket Events удаляются безвозвратно как часть удаления аккаунта. Этот cleanup был исправлен **9 апреля 2026** — аккаунты, удалённые до этой даты, могли оставить «сиротские» записи событий; обратитесь в поддержку при подозрении.

</details>

<details>
<summary>Хранит ли бот историю моих торгов на Polymarket?</summary>

Бот хранит только **то, что вы попросили отслеживать** (ссылки на события, адреса кошельков) и алерты, которые он отправил. Он не агрегирует и не публикует ваши торговые позиции.

</details>

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| Ссылка на событие не принимается | URL — категория или невалидный формат | Откройте конкретное событие на `polymarket.com` и скопируйте его URL |
| Сообщение "Limit reached" | Достигнут лимит Polymarket Events | Удалите старые или [обновите план](./plan-limits.md) |
| Событие добавлено, но алертов нет | Слишком высокие пороги или рынок неактивен | Снизьте пороги в [Alerts & Filters](./alerts-and-filters.md); проверьте, что у рынка есть недавний объём |
| Wallet-алерты не показывают Polymarket-активность | Тоггл `Filters → Events → Polymarket` ВЫКЛЮЧЕН | Включите в `Wallet → Filters → Events` |
| Polymarket-алерты не на той сети | Сделки идут на Ethereum/другой сети, не на Polygon | Polymarket — только Polygon, это ожидаемое поведение |
| Старые события остались после удаления аккаунта | Аккаунт был удалён до cleanup-fix 9 апреля 2026 | Обратитесь в поддержку для очистки сирот |
| Слишком много алертов | Слишком низкие пороги, рынок очень активен | Поднимите whale и price-move-пороги; переключитесь в Digest |
| Per-event переопределение не применяется | Недавний bulk edit перетёр его | Заново задайте переопределение через панель редактирования |
| Telegram-кэш показывает старый лимит | Устаревшее сообщение | `/menu` для обновления |
| Разрешённые рынки всё ещё в списке | Сохраняются как история | Bulk-remove для освобождения слотов |

## 📚 Связанные страницы

* [Обзор](./polymarket.md)
* [Быстрый старт](./quickstart.md)
* [Добавить Polymarket Event](./add-event.md)
* [Активность кошельков на Polymarket](./wallet-activity.md)
* [Управление событиями](./event-management.md)
* [Настройка алертов](./alerts-and-filters.md)
* [Лимиты тарифов](./plan-limits.md)

## 💬 Остались вопросы

Напишите через Help Center в боте либо посмотрите [основную документацию EtherDrops](https://etherdrops.gitbook.io/etherdrops-bot/) для вопросов не по Polymarket.

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
