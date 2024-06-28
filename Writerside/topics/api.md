# Api

## Models
## User

```json
{
  "userId": "device_id",
  "name": "userName"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Серийный номер устройства</td><td>String</td>
</tr>
<tr>
<td>name</td><td>Ник пользователя</td><td>String</td>
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
  "id": "1q3ev4m",
  "name": "Новинки 2023 года",
  "imgUrl": "http://www.img.ru/img.jpg"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Уникальный идентификатор подборки</td><td>String</td>
</tr>
<tr>
<td>name</td><td>Имя подборки</td><td>String</td>
</tr>
<tr>
<td>imgUrl</td><td>Ссылка на постер подборки</td><td>String</td>
</tr>
</table>

## ShortMovie
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

## Movie
```json
{
  "id": 999,
  "name": "Дюна",
  "poster": "http://www.img.ru/img.jpg",
  "alternative_name": "Dune",
  "rating_kp": 8.5,
  "numOfMarksKinopoisk": 1000,
  "rating_imdb": 6.1,
  "numOfMarksImdb": 500,
  "genres": [
    {
      "name": "Фантастика"
    },
    {
      "name": "Боевик"
    }
  ],
  "year": 2021,
  "countries": [
    "Канада",
    "Венгрия"
  ],
  "movie_length": 155,
  "description": "Наследник знаменитого дома Атрейдесов...",
  "actors": [
    "Тимоти Шаламе",
    "Оскар Айзек"
  ],
  "directors": [
    "Дени Вильнев"
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
<td>poster</td><td>Ссылка на постер фильма</td><td>String</td>
</tr>
<tr>
<td>alternative_name</td><td>Название фильма на другом языке</td><td>String? (может быть null)</td>
</tr>
<tr>
<td>rating_kp</td><td>Оценка на Кинопоиске</td><td>Float</td>
</tr>
<tr>
<td>numOfMarksKinopoisk</td><td>Количество оценок на Кинопоиске</td><td>Integer</td>
</tr>
<tr>
<td>rating_imdb</td><td>Оценка на Imdb</td><td>Float</td>
</tr>
<tr>
<td>numOfMarksImdb</td><td>Количество оценок на Imdb</td><td>Integer</td>
</tr>
<tr>
<td>genres</td><td>Массив жанров фильма</td><td>[Genre]</td>
</tr>
<tr>
<td>year</td><td>Дата выхода</td><td>Integer</td>
</tr>
<tr>
<td>countries</td><td>Массив стран фильма</td><td>[String]</td>
</tr>
<tr>
<td>movie_length</td><td>Продолжительность фильма в минутах</td><td>Integer</td>
</tr>
<tr>
<td>description</td><td>Описание фильма</td><td>String</td>
</tr>
<tr>
<td>actors</td><td>Массив актеров</td><td>[String]</td>
</tr>
<tr>
<td>directors</td><td>Массив режиссеров</td><td>[String]</td>
</tr>
</table>

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
      "id": "1q3ev4m",
      "name": "Новинки 2023 года",
      "imgUrl": "http://www.img.ru/img.jpg"
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
  "userId": "device_id",
  "name": "userName",
  "genres": [
    {
      "name": "Комедия"
    }
  ],
  "collections": []
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя</td><td>String</td>
</tr>
<tr>
<td>name</td><td>Ник пользователя</td><td>String</td>
</tr>
<tr>
<td>genres</td><td>Массив выбранных пользователем жанров (может быть пустым, если пользователь выбирает по подборкам)</td><td>[Genre]</td>
</tr>
<tr>
<td>collections</td><td>Массив выбранных пользователем подборок (может быть пустым, если пользователь выбирает по жанрам)</td><td>[Collection]</td>
</tr>
</table>

Структура ответа
```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Подключение к сессии
## POST /connect_session
Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281",
  "user": {
    "userId": "device_id",
    "name": "userName"
  }
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
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
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "users": [
    {
      "userId": "device_id",
      "name": "userName"
    }
  ],
  "isSessionStart": false,
  "isSessionEnd": false
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
<td>isSessionStart</td><td>Флаг, который оповещает пользователей о том, что сеанс был начат создателем</td><td>Boolean</td>
</tr>
<tr>
<td>isSessionEnd</td><td>Флаг, который оповещает пользователей о том, что сеанс был отменен создателем</td><td>Boolean</td>
</tr>
</table>

## Информирование о начале сессии от ее создателя
## POST /start_session
Структура запроса RequestBody

```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Информирование о выходе из комнаты ожидания
## POST /exit_session
Структура запроса RequestBody

```json
{
  "sessionCode": "GIGd281",
  "userId": "device_id"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя. Если серийный номер равен серийному номеру создателя, оповещаем пользователей об отмене сессии</td><td>String</td>
</tr>
</table>

## Получение списка фильмов для выбора
## GET /movies
Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "movies": [
    {
      "id": 999,
      "name": "Дюна",
      "poster": "http://www.img.ru/img.jpg",
      "alternative_name": "Dune",
      "rating_kp": 8.5,
      "numOfMarksKinopoisk": 1000,
      "rating_imdb": 6.1,
      "numOfMarksImdb": 500,
      "genres": [
        {
          "name": "Фантастика"
        },
        {
          "name": "Боевик"
        }
      ],
      "year": 2021,
      "countries": [
        "Канада",
        "Венгрия"
      ],
      "movie_length": 155,
      "description": "Наследник знаменитого дома Атрейдесов...",
      "actors": [
        "Тимоти Шаламе",
        "Оскар Айзек"
      ],
      "directors": [
        "Дени Вильнев"
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
<td>movies</td><td>Массив фильмов для выбора, отфильтрованный по выбранным жанрам или подборкам</td><td>[Movie]</td>
</tr>
</table>

## Пометка фильма как понравившегося
## POST /like
Структура запроса RequestBody
```json
{
  "filmId": "1q3fj38d",
  "userId": "device_id",
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>filmId</td><td>Id понравившегося фильма</td><td>String</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя, который пометил фильм как понравившийся</td><td>String</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Отмена выбора фильма как понравившегося
## POST /revertLikedMovie
Структура запроса RequestBody
```json
{
  "filmId": "1q3fj38d",
  "userId": "device_id",
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>filmId</td><td>Id фильма</td><td>String</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя, который отменил свой выбор</td><td>String</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>

## Получение количества совпадений и последнего match фильма (Периодический запрос)
## GET /matches
1. Совпадением фильма считается, когда все участники сессии пометили фильм как понравившийся

Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "count": 5,
  "lastMatchedMovie": {
    "id": 999,
    "name": "Дюна",
    "poster": "http://www.img.ru/img.jpg",
    "alternative_name": "Dune",
    "rating_kp": 8.5,
    "numOfMarksKinopoisk": 1000,
    "rating_imdb": 6.1,
    "numOfMarksImdb": 500,
    "genres": [
      {
        "name": "Фантастика"
      },
      {
        "name": "Боевик"
      }
    ],
    "year": 2021,
    "countries": [
      "Канада",
      "Венгрия"
    ],
    "movie_length": 155,
    "description": "Наследник знаменитого дома Атрейдесов...",
    "actors": [
      "Тимоти Шаламе",
      "Оскар Айзек"
    ],
    "directors": [
      "Дени Вильнев"
    ]
  },
  "isRouletteStart": false
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
<td>lastMatchedMovie</td><td>Последний совпавший фильм (может быть null, если совпадений ещё не было)</td><td>Movie</td>
</tr>
<tr>
<td>isRouletteStart</td><td>Признак начала сценария с рулеткой</td><td>Boolean</td>
</tr>
</table>

## Получение списка совпавших фильмов
## GET /listMatches
1. Совпадением фильма считается, когда все участники сессии пометили фильм как понравившийся

Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "shortMovies": [
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
<td>shortMovies</td><td>Массив совпавших фильмов</td><td>[ShortMovie]</td>
</tr>
</table>

## Получение полной информации о фильме
## GET /movie/[id]
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>id</td><td>Уникальный идентификатор фильма</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "movie": {
    "id": 999,
    "name": "Дюна",
    "poster": "http://www.img.ru/img.jpg",
    "alternative_name": "Dune",
    "rating_kp": 8.5,
    "numOfMarksKinopoisk": 1000,
    "rating_imdb": 6.1,
    "numOfMarksImdb": 500,
    "genres": [
      {
        "name": "Фантастика"
      },
      {
        "name": "Боевик"
      }
    ],
    "year": 2021,
    "countries": [
      "Канада",
      "Венгрия"
    ],
    "movie_length": 155,
    "description": "Наследник знаменитого дома Атрейдесов...",
    "actors": [
      "Тимоти Шаламе",
      "Оскар Айзек"
    ],
    "directors": [
      "Дени Вильнев"
    ]
  }
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>movie</td><td>Полная информация о фильме</td><td>Movie</td>
</tr>
</table>

## Получение подробной информации о сессии
## GET /api/sessions/[sessionCode]/
Структура ответа
```json
{
  "id": "Q2Nurf9o",
  "users": [
    {
      "userId": "string",
      "name": "string"
    }
  ],
  "movies": [
    {
      "id": 43395,
      "name": "Название",
      "description": "текст описания…",
      "year": 1972,
      "countries": [
        "страна1",
        "страна2"
      ],
      "poster": "http://www.img.ru/img.jpg",
      "alternative_name": null,
      "rating_kp": 8.548,
      "rating_imdb": 8.1,
      "movie_length": 160,
      "genres": [
        {
          "name": "название жанра1"
        },
        {
          "name": " название жанра2"
        }
      ],
      "persons": []
    }
  ],
  "matched_movies": [],
  "date": "2024-06-22",
  "status": "waiting"
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
<td>users</td><td>Массив пользователей, подключенных к сессии</td><td>[User]</td>
</tr>
<tr>
<td>movies</td><td>Массив фильмов для выбора</td><td>[Movie]</td>
</tr>
<tr>
<td>matched_movies</td><td>Массив совпавших фильмов</td><td>[Movie]</td>
</tr>
<tr>
<td>date</td><td>Дата создания сессии</td><td>String</td>
</tr>
<tr>
<td>status</td><td>Текущий статус сессии</td><td>String</td>
</tr>
</table>

## Информирование о начале события "Рулетка"
## POST /start_roulette
Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281",
  "userId": "device_id"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя, который инициировал событие</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "randomMovieId": "1q3ev4m"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>randomMovieId</td><td>Id выбранного фильма для просмотра случайным образом</td><td>String</td>
</tr>
</table>

## Подключение пользователя к событию "Рулетка"
## POST /connect_roulette
Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281",
  "userId": "device_id"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
<tr>
<td>userId</td><td>Серийный номер устройства пользователя, который подключается к событию</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "randomMovieId": "1q3ev4m"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>randomMovieId</td><td>Id фильма для просмотра, выбранного случайным образом</td><td>String</td>
</tr>
</table>

## Получение списка пользователей, подключенных к событию "Рулетка" (Периодический запрос)
## GET /roulette_users
Структура запроса RequestBody
```json
{
  "sessionCode": "GIGd281"
}
```
<table>
<tr>
<td>Поле</td><td>Описание</td><td>Тип данных</td>
</tr>
<tr>
<td>sessionCode</td><td>Уникальный код сеанса, по которому пользователи могут присоединиться (Состоит из 7 символов: 4 буквы и 3 цифры)</td><td>String</td>
</tr>
</table>
Структура ответа

```json
{
  "users": [
    {
      "userId": "device_id",
      "name": "userName"
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