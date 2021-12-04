# Система опросов пользователей

## Задача: спроектировать и разработать API для системы опросов пользователей.

### Функционал для администратора системы:

- авторизация в системе (регистрация не нужна)
- добавление/изменение/удаление опросов. Атрибуты опроса: название, дата старта, дата окончания, описание. После создания поле "дата старта" у опроса менять нельзя
- добавление/изменение/удаление вопросов в опросе. Атрибуты вопросов: текст вопроса, тип вопроса (ответ текстом, ответ с выбором одного варианта, ответ с выбором нескольких вариантов)

### Функционал для пользователей системы:

- получение списка активных опросов
- прохождение опроса: опросы можно проходить анонимно, в качестве идентификатора пользователя в API передаётся числовой ID, по которому сохраняются ответы пользователя на вопросы; один пользователь может участвовать в любом количестве опросов
- получение пройденных пользователем опросов с детализацией по ответам (что выбрано) по ID уникальному пользователя

### Переменные окружения:
```bash
SECRET_KEY - ключ Django

POSTGRES_DB - Имя БД
POSTGRES_USER - Имя пользователя БД
POSTGRES_PASSWORD - Пароль БД
POSTGRES_HOST - Адрес БД
POSTGRES_PORT - Порт БД
```
## Запуск
```bash
docker-compose up
```

## Администрирование
Интерфейс администрора реализован как по API, так и в стандартной панели администратора Django:

http://localhost:8000/admin

### Создание администратора
```bash
pipenv run python backend/manage.py createsuperuser
```

## Документация
#### После запуска приложения, документация доступна по адресу:

http://localhost:8000/swagger/
