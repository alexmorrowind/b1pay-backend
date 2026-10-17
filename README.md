# B1Pay Backend

Django REST API бэкенд для финтех-приложения B1Pay.

## Возможности

- 🔐 Регистрация и авторизация пользователей через MyID
- 💳 Интеграция с Payme (платежи и подписки)
- 🏦 Каталог банков Узбекистана
- 📊 API для инвестиций и стартапов
- 💸 P2P переводы через Octo
- 🔒 JWT аутентификация

## Технологии

- Python 3.11+
- Django 6.0.5
- Django REST Framework
- PostgreSQL / SQLite
- MyID Integration
- Payme Integration

## Установка

### 1. Клонируйте репозиторий
```bash
git clone https://github.com/alexmorrowind/b1pay-backend.git
cd b1pay-backend
```

### 2. Создайте виртуальное окружение
```bash
python -m venv venv
source venv/bin/activate  # для Linux/Mac
# или
venv\Scripts\activate  # для Windows
```

### 3. Установите зависимости
```bash
pip install -r requirements.txt
```

### 4. Настройте переменные окружения
Скопируйте файл `.env.example` в `.env` и заполните необходимые параметры:
```bash
cp .env.example .env
```

### 5. Примените миграции
```bash
python manage.py migrate
```

### 6. Создайте суперпользователя (опционально)
```bash
python manage.py createsuperuser
```

### 7. Запустите сервер
```bash
python manage.py runserver
```

API будет доступно по адресу: `http://127.0.0.1:8000`

## Конфигурация для cPanel

Для деплоя на cPanel используйте файл `.env.cpanel.example` как основу.

### Основные настройки:
- `DJANGO_DEBUG=false`
- `DJANGO_ALLOWED_HOSTS` - добавьте ваш домен
- `DATABASE_URL` - настройте подключение к БД
- Настройте MyID credentials
- Настройте Payme merchant ID и ключи

## API Endpoints

### Аутентификация
- `POST /api/auth/myid/web/start/` - Начать авторизацию через MyID
- `POST /api/auth/myid/mobile/start/` - Начать MyID для мобильного
- `POST /api/auth/myid/mobile/complete/` - Завершить MyID авторизацию
- `POST /api/auth/phone-login/` - Вход по телефону и паролю
- `POST /api/auth/register/` - Регистрация

### Банки
- `GET /api/banks/` - Список банков
- `GET /api/banks/{id}/` - Детали банка

### Платежи
- `POST /api/payme/webhook/` - Webhook для Payme
- `GET /api/integration-status/` - Статус интеграций

## Документация

Дополнительную документацию см. в папке с документами:
- `.env.example` - пример конфигурации
- `.env.cpanel.example` - конфигурация для cPanel

## Лицензия

Proprietary

## Автор

B1Pay Team
