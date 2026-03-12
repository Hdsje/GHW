# GHW — GitHub Workflows

> Централизованные reusable CI/CD workflows для всех проектов.

## Быстрый старт

```yaml
jobs:
  notify:
    uses: Hdsje/GHW/.github/workflows/telegram.yml@main
    secrets: inherit
```

## Доступные workflows

| Workflow | Назначение |
|----------|------------|
| `telegram.yml` | 📬 Telegram-уведомления о событиях |
| `self-healing.yml` | 🔄 Мониторинг + автоматическое восстановление |
| `auto-merge.yml` | 🔀 Авто-мерж PR после прохождения проверок |
| `security-scan.yml` | 🛡️ OWASP ZAP сканирование безопасности |
| `issue-triage.yml` | 🏷️ Авто-лейблы и триаж issues |
| `stale-branches.yml` | 🧹 Очистка устаревших веток |
| `changelog.yml` | 📝 Автогенерация CHANGELOG |
| `coverage.yml` | 📊 Покрытие тестами |
| `license-audit.yml` | ⚖️ Аудит лицензий зависимостей |

## Использование

Вызов из любого репозитория:

```yaml
name: CI

on:
  push:
    branches: [main]

jobs:
  telegram:
    uses: Hdsje/GHW/.github/workflows/telegram.yml@main
    secrets: inherit

  security:
    uses: Hdsje/GHW/.github/workflows/security-scan.yml@main
    secrets: inherit
```

## Секреты

Все секреты передаются из вызывающего репозитория через `secrets: inherit`.

| Секрет | Используется в |
|--------|---------------|
| `TELEGRAM_BOT_TOKEN` | telegram.yml |
| `TELEGRAM_CHAT_ID` | telegram.yml |
| `GH_TOKEN` | auto-merge, stale-branches |
