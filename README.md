# Yatube API

API для социальной сети Yatube. Позволяет получать, создавать, редактировать и удалять посты, комментарии, а также подписываться на авторов.

## Установка

1. Клонируйте репозиторий:
```bash
git clone git@github.com:gammbol/api-final-yatube-ad.git
```
2. Создайте и активируйте виртуальное окружение:
```bash
python -m venv venv
source venv/bin/activate  # для Linux/Mac
venv\Scripts\activate     # для Windows
```

3. Установите зависимости:
```bash
pip install -r requirements.txt
```

4. Выполните миграции:
```bash
cd yatube_api
python manage.py migrate
```

5. Запустите сервер:
```bash
python manage.py runserver
```

6. Примеры запросов
- Получение списка постов:
```
GET /api/v1/posts/
```

- Создание поста (требуется авторизация):
```
POST /api/v1/posts/
Authorization: Bearer <токен>
Content-Type: application/json

{
  "text": "Новый пост",
  "group": 1
}
```

- Получение токена:
```
POST /api/v1/jwt/create/

{
  "username": "user",
  "password": "pass"
}
```

Полная документация доступна по адресу /redoc/ после запуска сервера.