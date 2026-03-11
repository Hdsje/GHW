# Hdsje Reusable Workflows

Централизованные CI/CD workflow для всех проектов.

## Использование

```yaml
jobs:
  notify:
    uses: Hdsje/.github/.github/workflows/telegram.yml@main
    secrets: inherit
```

## Доступные workflows

| Workflow | Назначение |
|----------|----------|
| `telegram.yml` | Telegram уведомления |
| `ai-self-heal.yml` | AI само-исправление |
| `auto-merge.yml` | Авто-мерж PR |
| `stale-branches.yml` | Очистка веток |
| `issue-triage.yml` | Авто-лейблы |
| `self-healing.yml` | Мониторинг + восстановление |
| `security-scan.yml` | OWASP ZAP |
| `license-audit.yml` | Аудит лицензий |
| `coverage.yml` | Покрытие тестами |
| `changelog.yml` | Авто-CHANGELOG |

## Секреты

Все секреты передаются из вызывающего репозитория через `secrets: inherit`.
