# API для проекта Yatube

Этот проект — это RESTful API для социальной сети Yatube, позволяющий пользователям публиковать посты, комментировать их и подписываться на других пользователей. Цель проекта — предоставить функциональность для взаимодействия с контентом через API.

## Описание

Проект включает в себя несколько основных функций:
- **Публикация постов**: Пользователи могут создавать, редактировать и удалять свои посты.
- **Комментарии**: Пользователи могут оставлять комментарии под постами.
- **Подписки**: Возможность подписываться на других пользователей и следить за их постами.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/kaplunovAlexander/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
py -x.y -m venv venv
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

Теперь проект доступен по адресу [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

## Примеры запросов к API

### 1. Получить список всех постов:

Метод: `GET`  
URL: `/api/v1/posts/`  
Ответ: Список всех постов пользователя.

### 2. Создать новый пост:

Метод: `POST`  
URL: `/api/v1/posts/`  
Тело запроса:
{ "text": "Текст поста", "group": 1 }
Ответ:
{ "id": 1, "text": "Текст поста", "pub_date": "20XX-XX-XXTXX:XX:XXZ", "author": "username", "group": 1 }

### 3. Подписаться на пользователя:

Метод: `POST`  
URL: `/api/v1/follow/`  
Тело запроса:
{ "following": "username_to_follow" }
Ответ:
{ "user": "username", "following": "username_to_follow" }
