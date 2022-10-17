# Проект «API для Yatube»

## API для работы с постами, комментариями, подписками проекта социальная сеть Yatube. 

- Получение постов, комментариев, сообществ, подписок.
- Создание, редактирование, удаление постов.
- Создание, редактирование, удаление комментариев.
- Просмотр своих подписок.
- Просмотр информации о сообществе и списка всех сообществ. 
- Получение, обновление, проверка JWT-токенов.

Полные права к постам, комментариям и подпискам доступны только для авторизованных пользователей, редактирование чужого контента запрещено. 
Для анонимных пользователей доступ только на чтение к постам, комментариям и сообществам.

## Установка

- склонируйте репозитарий 
- создайте и активируйте виртуальное окружение
`python3 -m venv venv`
`python3 venv/bin/activate`
- установите все зависимости из файла requirements.txt командой: 
`pip install -r requirements.txt`
- выполните миграции
`python manage.py migrate`
- запустите веб сервер
`python manage.py runserver`

## Примеры запросов

```
GET /api/v1/posts/
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

`POST /api/v1/posts/`
Content type JSON:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Response:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
