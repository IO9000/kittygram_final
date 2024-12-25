# Описание проекта

    Kittygram — это веб-приложение, предназначенное для обмена фотографиями и видео с милыми котиками.
Пользователи могут загружать свои фотографии, оставлять комментарии и ставить лайки.
Проект создан для того, чтобы объединить любителей котиков и предоставить им платформу для общения и обмена контентом.

## Что нужно сделать

    - Регистрация и авторизация пользователей
    - Загрузка и отображение фотографий котиков

## Стек технологий

    - Backend: Python, Django, Django REST Framework
    - Frontend: React
    - База данных: PostgreSQL
    - Контейнеризация: Docker
    - CI/CD: GitHub Actions
    - Тестирование: Pytest

# Развертывание проекта

Клонируйте репозиторий:
    ```
    git clone https://github.com/ваш_логин/kittygram.git
    cd kittygram
    ```

Создайте и активируйте виртуальное окружение:
    ```
    python -m venv venv
    source venv/bin/activate  # для Linux/Mac
    venv\Scripts\activate  # для Windows
    ```
Установите зависимости:
    ```
    pip install -r backend/requirements.txt
    ```
Запустите проект:
    ```
    docker compose -f docker-compose.production.yml up -d
    ```
Установите зависимости:
    ```
    docker compose -f docker-compose.production.yml exec backend python manage.py migrate
    ```

# Заполнение .env

    Создайте и откройте файл .env в текстовом редакторе и добавьте следующие переменные окружения:
    POSTGRES_USER = ...
    POSTGRES_PASSWORD = ...
    POSTGRES_DB = ...

    DB_HOST = ...
    DB_PORT = ...
    SECRET_KEY = ...
    USE_SQLITE = ...
    DEBUG = ...
    ALLOWED_HOSTS = ...

## Автор
Проект разработан IO9000.
![example workflow](https://github.com/IO9000/kittygram_final/actions/workflows/main.yml/badge.svg)