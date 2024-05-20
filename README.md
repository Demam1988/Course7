Курсовая работа.

Уважаемый пользователь!

В 2018 году Джеймс Клир написал книгу «Атомные привычки», которая посвящена приобретению новых полезных привычек и
искоренению старых плохих привычек. В рамках курсовой работы была реализована бэкенд-часть веб-приложения трекера
полезных привычек.

Важно указывать актуальный и правильный chat id при регистрации пользователя. Узнать его можно у
бота https://t.me/getmyid_bot. Если не указать chat_id, то напомнания не будут отправляться.

Установка Клонируйте проект. Активируйте виртуальное окружение командой: poetry shell. Установите зависимости командой:
poetry install.

Создайте Базу данных PostgreSQL, пропишите переменные окружения в файл .env. Используемые в проекте переменные окружения
записаны в файле .env.sample.

Для миграции в базу данных используйте команду: python manage.py migrate

Установите Redis (используется для периодических задач celer).

Команды:

Для создания суперпользователя и пользователей используйте команду: python manage.py create_users

Пароль и логин для суперпользователя:

login: admin@test.com password: 12345

Для всех пользователей (user1@test.com, user2@test.com, staff@test.com) password: 12345.

Для запуска планировщика celery используйте команду: python.exe -m celery -A config beat --loglevel=info. Остановка
планировщика: ctrl + break. Для запуска worker используйте команду: python.exe -m celery -A config worker -l INFO -P
eventlet. Остановка worker: ctrl + break.

Работа с DOCKER: Установите DOCKER и при необходимости плагин Docker Compose Создайте образ командой docker-compose
build Создайте БД командами:

docker-compose exec db psql -U <имя пользователя>
CREATE DATABASE <имя базы данных>;
\q Запустите контейнеры командой docker-compose up Наличие файла .env с переменными окружения обязательно.