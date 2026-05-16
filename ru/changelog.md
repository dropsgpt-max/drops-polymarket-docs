# Polymarket Changelog

Обратно-хронологический лог изменений в трекинге Polymarket в Drops Bot. Источник — официальное зеркало changelog'а; детали UI, которых нет в публичных анонсах, помечены отдельно.

## 2026-04-09 — Polymarket Events Cleanup Fix

Polymarket-события удаляются при удалении аккаунта.

**Что нового**

* Polymarket-события очищаются после удаления аккаунта
* Старые данные о событиях больше не сохраняются после удаления

**Почему это важно**

* Предотвращает «сиротские» Polymarket-события после удаления аккаунта
* Гарантирует, что данные аккаунта удалены полностью

> [!NOTE]
> В том же релизе вышли **Liquidation Alerts** для кошельков Hyperliquid L1 (не связано с Polymarket, но вышло в тот же день).

## 2026-03-10 — Polymarket Event Tracking *(запуск)*

Трекинг Polymarket-событий и алерты по wallet-активности на Polygon.

**Что нового**

* Трекинг событий Polymarket через event-ссылки
* Polymarket-активность отслеживается для наблюдаемых кошельков
* Опция Polymarket добавлена в настройки кошелька `Filters → Events`
* Real-time алерты по трекаемой Polymarket-активности

**Как это работает**

* Event-ссылка Polymarket пересылается боту, чтобы начать трекинг события
* Опция Polymarket включается в `Filters → Events` настройках кошелька
* Активность кошелька на Polygon мониторится на Polymarket-события

**Почему это важно**

* Мониторинг событий Polymarket через прямой трекинг событий
* Детект Polymarket-активности для отслеживаемых кошельков
* Доставка алертов при появлении трекаемой Polymarket-активности

## 📚 Связанные страницы

* [Обзор](./polymarket.md)
* [Лимиты тарифов](./plan-limits.md)
* [Активность кошельков на Polymarket](./wallet-activity.md)
* [Глобальный changelog Drops Bot](https://etherdrops.gitbook.io/etherdrops-bot/help-center/changelog) — не-Polymarket изменения бота

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
