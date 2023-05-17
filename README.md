![yamdb_final event parameter](https://github.com/kubich13/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

# Проект YaMDb

Проект YaMDb собирает отзывы пользователей на различные произведения. Категории произведений: «Книги», «Фильмы», «Музыка». Список категорий можно расширить. Пользователи могут оставлять к произведениями отзывы и давать рейтинг. Произведению может быть присвоен жанр из готового списка. Новые жанры может добавлять только администратор.

## Какие есть роли:

- Неаутентифицированный пользователь - может только читать описание произведений, читать отзывы и комментарии.

- Аутентифицированный пользователь - может все то, что неаутентифицированный пользователь, и вдобавок к этому он может публиковать отзывы, ставить оценку произведению и комментировать чужие отзывы.

- Модератор - может все то, что аутентифицированный пользователь, и также может удалять любые отзывы и комментарии.

- Администратор - полные права на управление контентом проекта, к этому относится: создавание и удаление произведений, категорий и жанров, и назначение роли пользователей. 

- Суперюзер Django — обладет правами администратора.

## Какие есть ресурсы:

- auth - аутентификация
- users - пользователи.
- titles - произведения
- categories - категории (типы) произведений
- genres - жанры произведений.
- reviews - отзывы на произведения.
- comments - комментарии к отзывам. 

## ENDPOINTS:

- http://84.201.132.212/api/v1/
- http://84.201.132.212/admin
- http://84.201.132.212/redoc

### Полная документация API: http://84.201.132.212/redoc/

![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

### 1. Создайте по образцу .env-файл

- DB_ENGINE=<...>
- DB_NAME=<...>
- POSTGRES_USER=<...>
- POSTGRES_PASSWORD=<...>
- DB_HOST=<...>
- DB_PORT=<...>
- SECRET_KEY=<...>

### 2. Соберите контейнер с помощью Docker-compose
docker-compose build

### 3. Запустите контейнер
docker-compose up

### 4. Выполните миграции
docker-compose exec web python manage.py makemigrations  
docker-compose exec web python manage.py migrate 

### 5. Соберите статику
docker-compose exec web python manage.py collectstatic --no-input

### 6. Создайте суперюзера
docker-compose exec web python manage.py createsuperuser

### 7. Заполнить базу данными
docker-compose exec web python manage.py loaddata fixtures.json
