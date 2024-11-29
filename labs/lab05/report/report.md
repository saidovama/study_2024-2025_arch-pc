---
## Front matter
title: "Лабораторная работа №5."
subtitle: "Основы работы с Midnight Commander (mc). Структура программы на языке ассемблера NASM. Системные вызовы в ОС GNU Linux"
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

Приобретение практических навыков работы в Midnight Commander. Освоение инструкций языка ассемблера mov и int.

# Задание

1. Открыть Midnight Commander
2. Перейти в каталог ~/work/arch-pc созданный при выполнении лабораторной работы №4 
3. Создать папку lab05 и перейти в созданный каталог.
4. Создать файл lab5-1.asm 
5. Открыть файл lab5-1.asm для редактирования во встроенном редакторе. 
6. Ввести текст программы из листинга 5.1, сохранить изменения и закрыть файл.
7. Оттранслировать текст программы lab5-1.asm в объектный файл. Выполнить компоновку объектного файла и запустить получившийся исполняемый файл. 
8. Скачать файл in_out.asm со страницы курса в ТУИС.
9. Создайте копию файла lab5-1.asm с именем lab5-2.asm.
10. Исправить текст программы в файле lab5-2.asm с использование подпрограмм из внешнего файла in_out.asm в соответствии с листингом 5.2. Создать исполняемый файл и проверить его работу.
11. В файле lab5-2.asm заменить подпрограмму sprintLF на sprint. Создать исполняемый файл и проверьте его работу. 
12. Выполнить самостоятельную работу
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

1. Открытие Midnight Commander

![Midnight Commander](image/51.jpg){#fig:001 width=70%}

2. Создание папки lab05 и переход в созданный каталог

![Создать папку](image/52.jpg){#fig:002 width=70%}

3. Создание файла lab5-1.asm и открытие его

![Создать файл](image/58.jpg){#fig:003 width=70%}

4. Открытие файла lab5-1.asm для редактирования во встроенном редакторе и введение текста программы из листинга 5.1

![Открыть файлы](image/60.jpg){#fig:004 width=70%}
 
5. Оттранслирование текста программы lab5-1.asm в объектный файл. Выполнение компоновки объектного файла и запуск получившегося исполняемого файла.

![Компановка и запуск](image/54.jpg){#fig:005 width=70%} 

6. Создание копии файла lab5-1.asm с именем lab5-2.asm.

![Создание копии файла](image/57.jpg){#fig:006 width=70%} 

7. Исправление текста программы в файле lab5-2.asm с использование подпрограмм из внешнего файла in_out.asm в соответствии с листингом 5.2. Создание исполняемого файла и проверка его работу.

![Листинг 5.2](image/59.jpg){#fig:007 width=70%} 

8. В файле lab5-2.asm замена подпрограммы sprintLF на sprint. Создание исполняемого файла и проверка его работу.

![sprint](image/61.jpg){#fig:008 width=70%} 

9. Самостоятельная работа:

 9.1 Создание копии файла lab5-1.asm. Внесение изменений для выполнения алгоритма:
• вывести приглашение типа “Введите строку:”;
• ввести строку с клавиатуры;
• вывести введённую строку на экран.

![Выполнение алгоритма](image/ср1.jpg){#fig:009 width=70%} 

![Изменение в тексте](image/ср11.jpg){#fig:010 width=70%} 

 9.2 Создание копии файла lab5-2.asm. Внесение изменений для выполнения алгоритма:
• вывести приглашение типа “Введите строку:”;
• ввести строку с клавиатуры;
• вывести введённую строку на экраан.

![Выполнение алгоритма](image/ср2.jpg){#fig:011 width=70%} 

![Изменение в тексте](image/ср22.jpg){#fig:012 width=70%} 

# Выводы

В процессе выполнения лабораторной работы приобрела практические навыки работы в Midnight Commander.

# Список литературы{.unnumbered}

::: {#refs}
:::
