![yamdb_final event parameter](https://github.com/kubich13/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

# Проект YaMDb

Проект YaMDb собирает отзывы пользователей на различные произведения.

## ENDPOINTS:

- http://localhost/api/v1/
- http://localhost/admin
- http://localhost/redoc

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
