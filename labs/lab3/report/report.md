---
## Front matter
title: "Шаблон отчёта по лабораторной работе 3"
subtitle: "Дисциплина: Основы информационной безопасности"
author: "Разанацуа Сара Естэлл"

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

- Получение практических навыков работы в консоли с атрибутами фай- лов для групп пользователей.

# Выполнение лабораторной работы

- В предыдущей работе в установленной операционной системе создали учетную запись пользователя guest и задали пароль для пользователя (используя учетную запись администратора) (рис. [-@fig:001]).  (рис. [-@fig:002]).

![создать guest](image/1.jpg){#fig:001 width=70%}

![создать guest](image/2.jpg){#fig:002 width=70%}

- Аналогично создали второго пользователя guest2 и выполнили вход в эту учетную запись. (рис. [-@fig:003]).

![создать guest2](image/3.jpg){#fig:003 width=70%}

- Добавили пользователя guest2 в группу guest используя команду: gpasswd -a guest2 guest. (рис. [-@fig:004]).

![Добавление пользователей в группу](image/4.jpg){#fig:004 width=70%}

- Выполнили вход в две учетные записи guest guest2 на разных консолях.  (рис. [-@fig:005]).

![вход в две учетные](image/5.jpg){#fig:005 width=70%}

- Для обоих пользователей командой Pwd определили директорию, в которой находимся. Сравнили ее с приглашением командой строки.

- Уточнили имя нашего пользователя, его группу, кто входит в нее и к каким группам принадлежит он сам. Определили командами groups guest и groups guest2, в какие группы входят пользователи guest и guest2. Сравнили выводы команды groups с выводом команд id –Gn и id –G. (рис. [-@fig:005]).

![Информация о пользователях](image/5.jpg){#fig:006 width=70%}


-	Сравнили полученную информацию с содержимым файла /etc/group. Посмотрели файл командой cat /etc/group. (рис. [-@fig:006]).

![Информация о пользователях](image/6.jpg){#fig:007 width=70%}

- От имени пользователя guest2 выполнили регистрацию пользователя guest2 в группе guestкомандой newgrp guest. (рис. [-@fig:007]).

![Содержимое файла /etc/group и регистрация в группе](image/7.jpg){#fig:008 width=70%}

- От имени пользователя guest изменили права директории /home/guest, разрешив все действия для пользователей группы: chmod g+rwx /home/guest. И также от имени пользователя guest сняли с директории /home/guest/dir1 все атрибуты командой chmod 000 dirl и проверили правильность снятия атрибуто. (рис. [-@fig:008]).

![Заполнение таблицы](image/8.jpg){#fig:009 width=70%}

- Обозначения в таблице: (1) Создание файла, (2) Удаление файла, (3) Запись в файл, (4) Чтение файла, (5) Смена директории, (6) Просмотр файлов в директории, (7) Переименование файл, (8) Смена атрибутов файла.

- Установленные права и разрешённые действия для групп : Таблица 2.1 (рис. [-@fig:009]).

![Заполнение таблицы 2.1](image/9.jpg){#fig:010 width=70%}

- Таблица (рис. [-@fig:010]).

![Заполнение блицы 2.1](image/10.jpg){#fig:011 width=70%}

- Минимальные права для совершения операций : Таблица 2.2 (рис. [-@fig:011]).

![Заполнение таблицы 2.2](image/11.jpg){#fig:012 width=70%}


# Выводы

- в этой лаборатории мы узнали, как получить практические навыки работы в консоли с атрибутами файлов для групп пользователей.

# Список литературы{.unnumbered}

::: {#refs}
:::
