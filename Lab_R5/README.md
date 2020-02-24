Lab5. Рынок недвижимости в Москве
================
Alexey Klimov
08 июня, 2017

-   [Текст задания доступен [по ссылке](https://docs.google.com/document/d/1J6iW5QnxXUECdo7fKcBOLXqgdiRpFc_fKhKM5uAmClk)](#----)
-   [Загрузка нужных пакетов и хорошие настройки](#-----)
-   [Служебные функции](#-)
-   [Загрузка данных](#-)
    -   [Считываем данные из таблиц](#---)

Текст задания доступен [по ссылке](https://docs.google.com/document/d/1J6iW5QnxXUECdo7fKcBOLXqgdiRpFc_fKhKM5uAmClk)
===================================================================================================================

Загрузка нужных пакетов и хорошие настройки
===========================================

``` r
options(scipen = 10, digits = 2, OutDec = '.')
knitr::opts_chunk$set(
  cache = TRUE
  , echo = FALSE
  , autodep = TRUE
  , encoding = "UTF-8"
  , dpi = 96
  , global.par = TRUE
  , par = TRUE
  , crop = TRUE
  , comment = NA
  )
```

Если следующий блок кода выдает ошибки, то нужно доставить необходимые библиотеки

``` r
library(pander)
library(tidyverse) # Наше все
library(forcats) # Работа с факторными переменными
library(rvest) # Считываем таблицы из интернета
library(stringi) # Операции с кодировкой строк
library(lubridate) # Работа с датами
library(tsoutliers) # Определение выбросов во временных рядах
```

Служебные функции
=================

-   `save_url` - для сохранения страниц с обработкой javascript
-   `write` - для сохранения файлов с одновременным созданием необходимых поддиректорий
-   `apply_function_to_column`, `apply_function_to_column` - применение функции к колонке и нескольким колонкам (аналог apply)
-   `remove_whitespace`

Загрузка данных
===============

Берем данные с restate.ru (исходный код страниц для Москвы и Санкт-Петербурга сохранен в папке `data/raw_html`).

Считываем данные из таблиц
--------------------------

Здесь нам поможет пакет `rvest` и его функции `html_node`, `html_table`. Подсказка - исходная таблица находится в css-селекторе — "div.chart table". Делается это так: `html_table_node <- html_node(x = read_html(filename), css = "div.chart table")` и `realty_data <- html_table(html_table_node, fill = TRUE, dec = ",")`.

Затем данные и даже сами имена переменных нужно отчистить (например, я использовал пакет `stringi` начиная с такого `names(data) %>% stri_trans_tolower %>%   stri_trans_general("latin") %>% stri_trans_general("latin-ascii") %>% iconv(to = 'ASCII//TRANSLIT')`)
