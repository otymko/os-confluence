﻿# Функции взимодействия с confluence

## Введение

Модуль предоставляет набор функционала для взаимодействия с Atlassian Confluence посредством REST-API.
Описание продукта по ссылке `https://ru.atlassian.com/software/confluence`

## Установка

Библиотеку можно установить двумя способами:

* Используя менеджер пакетов opm

```
opm install confluence
```

*  Копированием библиотеки в папку lib osctript (требуется установленная библиотека json)

Выбираем временный каталог и клонируем библиотеку

``` 
git clone https://github.com/otymko/os-confluence.git
```

Копируем библиотеку в папку /path/to/oscript/lib

## Использование

Все методы модуля требуют параметры подключения к серверу confluence: Адрес и учетные данные.

Для начала необходимо сформировать описание подключения методом `ОписаниеПодключения`

### Примеры

#### Подключение

`Подключение = Confluence.ОписаниеПодключения("https://confluence.myserver.ru", "user", "password")`.

#### Создание страницы

`ИдентификаторНовойСтраницы = Confluence.СоздатьСтраницу(Подключение, "SpaceKey", "Новая страница", "Содержимое новой страницы")`

#### Переименование страницы

`ИдентификаторНовойСтраницы = Confluence.ОбновитьСтраницу(Подключение, "SpaceKey", "Новое имя страницы", ИдентификаторНовойСтраницы)`

#### Удаление страницы

`Confluence.УдалитьСтраницу(Подключение, "SpaceKey", "Новое имя страницы")`
