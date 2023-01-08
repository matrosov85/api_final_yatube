# Проект "API для Yatube"

## Описание

Проект добавляет интерфейс API к проекту Yatube, благодаря чему повявляются следующие возможности:
* Создание/просмотр/редактирование/удаление публикаций
* Создание/просмотр/редактирование/удаление комментариев к публикациям
* Просмотр сообществ
* Создание/просмотр подписок на авторов
* JWT авторизация

## Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:matrosov85/api_final_yatube.git
```
```
cd api_final_yatube
```
Cоздать и активировать виртуальное окружение:
```
python -m venv venv
```
```
source venv/scripts/activate
```
Установить зависимости из файла requirements.txt:
```
python -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Выполнить миграции:
```
python manage.py migrate
```
Запустить проект:
```
python manage.py runserver
```

## Примеры запросов
Подробное описание всех запросов к API http://127.0.0.1:8000/redoc/
* #### Создание публикации
    **Request**
    ```
    POST /api/v1/posts/
    {
        "text": "string",
        "image": "string",
        "group": 0
    }
    ```
    **Response**
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
* #### Получение информации о сообществе
    **Request**
    ```
    GET /api/v1/groups/{id}/
    ```
    **Response**
    ```
    {
        "id": 0,
        "title": "string",
        "slug": "string",
        "description": "string"
    }
    ```
* #### Удаление комментария
    **Request**
    ```
    DELETE /api/v1/posts/{post_id}/comments/{id}/
    ```
