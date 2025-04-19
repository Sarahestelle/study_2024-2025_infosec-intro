---
## Front matter
title: "Отчет по лабораторной работе №5"
subtitle: "Основы информационной безопасности"
author: "Разанацуа Сара Естэлл НКАбд-02-23"

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

- Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма
смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.


# Выполнение лабораторной работы

- Для лабораторной работы необходимо проверить, установлен ли компилятор gcc, комнда `gcc -v` позволяет это сделать. Также осуществляется отключение системы запретом с помощью `setenforce 0` (рис. 1).

![Подготовка к лабораторной работе](image/1.jpg){#fig:001 width=70%}

- Создание файла simpled.c и запись в файл кода (рис. 2)

![Создание файла](image/2.jpg){#fig:002 width=70%}

```C++ Листинг 1
#include <sys/types.h>
#include <unistd.h>
#include <stdio.h>
int
main ()
{
uid_t uid = geteuid ();
gid_t gid = getegid ();
printf ("uid=%d, gid=%d\n", uid, gid);
return 0;
}
```

- Cодержимое файла выглядит следующти образом (рис. 3)

![Содержимое файла](image/3.jpg){#fig:003 width=70%}

- Компилирую файл, проверяю, что он скомпилировался (рис. 4)

![Компиляция файла](image/4.jpg){#fig:004 width=70%}

- Запускаю исполняемый файл. В выводе файла выписыны номера пользоватея и групп, от вывода при вводе if, они отличаются только тем, что информации меньше (рис. 5)

![Сравнение команд](image/5.jpg){#fig:005 width=70%}

- Создание, запись в файл и компиляция файла simpled2.c. Запуск программы (рис. 6)

![Создание и компиляция файла](image/6.jpg){#fig:006 width=70%}

```C++ Листинг 2
#include <sys/types.h>
#include <unistd.h>
#include <stdio.h>
int
main ()
{
uid_t real_uid = getuid ();
uid_t e_uid = geteuid ();
gid_t real_gid = getgid ();
gid_t e_gid = getegid () ;
printf ("e_uid=%d, e_gid=%d\n", e_uid, e_gid);
printf ("real_uid=%d, real_gid=%d\n", real_uid,
real_gid);
return 0;
}
```

(рис. 7)

![Содержимое файла](image/8.jpg){#fig:007 width=70%}

- С помощью chown изменяю владельца файла на суперпользователя, с помощью chmod изменяю права доступа (рис. 9)

![Смена владельца файла и прав доступа к файлу](image/9.jpg){#fig:009 width=70%}

- Создание и компиляция файла readfile.c (рис. 10)

![Создание и компиляция файла](image/10.jpg){#fig:010 width=70%}

```C++ Листинг 3
#include <fcntl.h>
#include <stdio.h>
#include <sys/stat.h>
#include <sys/types.h>
#include <unistd.h>
int
main (int argc, char* argv[])
{
unsigned char buffer[16];
size_t bytes_read;
int i;
int fd = open (argv[1], O_RDONLY);
do
{
bytes_read = read (fd, buffer, sizeof (buffer));
for (i =0; i < bytes_read; ++i) printf("%c", buffer[i]);
}
while (bytes_read == sizeof (buffer));
close (fd);
return 0;
}
```

(рис. 12)

![Содержимое файла](image/12.jpg){#fig:012 width=70%}

- Снова от имени суперпользователи меняю владельца файла readfile. Далее меняю права доступа так, чтобы пользователь guest не смог прочесть содержимое файла (рис. 13)

![Смена владельца файла и прав доступа к файлу](image/13.jpg){#fig:013 width=70%}

- Проверка прочесть файл от имени пользователя guest.Прочесть файл не удается (рис. 14)

![Попытка прочесть содержимое файла](image/14.jpg){#fig:014 width=70%}

- Попытка прочесть тот же файл с помощью программы readfile, в ответ получаем "отказано в доступе" (рис. 15)

![Попытка прочесть содержимое файла программой](image/15.jpg){#fig:015 width=70%}

- Попытка прочесть файл `\etc\shadow` с помощью программы, все еще получаем отказ в доступе (рис. 16)

![Попытка прочесть содержимое файла программой](image/16.jpg){#fig:016 width=70%}

- Проверяем папку tmp на наличие атрибута Sticky, т.к. в выводе есть буква t, то атрибут установлен (рис. 17)

![Проверка атрибутов директории tmp](image/17.jpg){#fig:017 width=70%}



# Выводы

- Изучила механизм изменения идентификаторов, применила SetUID- и Sticky-биты. Получила практические навыки работы в консоли с дополнительными атрибутами. Рассмотрела работы механизма
смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Список литературы{.unnumbered}

::: {#refs}
:::

