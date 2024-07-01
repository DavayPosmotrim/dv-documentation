# Api

## Models
## User

```json
{
  "name": "userName",
  "device_id": "Qr2da&y38dba7"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>name</td><td>Ник пользователя</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства</td><td>String</td>
</tr>
</table>

## Genre

```json
{
  "name": "Комедия"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>name</td><td>Жанр фильма</td><td>String</td>
</tr>
</table>

## Collection
```json
{
  "slug": "dune_2_arrakis",
  "name": "Новинки 2023 года",
  "cover": "https://images.unsplash.com/photo-1719811838849-bf1cb4426c69?q=80&w=3087&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>slug</td><td>Slug идентификатор подборки</td><td>String</td>
</tr>
<tr>
<td>name</td><td>Имя подборки</td><td>String</td>
</tr>
<tr>
<td>cover</td><td>Ссылка на постер подборки</td><td>String</td>
</tr>
</table>

## Movie
```json
{
  "id": 999,
  "name": "Дюна",
  "poster": "http://www.img.ru/img.jpg"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Уникальный идентификатор фильма</td><td>Integer</td>
</tr>
<tr>
<td>name</td><td>Название фильма</td><td>String</td>
</tr>
<tr>
<td>poster</td><td>Ссылка на постер фильма</td><td>String</td>
</tr>
</table>

## MovieDetails
```json
{
  "id": 999,
  "name": "Дюна",
  "description": "Наследник знаменитого дома Атрейдесов...",
  "year": 2021,
  "countries": [
    "Канада",
    "Венгрия"
  ],
  "poster": "http://www.img.ru/img.jpg",
  "alternative_name": "Dune",
  "rating_kp": 8.5,
  "rating_imdb": 6.1,
  "votes_kp": 1000,
  "votes_imdb": 500,
  "movie_length": 155,
  "genres": [
    {
      "name": "Фантастика"
    },
    {
      "name": "Боевик"
    }
  ],
  "directors": [
    "Дени Вильнев"
  ],
  "actors": [
    "Тимоти Шаламе",
    "Оскар Айзек"
  ]
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Уникальный идентификатор фильма</td><td>Integer</td>
</tr>
<tr>
<td>name</td><td>Название фильма</td><td>String</td>
</tr>
<tr>
<td>description</td><td>Описание фильма</td><td>String</td>
</tr>
<tr>
<td>year</td><td>Дата выхода</td><td>Integer</td>
</tr>
<tr>
<td>countries</td><td>Массив стран фильма</td><td>[String]</td>
</tr>
<tr>
<td>poster</td><td>Ссылка на постер фильма</td><td>String</td>
</tr>
<tr>
<td>alternative_name</td><td>Название фильма на другом языке</td><td>String? (Может быть null)</td>
</tr>
<tr>
<td>rating_kp</td><td>Оценка на Кинопоиске</td><td>Float</td>
</tr>
<tr>
<td>rating_imdb</td><td>Оценка на Imdb</td><td>Float</td>
</tr>
<tr>
<td>votes_kp</td><td>Количество оценок на Кинопоиске</td><td>Integer</td>
</tr>
<tr>
<td>votes_imdb</td><td>Количество оценок на Imdb</td><td>Integer</td>
</tr>
<tr>
<td>movie_length</td><td>Продолжительность фильма в минутах</td><td>Integer</td>
</tr>
<tr>
<td>genres</td><td>Массив жанров фильма</td><td>[Genre]</td>
</tr>
<tr>
<td>directors</td><td>Массив режиссеров</td><td>[String]</td>
</tr>
<tr>
<td>actors</td><td>Массив актеров</td><td>[String]</td>
</tr>
</table>

## Session

```json
{
  "id": "Q2Nurf9o",
  "users": [
    {
      "device_id": "string",
      "name": "string"
    }
  ],
  "matched_movies": 5,
  "date": "2024-06-22",
  "status": "waiting",
  "session_img": "poster url"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>users</td><td>Массив пользователей сессии</td><td>[User]</td>
</tr>
<tr>
<td>matched_movies</td><td>Число совпавших фильмов</td><td>Integer</td>
</tr>
<tr>
<td>date</td><td>Дата создания сессии</td><td>String</td>
</tr>
<tr>
<td>status</td><td>Статус сессии</td><td>SessionStatus</td>
</tr>
<tr>
<td>session_img</td><td>Ссылка на постер из любого фильма сессии (в приоритете постеры из фильмов по которым были совпадния с наибвысшей оценкой по кинопоиску, если совпадений не было, то берем постер фильма с наивысшей оценкой по кинопоиску)</td><td>String</td>
</tr>
</table>

## Статусы сессии
### Enum: SessionStatus

`SessionStatus` представляет собой возможные статусы сессии. Эти статусы могут использоваться для отслеживания состояния сессии на различных этапах.

#### Значения статусов:

- `waiting` - Ожидание
- `voting` - Голосование
- `closed` - Закрыто

## Получение списка доступных жанров и подборок
## GET /categories
Структура ответа
```json
{
  "genres": [
    {
      "name": "Комедия"
    }
  ],
  "collections": [
    {
      "slug": "dune_2_arrakis",
      "name": "Новинки 2023 года",
      "cover": "http://www.img.ru/img.jpg"
    }
  ]
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>genres</td><td>Массив доступных для выбора жанров</td><td>[Genre]</td>
</tr>
<tr>
<td>collections</td><td>Массив доступных для выбора подборок</td><td>[Collection]</td>
</tr>
</table>

## Создание сеанса для выбора фильмов
## POST /create_session
Структура запроса RequestBody
```json
{
  "device_id": "Qr2da&y38dba7",
  "name": "userName",
  "genres": [
    "Комедия"
  ],
  "collections": []
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя</td><td>String</td>
</tr>
<tr>
<td>name</td><td>Ник пользователя</td><td>String</td>
</tr>
<tr>
<td>genres</td><td>Массив полей name у модели Genre, выбранных пользователем жанров (может быть пустым, если пользователь выбирает по подборкам)</td><td>[String]</td>
</tr>
<tr>
<td>collections</td><td>Массив полей slug у модели Collection, выбранных  пользователем подборок (может быть пустым, если пользователь выбирает по жанрам)</td><td>[String]</td>
</tr>
</table>

Структура ответа
```json
{
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Подключение к сессии
## POST /connect_session
Структура запроса RequestBody
```json
{
  "session_id": "GIGd281",
  "user": {
    "name": "userName",
    "device_id": "Qr2da&y38dba7"
  }
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>user</td><td>Информация о подключаемом пользователе</td><td>User</td>
</tr>
</table>

## Получение информации о комнате ожидания (сессии) (Периодический запрос)
## GET /session_waiting_room
Структура запроса RequestBody
```json
{
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "users": [
    {
      "device_id": "Qr2da&y38dba7",
      "name": "userName"
    }
  ],
  "matched_movies": 0,
  "date": "2024-09-23",
  "status": "waiting"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>users</td><td>Массив пользователей, присоединенных к комнате ожидания</td><td>[User]</td>
</tr>
<tr>
<td>matched_movies</td><td>Число совпавших фильмов</td><td>Integer</td>
</tr>
<tr>
<td>date</td><td>Дата создания сессии</td><td>String</td>
</tr>
<tr>
<td>status</td><td>Статус сессии</td><td>SessionStatus</td>
</tr>
</table>

## Информирование о начале сессии от ее создателя
## POST /start_session
Структура запроса RequestBody

```json
{
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Информирование о выходе из комнаты ожидания
## POST /exit_session
Структура запроса RequestBody

```json
{
  "session_id": "GIGd281",
  "device_id": "Qr2da&y38dba7"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя. Если серийный номер равен серийному номеру создателя, оповещаем пользователей об отмене сессии</td><td>String</td>
</tr>
</table>

## Получение списка фильмов в сессии для выбора
## GET /api/sessions/[session_id]/movies/
Структура запроса
<table>
<tr>
<td>Параметр</td><td>Описание</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td>
</tr>
</table>
Структура ответа

```json
{
  "movies": [
    {
      "id": 999,
      "name": "Дюна",
      "description": "Наследник знаменитого дома Атрейдесов...",
      "year": 2021,
      "countries": [
        "Канада",
        "Венгрия"
      ],
      "poster": "http://www.img.ru/img.jpg",
      "alternative_name": "Dune",
      "rating_kp": 8.5,
      "rating_imdb": 6.1,
      "votes_kp": 1000,
      "votes_imdb": 500,
      "movie_length": 155,
      "genres": [
        {
          "name": "Фантастика"
        },
        {
          "name": "Боевик"
        }
      ],
      "directors": [
        "Дени Вильнев"
      ],
      "actors": [
        "Тимоти Шаламе",
        "Оскар Айзек"
      ]
    }
  ]
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>movies</td><td>Массив фильмов для выбора, отфильтрованный по выбранным жанрам или подборкам</td><td>[MovieDetails]</td>
</tr>
</table>

## Пометка фильма как понравившегося
## POST /like
Структура запроса RequestBody
```json
{
  "film_id": "1q3fj38d",
  "device_id": "Qr2da&y38dba7",
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>film_id</td><td>Id понравившегося фильма</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя, который пометил фильм как понравившийся</td><td>String</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Отмена выбора фильма как понравившегося
## POST /revertLikedMovie
Структура запроса RequestBody
```json
{
  "film_id": "1q3fj38d",
  "device_id": "Qr2da&y38dba7",
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>film_id</td><td>Id фильма</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя, который отменил свой выбор</td><td>String</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Получение количества совпадений и последнего match фильма (Периодический запрос)
## GET /matches
1. Совпадением фильма считается, когда все участники сессии пометили фильм как понравившийся

Структура запроса RequestBody
```json
{
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "count": 5,
  "last_matched_movie":
  {
    "id": 999,
    "name": "Дюна",
    "description": "Наследник знаменитого дома Атрейдесов...",
    "year": 2021,
    "countries": [
      "Канада",
      "Венгрия"
    ],
    "poster": "http://www.img.ru/img.jpg",
    "alternative_name": "Dune",
    "rating_kp": 8.5,
    "rating_imdb": 6.1,
    "votes_kp": 1000,
    "votes_imdb": 500,
    "movie_length": 155,
    "genres": [
      {
        "name": "Фантастика"
      },
      {
        "name": "Боевик"
      }
    ],
    "directors": [
      "Дени Вильнев"
    ],
    "actors": [
      "Тимоти Шаламе",
      "Оскар Айзек"
    ]
  },
  "is_roulette_start": false
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>count</td><td>Количество совпадений</td><td>Integer</td>
</tr>
<tr>
<td>last_matched_movie</td><td>Последний совпавший фильм (может быть null, если совпадений ещё не было)</td><td>MovieDetails</td>
</tr>
<tr>
<td>is_roulette_start</td><td>Признак начала сценария с рулеткой</td><td>Boolean</td>
</tr>
</table>

## Получение списка совпавших фильмов в сессии
## GET /api/sessions/[session_id]/get_matched_movies/
1. Совпадением фильма считается, когда все участники сессии пометили фильм как понравившийся

Структура запроса
<table>
<tr>
<td>Параметр</td><td>Описание</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td>
</tr>
</table>
Структура ответа

```json
{
  "movies": [
    {
      "id": 999,
      "name": "Дюна",
      "poster": "http://www.img.ru/img.jpg"
    }
  ]
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>movies</td><td>Массив совпавших фильмов</td><td>[Movie]</td>
</tr>
</table>

## Получение полной информации о фильме
## GET /api/movieDetails/[movie_id]/
<table>
<tr>
<td>Параметр</td><td>Описание</td>
</tr>
<tr>
<td>movie_id</td><td>Уникальный идентификатор фильма</td>
</tr>
</table>
Структура ответа

```json
{
  "movie":
  {
    "id": 999,
    "name": "Дюна",
    "description": "Наследник знаменитого дома Атрейдесов...",
    "year": 2021,
    "countries": [
      "Канада",
      "Венгрия"
    ],
    "poster": "http://www.img.ru/img.jpg",
    "alternative_name": "Dune",
    "rating_kp": 8.5,
    "rating_imdb": 6.1,
    "votes_kp": 1000,
    "votes_imdb": 500,
    "movie_length": 155,
    "genres": [
      {
        "name": "Фантастика"
      },
      {
        "name": "Боевик"
      }
    ],
    "directors": [
      "Дени Вильнев"
    ],
    "actors": [
      "Тимоти Шаламе",
      "Оскар Айзек"
    ]
  }
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>movie</td><td>Полная информация о фильме</td><td>MovieDetails</td>
</tr>
</table>

## Получение подробной информации о сессии
## GET /api/sessions/[session_id]/
Структура запроса
<table>
<tr>
<td>Параметр</td><td>Описание</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td>
</tr>
</table>

Структура ответа
```json
{
  "session": {
    "id": "Q2Nurf9o",
    "users": [
      {
        "userId": "string",
        "name": "string"
      }
    ],
    "matched_movies": 5,
    "date": "2024-06-22",
    "status": "waiting",
    "session_img": "poster url"
  }
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session</td><td>Данные сессии</td><td>Session</td>
</tr>
</table>

## Информирование о начале события "Рулетка"
## POST /start_roulette
Структура запроса RequestBody
```json
{
  "session_id": "GIGd281",
  "device_id": "Qr2da&y38dba7"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя, который инициировал событие</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "random_movie_id": "1q3ev4m"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>random_movie_id</td><td>Id выбранного фильма для просмотра случайным образом</td><td>String</td>
</tr>
</table>

## Подключение пользователя к событию "Рулетка"
## POST /connect_roulette
Структура запроса RequestBody
```json
{
  "session_id": "GIGd281",
  "device_id": "Qr2da&y38dba7"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>device_id</td><td>Серийный номер устройства пользователя, который подключается к событию</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "random_movie_id": "1q3ev4m"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>random_movie_id</td><td>Id фильма для просмотра, выбранного случайным образом</td><td>String</td>
</tr>
</table>

## Получение списка пользователей, подключенных к событию "Рулетка" (Периодический запрос)
## GET /roulette_users
Структура запроса RequestBody
```json
{
  "session_id": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>session_id</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "users": [
    {
      "name": "userName",
      "device_id": "Qr2da&y38dba7"
    }
  ]
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>users</td><td>Массив пользователей, подключенных к событию "Рулетка"</td><td>[User]</td>
</tr>
</table>