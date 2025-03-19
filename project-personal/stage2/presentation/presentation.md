---
## Front matter
lang: ru-RU
title: Отчёт по индивидуальному проекту. Этап 2
author: |
	 Разанацуа Сара Естэлл  НКАбд-02-23\inst{1}

institute: |
	\inst{1}Российский Университет Дружбы Народов

date: 19 марта, Москва, Россия

## Formatting
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 169
section-titles: true

---
# Информация

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Разанацуа Сара Естэлл
  * Студентка, НКАбд-02-23
  * Российский университет дружбы народов
  * [1032225834@pfur.ru](mailto: 1032225834@pfur.ru)

:::

::::::::::::::

# Цели и задачи работы

## Цель лабораторной работы

Установка DVWA в гостевой системе Kali Linux.

# Процесс выполнения лабораторной работы

## Клонируем репозиторий
Клонируем репозиторий git: sudo git clone https://github.com/digininja/DVWA.git.

![Клонируем репозиторий](image/1.jpg){#fig:001 width=/70%}

## Скопируем файл
Скопируем файл конфигурации и переименуем его: cp config.inc.php.dist config.inc.php. 

![редактировать файл ](image/3.jpg){#fig:002 width=50%}

## Установка mariadb
Установим mariadb

![Установка mariadb ](image/4.jpg){#fig:003 width=70%}

## Запустиv сервер Apache
Запустиv сервер Apache : sudo service apache2 start

![Запустим базу ](image/7.jpg){#fig:004 width=70%}

## Создание базу данных
Давайте нажмем create, чтобы создать базу данных. Затем введите имя пользователя и пароль

![Запустим базу ](image/9.jpg){#fig:005 width=70%}


# Выводы по проделанной работе

## Вывод

В ходе выполнения данной лабораторной работыб, я установила DVWA в гостевой системе Kali Linux.

## Список литературы{.unnumbered}

1. Парасрам, Ш. Kali Linux: Тестирование на проникновение и безопасность : Для профессионалов. Kali Linux / Ш. Парасрам, А. Замм, Т. Хериянто, и др. – Санкт-Петербург : Питер, 2022. – 448 сс..



