---
## Front matter
title: "Лабораторная работа № 1"
subtitle: "Основы информационной безопасности"
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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

- Целью данной работы является приобретение практических навыков
установки операционной системы на виртуальную машину, настройки ми-
нимально необходимых для дальнейшей работы сервисов.


# Выполнение лабораторной работы

- Проверьте в свойствах VirtualBox месторасположение каталога для виртуальных машин. Для этого в VirtualBox выберите Файл Настройки , вкладка Общие . 

- Задаю конфигурацию жёсткого диска — VDI, динамический виртуальный диск и размера виртуального динамического жёсткого диска. (рис. [-@fig:001]).

![Рис.1](image/1.jpg){#fig:001 width=70%}

(рис. [-@fig:002]).

![Рис.2](image/2.jpg){#fig:002 width=70%}

- Запускаю виртуальную машину и выбираю установку системы на жёсткий диск.(рис. [-@fig:004]).

![Рис.3](image/4.jpg){#fig:004 width=70%}

- Устанавливаю язык для интерфейса и раскладки клавиатуры.(рис. [-@fig:003]).

![Рис.4](image/3.jpg){#fig:003 width=70%}

- Подключение образа диска дополнений гостевой ОС. (рис. [-@fig:005]).

![Рис.5](image/5.jpg){#fig:005 width=70%}

## Информация по машине.

1. Версия ядра Linux (Linux version). (рис. [-@fig:006]).

![Команда dmesg](image/6.jpg){#fig:006 width=70%}

2. Частота процессора (Detected Mhz processor). (рис. [-@fig:007]).

![Запуск образа диска](image/7.jpg){#fig:007 width=70%}

3. Модель процессора (CPU0). (рис. [-@fig:008]).

![Запуск образа диска](image/8.jpg){#fig:008 width=70%}

4. Объем доступной оперативной памяти (Memory available). (рис. [-@fig:009]).

![Запуск образа диска](image/9.jpg){#fig:009 width=70%}

5. Тип обнаруженного гипервизора (Hypervisor detected).(рис. [-@fig:010]).

![Команда dmesg](image/10.jpg){#fig:010 width=70%}

6. Тип файловой системы корневого раздела.(рис. [-@fig:011]).

![Запуск образа диска](image/11.jpg){#fig:011 width=70%}

7. Последовательность монтирования файловых систем.(рис. [-@fig:012]).

![Команда dmesg](image/12.jpg){#fig:012 width=70%}


#  Вывод

- Мы приобрели практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.


# Список литературы{.unnumbered}

::: {#refs}
:::
