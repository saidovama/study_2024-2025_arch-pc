---
## Front matter
title: "Шаблон отчёта по лабораторной работе №6"
subtitle: "Арифметические операции в NASM."
author: "Саидова Маржина Авдулвохидовна"

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

Освоение арифметических инструкций языка ассемблера NASM.

# Задание

1. Создать каталог для программ лабораторной работы № 6.
2. Создать файл lab6-1.asm и ввести в файл lab6-1.asm текст программы из листинга 6.1. Создать исполняемый файл и запустить его.
3. Исправить текста программы (Листинг 6.1), создать исполняемый файл и запустить его.
4. Создать файл lab6-2.asm и ввести в него текст программы из листинга 6.2. Исправить текст программы (Листинг 6.2). Создать исполняемый файл и запустите его.
5. Заменить функцию iprintLF на iprint. Создать исполняемый файл и запустить его. 
6. Создать файл lab6-3.asm. Ввести текст программы из листинга 6.3. 
7. Изменить текст программы для вычисления выражения 𝑓(𝑥) = (4 ∗ 6 + 2)/5. Создать исполняемый файл и проверить его работу.
8. Создать файл variant.asm в каталоге. Ввести в файл variant.asm текст программы из 6.4 листинга. Создать исполняемый файл и запустить его. 
9. Ответить на вопросы.
10. Самостоятельная работа 

# Теоретическое введение

Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. [-@tbl:std-dir] приведено краткое описание стандартных каталогов Unix.

: Описание некоторых каталогов файловой системы GNU Linux {#tbl:std-dir}

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

Более подробно про Unix см. в [@tanenbaum_book_modern-os_ru; @robbins_book_bash_en; @zarrelli_book_mastering-bash_en; @newham_book_learning-bash_en].

# Выполнение лабораторной работы

1. Создать каталог для программ лабораторной работы № 6.
 
![каталог лаб6](image/л1.png){#fig:001 width=70%} 

2. Создать файл lab6-1.asm и ввести в файл lab6-1.asm текст программы из листинга 6.1. Создать исполняемый файл и запустить его. 

![текст программы из листинга 6.1](image/л3.png){#fig:002 width=70%}

![запуск исполняемый файл](image/л5.png){#fig:003 width=70%}

3. Исправить текста программы (Листинг 6.1), создать исполняемый файл и запустить его. 

![исправленый текст (листинг 6.1)](image/л4.png){#fig:004 width=70%}

![запуск файла](image/л5.png){#fig:005 width=70%}

4. Создать файл lab6-2.asm и ввести в него текст программы из листинга 6.2. 

![запуск lab6-2](image/л6.png){#fig:006 width=70%}

![текст из листинга 6.2](image/л7.png){#fig:007 width=70%}

5. Исправить текст программы (Листинг 6.2). Создать исполняемый файл и запустите его.

![исправленный текст](image/л8.png){#fig:008 width=70%} 

![запуск файла](image/л9.png){#fig:009 width=70%}

6. Заменить функцию iprintLF на iprint. Создать исполняемый файл и запустить его. 

![запуск файла с заменой](image/л10.png){#fig:010 width=70%}

7. Создать файл lab6-3.asm. Ввести текст программы из листинга 6.3. Запустить файл.

![запуск файла lab6-3.asm](image/л11.png){#fig:011 width=70%}

8. Изменить текст программы для вычисления выражения 𝑓(𝑥) = (4 ∗ 6 + 2)/5. Создать исполняемый файл и проверить его работу. 

![изменения текста](image/л13.png){#fig:012 width=70%}

![проверка работы файла](image/л12.png){#fig:013 width=70%}

9. Создать файл variant.asm в каталоге. Ввести в файл variant.asm текст программы из 6.4 листинга. Создать исполняемый файл и запустить его. 

![листинг 6.4](image/л14.png){#fig:014 width=70%}

![запуск файла](image/л15.png){#fig:015 width=70%}

10. Ответить на вопросы:

 Какие строки листинга 6.4 отвечают за вывод на экран сообщения ‘Ваш вариант:’? 
mov eax, rem call sprint 2
 Для чего используется следующие инструкции?
mov ecx, x
mov edx, 80
call sread
Для полученния данных с клавиатуры.
 Для чего используется инструкция “call atoi”?
Для преобразования ASCII кода в число
 Какие строки листинга 6.4 отвечают за вычисления варианта?
xor edx, edx mov ebx, 20 div ebx inc edx
 В какой регистр записывается остаток от деления при выполнении инструкции “div ebx”?
 Для чего используется инструкция “inc edx”?
Увелечение edx на 1
 Какие строки листинга 6.4 отвечают за вывод на экран результата вычислений?
mov eax, edx
call iprintlF

11. Самостоятельная работа

![проверка работы файла](image/л16.png){#fig:016 width=70%}

![текст программы](image/л17.png){#fig:017 width=70%} 

# Выводы

Освоила арифметические инструкции языка ассемблера NASM.

# Список литературы{.unnumbered}

::: {#refs}
:::
