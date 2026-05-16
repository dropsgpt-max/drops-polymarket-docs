# Быстрый старт Polymarket

## ⚡ Запустить трекинг за 60 секунд

Чтобы начать получать Polymarket-алерты, не нужно ничего настраивать. Откройте интересующий рынок, перешлите ссылку боту — и всё готово: следующее движение цены прилетит в Telegram.

{% hint style="info" %}
**Что нужно заранее**
* Активный чат с EtherDrops Bot (`/start` уже отправлен).
* Не достигнут лимит Polymarket Events по вашему тарифу — см. [Лимиты тарифов](./plan-limits.md).
{% endhint %}

## 🚀 Четыре шага

{% stepper %}

{% step %}
### Откройте событие на Polymarket

Перейдите на [polymarket.com](https://polymarket.com), найдите интересующий рынок и откройте его страницу.

![Страница события Polymarket — URL копируем из адресной строки сверху](../../../media/screenshots/polymarket/event-page.png)
{% endstep %}

{% step %}
### Скопируйте ссылку на событие

Скопируйте URL из адресной строки. Бот принимает ссылки вида `https://polymarket.com/event/<slug>` (с query-параметрами или без них).

{% hint style="warning" %}
**Только URL события.** Категории (`polymarket.com/markets`, `/sports` и т.п.) и главная Polymarket не принимаются — убедитесь, что в URL есть `/event/` и slug после него.
{% endhint %}
{% endstep %}

{% step %}
### Перешлите ссылку боту

Вставьте URL в чат с Drops Bot и отправьте. Бот распознает домен Polymarket и попросит подтвердить.

<!-- screenshot: Telegram-чат с вставленным URL Polymarket -->
{% endstep %}

{% step %}
### Подтвердите трекинг

Нажмите **Track Event** в ответе бота. Рынок добавляется в список `🟦 Polymarket Events`, алерты начинают приходить сразу.

{% hint style="success" %}
**Готово!** Вы получите уведомление в Telegram при следующей активности, которая пересечёт ваши пороги.
{% endhint %}
{% endstep %}

{% endstepper %}

## ➡️ Что дальше

Когда первое событие в трекинге, можно:

* 🔔 [Настроить чувствительность алертов](./alerts-and-filters.md) — глобальные пороги и переопределения по событию.
* 🔁 [Отслеживать кошельки, ставящие на Polymarket](./wallet-activity.md) — автоматически ловить китов.
* 🛠️ [Управлять списком событий](./event-management.md) — просмотр, редактирование, удаление.

## 🔧 Troubleshooting

| Проблема | Вероятная причина | Решение |
|---|---|---|
| Бот не распознаёт ссылку | URL ведёт на категорию, а не на конкретное событие | Откройте само событие и скопируйте его URL |
| Сообщение "Limit reached" | Достигнут лимит Polymarket Events по тарифу | Удалите старое событие или [обновите план](./plan-limits.md) |
| Ссылка принята, но алертов нет | Рынок уже разрешён или нет активности | Выберите активный рынок с недавним объёмом |

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
