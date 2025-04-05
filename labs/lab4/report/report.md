---
## Front matter
title: "Отчет по лабораторной работе №4"
subtitle: "Основы информационной безопасности"
author: "Разанацуа Сара Естэлл, НКАбд-02-23"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с расширенными
атрибутами файлов



# Выполнение лабораторной работы

- От имени пользователя guest, созданного в прошлых лабораторных работах, определяю расширенные атрибуты файлa `/home/guest/dir1/file1` (рис. 1).

![Определение атрибутов](image/1.jpg){#fig:001 width=70%}

- Изменяю права доступа для файла home/guest/dir1/file1 с помощью chmod 600 (рис. 2).

![Изменение прав доступа](image/2.jpg){#fig:002 width=70%}

- Пробую установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest, в ответ получаю отказ от выполнения операции (рис. 3).

![Попытка установки рассширенных атрибутов](image/3.jpg){#fig:003 width=70%}

- Устанавливаю расширенные права уже от имени суперпользователя, теперь нет отказа от выполнения операции (рис. 4).

![Установка расширенных атрибутов](image/4.jpg){#fig:004 width=70%}

- От пользователя guest проверяю правильность установки атрибута (рис. 5).

![Проверка атрибутов](image/5.jpg){#fig:005 width=70%}

- Снимаю расширенные атрибуты с файла (рис. 10).

![Снятие расширенных атрибутов](image/10.jpg){#fig:010 width=70%}

- Проверяю ранее не удавшиеся действия: чтение, переименование, изменение прав доступа. Теперь все из этого выполняется (рис. 11).

![Проверка выполнения действий](image/11.jpg){#fig:011 width=70%}

- Пытаюсь добавить расширенный атрибут i от имени пользователя guest, как и раньше, получаю отказ (рис. 12).

![Попытка добавить расширенный атрибут](image/12.jpg){#fig:012 width=70%}

- Добавляю расширенный атрибут i от имени суперпользователя, теперь все выполнено верно (рис. 13).

![Добавление расширенного атрибута](image/13.jpg){#fig:013 width=70%}

- Пытаюсь записать в файл, дозаписать, переименовать или удалить, ничего из этого сделать нельзя (рис. 14).

![Проверка выполнения действий](image/14.jpg){#fig:014 width=70%}


# Выводы

- В результате выполнения работы вы повысили свои навыки использования интерфейса командой строки (CLI), познакомились на примерах с тем,
как используются основные и расширенные атрибуты при разграничении доступа. Имели возможность связать теорию дискреционного разделения
доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux. Опробовали действие на практике расширенных атрибутов «а» и «i»

