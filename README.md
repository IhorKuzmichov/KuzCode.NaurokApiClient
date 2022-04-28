[EN](README_en.md) | [RU](README.md)

# NaurokApiClient

## Что такое NaurokApiClient?
В Украине существует популярный сайт https://naurok.com.ua, предназначенный для тестирования учеников. У него есть непубличное недокументированное API.
Данная библиотека классов является API-клиентом для сайта и позволяет взаимодействовать с большинством его функций.

Уникальностью библиотеки являеться подробная документация на русском языке (через *summary*) каждого метода и класса,
из которой можно узнать все ограничения и возможные причины ошибок.

## Какой функционал уже доступен?
На данный момент библиотека поддерживает возможности неавторизованных пользователей и учителей.
Так как авторизация на сайте производиться с использованием *reСaptcha*, авторизация в библиотеке реализована через *cookie*-значение '*PHPSESSID*'.

Реализованный функционал *неавторизованного пользователя*:
* Получение сессии прохождения теста
* Завершение сессии прохождения теста
* Сохранение ответа на вопрос теста
* Получение флеш-карт теста (при наличие доступа от учителя)
* Получение карточек и лучшего результата игры на сопостовления вопросов с ответами (при наличие доступа от учителя)
* Сохранение результата игры на сопостовления вопросов с ответами (при наличие доступа от учителя)

Реализованный функционал *пользователя-учителя*:
* Весь функционал неавторизованного пользователя
* Получение информации о вопросе
* Получение флеш-карт теста (при наличии базовой сертефикации)
* Получение карточек и лучшего результата игры на сопостовления вопросов с ответами (при наличии базовой сертефикации)
* Сохранение результата игры на сопостовления вопросов с ответами (при наличии базовой сертефикации)
* Получения документа своего теста
* Поиск документов тестов со схожими вопросами
* Получение краткого и полного excel-отчёта о прохождении домашнего задания

Также реализован полностью рабочий *RealTime*-клиент для взаимодействия с тестированиями, проходящими в режиме реального времени.

## Что планируеться сделать?
* Проверка значения '*PHPSESSID*' на авторизованность пользователя-учителя
* Проверка наличия базового сертефиката у пользователя-учителя
* Расширение функционала
* Добавление *Unit*-тестов на замену консольному проекту
* Добавление интерактивной документации (вики) на *github* в данном репозитории
* Создание полноценного клиента - мобильного приложения

## Документация
Документация реализованна в коде через *summary*, а также в репозитории [тут](https://github.com/IhorKuzmichov/KuzCode.NaurokApiClient/wiki).

## Примечания
В проекте используеться *user-secrets*. Файл *secret.json* имеет следующий вид:
```json
{
  "teacherPhpSessionId": "PHPSESSID учителя...",
  "sessionId": 0,
  "documentId": 0,
  "userAgent": "Заголовок User-Agent..."
}
```

## Лицензия
Данный проект покрыт лицензией *MIT*.

