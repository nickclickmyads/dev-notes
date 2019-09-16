# Docker

## Управление сервисом

Запуск

    sudo service docker start

Остановка

    sudo service docker stop

Включение сервиса при каждом старте системы

    sudo systemctl enable docker.service

## Сборка и запуск контейнеров

Прежде чем собирать контейнер убедитесь, что в репозитории есть файл .env и в нем указан GITHUB_API_TOKEN.
Если его нет, скопируйте его с файла .env.example.
Получить GITHUB_API_TOKEN можно следуя этой инструкции https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line

Сборка и запуск проекта

    docker-compose up --build

Если в репозитории есть файл `docker-compose.ext.yml`, нужно использовать

    docker-compose -f "docker-compose.yml" -f "docker-compose.ext.yml" up --build

## Подключение к запущенному контейнеру

    docker-compose exec {имя-контейнера} {команда}

## Запуск нового экземпляра контейнера

    docker-compose run --rm {имя-контейнера} {команда}

## Импорт базы данных MySQL для контейнера

    docker exec -i {mysql-container} mysql -u{имя-пользователя} -p{пароль} homestead < {путь-к-файлу-дампа}

## Экспорт базы данных MySQL для контейнера

    docker exec -i {mysql-container} mysqldump -u{имя-пользователя} -p{пароль} homestead > {путь-к-файлу-дампа}

## Проверка использования дискового пространства

    docker system df

## Очистка дискового пространства

    docker system prune -a

Некоторые проекты могут занимать большой объем пространства из-за избыточной генерации временных файлов внутри контейнера (xdebug).

Проверить объем занимаемый временными файлами

    du -sh /tmp

Удалить все временные файлы

    rm -r /tmp/*
