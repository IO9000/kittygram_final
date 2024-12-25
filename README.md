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

### Клонируйте репозиторий:
    ```
    git clone https://github.com/ваш_логин/kittygram.git
    cd kittygram
    ```

### Установите зависимости:
    ```
    pip install -r backend/requirements.txt
    ```

### Установите docker:
    Установите Windows Subsystem for Linux по инструкции с официального сайта Microsoft.
    Если ваш компьютер соответствует системным требованиям курса, он подойдёт и для установки WSL2.
    Для работы с докером можно будет использовать любой доступный терминал, на ваш вкус: PowerShell, cmd, Git Bash или же терминал Ubuntu из WSL.
    Мы рекомендуем работать в Git Bash.

# Заполнение .env

    Создайте и откройте файл .env в текстовом редакторе и добавьте следующие переменные окружения:
    POSTGRES_USER = user
    POSTGRES_PASSWORD = yoursecretpassword
    POSTGRES_DB = django

    DB_HOST = db
    DB_PORT = 9999
    SECRET_KEY = 'ваш_секретный_ключ'
    USE_SQLITE = true
    DEBUG = true
    ALLOWED_HOSTS = ['localhost', '<ваш_домен>']

### Запустите проект:

    ```
    docker compose -f docker-compose.production.yml up -d
    ```

### Выполните миграции:
    ```
    docker compose -f docker-compose.production.yml exec backend python manage.py migrate
    ```

### Скопируйте статику:
    ```
    docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
    docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/
    ```


## Автор
Проект разработан IO9000.
![example workflow](https://github.com/IO9000/kittygram_final/actions/workflows/main.yml/badge.svg)