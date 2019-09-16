# Общие заметки для PHP проектов

## Проверка оформления кода

    composer app:cs

## Проверка выполнения авто-тестов

    php artisan migrate:fresh --env=testing
    phpunit --no-coverage --stop-on-failure

- `--no-coverage` отключает сбор статистики покрытия тестов, ускоряет выполнение
- `--stop-on-failure` останавливает выполнение тестов на первой найденной ошибке
