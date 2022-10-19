# yamdb_final
# Yamdb


YaMDb Собирает отзывы и рецензии пользователей на различные произведения

---

## Список используемых библиотек и фреймворков:
* gunicorn==20.0.4
* psycopg2-binary==2.8.6
* requests==2.26.0
* django==2.2.16
* djangorestframework==3.12.4
* PyJWT==2.1.0
* pytest==6.2.4
* pytest-django==4.4.0
* pytest-pythonpath==0.7.3
* djangorestframework-simplejwt==4.7.2
* django-filter==21.1
* pytz==2020.1
* sqlparse==0.3.1 


## шаблон наполнения env-файла:
```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=имя базы данных
POSTGRES_USER=логин для подключения к базе данных
POSTGRES_PASSWORD=пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
SECRET_KEY=ваш SECRET_KEY из settings.py
```

## Команды для запуска проекта:

0. Добавьте файл .json с данными для БД в папку с файлом manage.py

1. Соберите контейнеры и запустите их
```
docker-compose up -d --build
```
2. Выполните по очереди команды:
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
docker-compose exec web python manage.py loaddata fixtures.json
```

3. Для остановки контейнеров выполние команду:
```
docker-compose stop
```
---
## Разработчик:
- [Александр Шарганов](https://github.com/AlexandrSharganov)


![workflow_status](https://github.com/alexandrsharganov/yamdb_final/actions/workflows/yamdb_workflows/badge.svg)
