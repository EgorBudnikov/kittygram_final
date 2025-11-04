#  Kittygram

[![CI/CD Status](https://github.com/Port-tf/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Port-tf/kittygram_final/actions/workflows/main.yml)

##  Описание проекта

Kittygram - это социальная сеть для любителей котиков, где пользователи могут делиться фотографиями своих питомцев, оценивать чужих котиков и создавать сообщества по интересам.

**Основные функции:**  Загрузка и публикация фотографий котиков  Добавление описаний, имен и характеристик котиков  Система лайков и комментариев  Подписки на других пользователей Создание тематических сообществ  Поиск и фильтрация котиков по различным параметрам

##  Стек технологий

**Backend:** Python 3.12, Django, Django REST Framework, PostgreSQL, Gunicorn, JWT  
**Frontend:** React, Redux, Axios, Tailwind CSS  
**Инфраструктура:** Docker, Docker Compose, Nginx, GitHub Actions, Telegram API

##  Развертывание проекта

```bash
git clone https://github.com/Port-tf/kittygram_final.git
cd kittygram_final
#  Создание .env файла
"POSTGRES_DB=kittygram
POSTGRES_USER=your_username
POSTGRES_PASSWORD=your_strong_password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=your_django_secret_key
DEBUG=False
ALLOWED_HOSTS=your_domain.com,localhost,127.0.0.1
DOCKER_USERNAME=your_dockerhub_username
HOST=your_server_ip
USER=your_server_user
SSH_KEY=your_ssh_private_key
SSH_PASSPHRASE=your_ssh_passphrase
TELEGRAM_TO=your_telegram_chat_id
TELEGRAM_TOKEN=your_telegram_bot_token"
docker-compose up -d
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py collectstatic --noinput
docker-compose exec backend python manage.py createsuperuser
```
# Проект будет доступен по адресу: http://localhost:8000

## Тестирование

```
# Тесты бэкенда
cd backend
python manage.py test
flake8 backend/

# Тесты фронтенда
cd frontend
npm test
npm run lint
```
## CI/CD Pipeline

Проект использует GitHub Actions для автоматизации. Тестирование запускается при любом пуше в любую ветку. Сборка и деплой запускаются только при пуше в ветку main. После успешного деплоя отправляется уведомление в Telegram.

## Автор
Port-tf - GitHub: @Port-tf


