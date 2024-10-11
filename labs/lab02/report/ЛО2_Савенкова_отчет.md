---
## Front matter
title: "Лабораторная работа №2"
subtitle: "дисциплина: Архитектура компьютера"
author: "Савенкова Алиса Евгеньевна"

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

Цель данной лабораторной работы заключается в изучении идеологии и
применении средств контроля версий, а также в приобретении практических навыков
по работе с системой git.

# Задание

1. Настройка GitHub.
2. Базовая настройка Git.
3. Создание SSH-ключа.
4. Создание рабочего пространства и репозитория курса на основе шаблона.
5. Создание репозитория курса на основе шаблона.
6. Настройка каталога курса.
7. Выполнение заданий для самостоятельной работы

# Теоретическое введение

Системы контроля версий (Version Control System, VCS) применяются при работе нескольких человек над одним проектом. Обычно основное дерево проекта хранится в локальном или удалённом репозитории, к которому настроен доступ для участников проекта.
В классических системах контроля версий используется централизованная
модель, предполагающая наличие единого репозитория для хранения файлов. Cреди распределённых VCS наиболее известны Git, Bazaar, Mercurial. Принципы их работы схожи, отличаются они в основном синтаксисом используемых в работе команд. Система контроля версий Git представляет собой набор программ командной строки. Доступ к ним можно получить из терминала посредством ввода команды git с различными опциями. Благодаря тому, что Git является распределённой системой контроля версий, резервную копию локального хранилища можно сделать простым копированием или архивацией. Работа пользователя со своей веткой начинается с проверки и получения изменений из центрального репозитория. Затем можно вносить изменения в локальном дереве и/или ветке. После завершения внесения какого-то изменения в файлы и/или каталоги проекта необходимо разместить их в центральном репозитории. Для этого необходимо проверить, какие файлы изменились к текущему моменту.

# Выполнение лабораторной работы

1. Настройка github

Сначала создаю учётную запись на сайте https://github.com/, заполняю основные данные (рис. [-@fig:001]).

![Создание профиля на github](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/1.png){#fig:001 width=70%}

2. Базовая настройка git

Затем делаю предварительную конфигурацию git, открываю терминал и ввожу
команды, указав свое имя и email (рис. [-@fig:002]).

![Предварительная конфигурация git](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/2.png){#fig:002 width=70%}

Следующим шагом настраиваю utf-8 в выводе сообщений git (рис. [-@fig:003]).

![Настройка кодировки вывода в консоль](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/3.png){#fig:003 width=70%}

Далее задаю имя master для начальной ветки (рис. [-@fig:004]).

![Имя начальной ветки](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/4.png){#fig:004 width=70%}

Затем задаю параметры autocrlf, чтобы в главном репозитории все переводы строк текстовых файлов были одинаковы, и safecrlf для предотвращения автозамены LF в CRLF (рис. [-@fig:005]-[-@fig:006]).

![Параметр autocrlf](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/5.png){#fig:005 width=70%}

![Параметр safecrlf](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/6.png){#fig:006 width=70%}

3. Создание SSH ключа

Для последующей идентификации на сервере репозиториев генерирую пару ключей (приватный и открытый) (рис. [-@fig:007]).

![Генерация ssh-ключа](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/7.png){#fig:007 width=70%}

Далее загружаю сгенерённый открытый ключ. Для этого захожу на сайт http://github.org/ под своей учётной записью и перехожу в меню Settings. После этого выбираю в боковом меню SSH and GPG keys и нажимаю кнопку New SSH key. Скопировав из локальной консоли ключ в буфер обмена, вставляю ключ в
появившееся на сайте поле и задаю ключу имя key1 (рис. [-@fig:008]-[-@fig:009]).

![Генерация ssh-ключа](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/8.png){#fig:008 width=70%}

![Ключ в профиле на github](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/9.png){#fig:009 width=70%}

4. Создание рабочего пространства и репозитория курса на основе шаблона

Открываю терминал и создаю каталог для 2024–2025 учебного года и предмета «Архитектура компьютера», с помощью ls проверяю выполнение команды (рис. [-@fig:010]).

![Создание каталога «Архитектура компьютера»](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/10.png){#fig:010 width=70%}

5. Создание репозитория курса на основе шаблона

Перехожу на станицу репозитория с шаблоном курса https://github.com/yamadharma/cour se-directory-student-template (рис. [-@fig:011]).

![Шаблон курса](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/11.png){#fig:011 width=70%}

В открывшемся окне задаю имя репозитория study_2024–2025_arh-pc и создаю репозиторий (рис. [-@fig:012]).

![Создание репозитория](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/12.png){#fig:012 width=70%}

Затем открываю терминал, перехожу в каталог курса и клонирую созданный репозиторий (рис. [-@fig:013]), перед этим скопировав ссылку для клонирования на странице созданного репозитория (рис. [-@fig:014]).

![Клонирование репозитория](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/13.png){#fig:013 width=70%}

![Ссылка для клонирования](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/14.png){#fig:014 width=70%}

6. Настройка каталога курса

Перехожу в каталог курса и удаляю лишние файлы (рис. [-@fig:015]).

![Удаление файла package.json](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/15.png){#fig:015 width=70%}

Создаю необходимые каталоги (рис. [-@fig:016]).

![Создание каталогов](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/16.png){#fig:016 width=70%}


Затем отправляю файлы на сервер (рис. [-@fig:017]).

![Отправление файлов на сервер](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/17.png){#fig:017 width=70%}

Далее убеждаюсь в правильности создания иерархии рабочего пространства на странице github.

7. Выполнение заданий для самостоятельной работы

Перехожу в директорию labs/lab02 с помощью cd. Создаю в каталоге файл для отчета по второй лабораторной работе, проверяю наличие файла (рис. [-@fig:018]).

![Создание файла с отчетом](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/18.png){#fig:018 width=70%}

Копирую отчеты по выполнению предыдущих лабораторных работ в соответствующие каталоги созданного рабочего пространства и проверяю с помощью команды ls (рис. [-@fig:019]).

![Отчеты по лабораторным работам](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/19.png){#fig:019 width=70%}

Загружаю файл с отчетом по предыдущей лабораторной работе на github (рис. [-@fig:020]).

![Загрузка отчета на гитхаб](/afs/.dk.sci.pfu.edu.ru/home/a/e/aesavenkova/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab02/report/image/20.png){#fig:020 width=70%}

# Выводы

В ходе данной лабораторной работы я изучила идеологию и применение средств
контроля версий и приобрела практические навыки по работе с системой git.
