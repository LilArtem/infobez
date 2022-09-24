---
# Front matter
lang: ru-Ru
title: "Лабораторная работа №3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
author: "Смирнов Артем Александрович"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: xelatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Выполнение лабораторной работы

1. В установленной при выполнении предыдущей лабораторной работы операционной системе создам учётную запись пользователя guest (использую учётную запись администратора).

1. Задам пароль для пользователя guest (использую учётную запись администратора): passwd guest.

   Пользователь создан в прошлой лабораторной работе.
   
   ![guest](image/1.png){#fig:001}

​       

3. Аналогично создам второго пользователя guest2.

![guest2](image/2.png){#fig:002}

4. Добавим пользователя guest2 в группу guest: gpasswd -a guest2 guest

   ![группа guest](image/3.png){#fig:003}

5. Осуществите вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли. 

   ![две консоли](image/4.png){#fig:004}

6. Для обоих пользователей командой pwd определите директорию, в которой вы находитесь. Сравните её с приглашениями командной строки. 

   ![pwd guest1](image/5.png){#fig:005}

   ![pwd guest2](image/6.png){#fig:006}

7. Уточните имя вашего пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. Определите командами groups guest и groups guest2, в какие группы входят пользователи guest и guest2. Сравните вывод команды groups с выводом команд id -Gn и id -G. 

   ![whoami guest](image/7.png){#fig:007}

   ![groups guest](image/8.png){#fig:008}

   ![whoami guest2](image/9.png){#fig:009}

   ![groups guest2](image/10.png){#fig:010}

   Сравню вывод команды groups с выводом команд id -Gn и id -G.
   Первая команда выводит на экран группы пользователя, но без уточнения к
   какому пользователю относятся группы, т.к. команды работаю только для
   пользователя, через которого открыта консоль. Вторая команда выводи код группы
   пользователя.

   ![id -Gn](image/11.png){#fig:011}

   ![id -Gn](image/12.png){#fig:012}

   

8. Сравните полученную информацию с содержимым файла /etc/group. Просмотрите файл командой cat /etc/group.

   Для guest:

   ![1](image/13.png){#fig:013}

   ![2](image/14.png){#fig:014}

   

   Для guest2:

   ![1](image/15.png){#fig:016}

   ![2](image/16.png){#fig:017}

9. От имени пользователя guest2 выполните регистрацию пользователя guest2 в группе guest командой newgrp guest. 

   ![Регистрация](image/17.png){#fig:019}

10. От имени пользователя guest измените права директории /home/guest, разрешив все действия для пользователей группы: chmod g+rwx /home/guest.

     ![chmod g+rwx /home/guest](image/18.png){#fig:020}

11. От имени пользователя guest снимите с директории /home/guest/dir1 все атрибуты командой chmod 000 dirl и проверьте правильность снятия атрибутов. 

    ![chmod 000 dirl](image/19.png){#fig:021}

12. Меняя атрибуты у директории dir1 и файла file1 от имени пользователя guest и делая проверку от пользователя guest2, заполните табл. 3.1, определив опытным путём, какие операции разрешены, а какие нет. Для этого создам скрипты и перенесу их директории guest и guest2.

Полученная таблица не совпадает с таблицей из прошлой
лабораторной работы, поскольку члены группы не имеют права изменять
атрибуты файла. Для остальных операций члену группы нужны такие же
права, как у владельца.

![1](image/23.png){#fig:023}

![2](image/24.png){#fig:024}

![3](image/25.png){#fig:025}

![4](image/26.png){#fig:026}

![5](image/27.png){#fig:027}

![6](image/28.png){#fig:028}

На основании заполненной таблицы выше определю те или иные минимально
необходимые права для выполнения пользователем guest2 операций внутри
директории dir1 и заполню таблицу:

![1](image/29.png){#fig:029}

### Вывод

В ходе данной лабораторной работы мы получили практические навыки работы в консоли с атрибутами файлов для групп пользователей.


# Список литературы

- <code>[Кулябов Д. С., Королькова А. В., Геворкян М. Н Лабораторная работа №3](https://esystem.rudn.ru/pluginfile.php/1651749/mod_resource/content/4/003-lab_discret_2users.pdf)</code>