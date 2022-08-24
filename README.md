# Проект: API для Yatube

## Описание:

Проект "API для Yatube" представляет собой интерфейс для обмена данными с сервисом YATUBE.

Он позволяет получать различные наборы данных, хранящихся в базе данных сервиса YATUBE и создавать новые данные внутри сервиса.

## Установка:

Для установки проекта на локальной машине необходимо:

1. Клонировать репозиторий и перейти в него в командной строке:  
`git clone git@github.com:Antony8720/api_final_yatube.git`  
`cd api_final_yatube`

2. Cоздать и активировать виртуальное окружение:  
`python3 -m venv env`  
`source env/bin/activate`

3. Установить зависимости из файла requirements.txt:  
`python3 -m pip install --upgrade pip`  
`pip install -r requirements.txt`

4. Выполнить миграции:  
`python3 manage.py migrate`

5. Запустить проект:  
`python3 manage.py runserver`

## Примеры запросов к API:

#### Получение публикаций:
`GET http://127.0.0.1:8000/api/v1/posts/`

#### Пример ответа:
```
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

#### Создание публикаций:
`POST http://127.0.0.1:8000/api/v1/posts/`
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
#### Пример ответа:
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
#### Полная документация:
Полная документация по API доступна по адресу `http://127.0.0.1:8000/redoc`
после запуска сервера
