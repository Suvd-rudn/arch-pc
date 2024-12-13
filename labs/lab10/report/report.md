---
## Front matter
title: "Отчёт по лабораторной работе 10"
subtitle: "Архитектура компьютера"
author: "Сувд Адиасурэн"

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

Целью работы является приобретение навыков написания программ для работы с файлами.

# Выполнение лабораторной работы

Я создала каталог для лабораторной работы № 10 и перешла в него.  
В этом каталоге я создала три файла: lab10-1.asm, readme-1.txt и readme-2.txt.

В файле lab10-1.asm я написала программу из листинга 10.1, которая записывает сообщение в файл. Затем я создала исполняемый файл из этого кода и проверила его работу (рис. [-@fig:001]).

![Программа в файле lab10-1.asm](image/01.png){ #fig:001 width=70%, height=70% }

Программа запрашивает строку и перезаписывает её в файл readme.txt.  
Если файл не существует, строка не будет записана никуда (рис. [-@fig:002]).

![Запуск программы lab10-1.asm](image/02.png){ #fig:002 width=70%, height=70% }

Чтобы запретить выполнение исполняемого файла lab10-1, я использовала команду chmod для изменения прав доступа. Я сняла атрибут "x" во всех трёх позициях. После этого я попыталась выполнить файл.  

Однако файл не запускается, так как выполнение запрещено из-за отсутствия атрибута "x" во всех трёх позициях (рис. [-@fig:003]).

![Запуск запрещён](image/03.png){ #fig:003 width=70%, height=70% }

Я изменила права доступа к файлу lab10-1.asm, добавив права на выполнение с помощью команды chmod.  
Затем я попыталась выполнить файл (рис. [-@fig:004]).

В результате файл запустился, и терминал попытался выполнить его содержимое как команды командной строки. Однако, так как это файл с кодом на языке ассемблера, а не команды терминала, возникли ошибки. Тем не менее, если в такой файл добавить команды командной строки, можно будет их выполнить, запустив файл.

![Файл с кодом с разрешением запуска](image/04.png){ #fig:004 width=70%, height=70% }

Далее я установила права доступа к файлам readme в соответствии с указанным вариантом из таблицы 10.4. Чтобы проверить правильность выполнения, я использовала команду ls -l (рис. [-@fig:005]).

Для варианта 4: -w- --- -w- ; 001 011 110

![Установка прав](image/05.png){ #fig:005 width=70%, height=70% }

## Задание для самостоятельной работы

Я написала программу, работающую по следующему алгоритму (рис. [-@fig:006], [-@fig:007]):

1. Вывод приглашения: “Как Вас зовут?”  
2. Ввод с клавиатуры фамилии и имени.  
3. Создание файла с именем name.txt.  
4. Запись в файл сообщения “Меня зовут”.  
5. Дополнение файла строкой, введённой с клавиатуры.  
6. Закрытие файла.

![Программа в файле lab10-2.asm](image/06.png){ #fig:006 width=70%, height=70% }

![Запуск программы lab10-2.asm](image/07.png){ #fig:007 width=70%, height=70% }

# Выводы

Я освоила работу с файлами и управление правами доступа.
