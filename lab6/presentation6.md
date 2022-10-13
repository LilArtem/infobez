---
marp: true
paginate : true
---
<style>
h1 { 
    font-size: 60px;
    color: Black;
    text-align: center;
    }       
h2 { 
    font-size: 30px;
    color: Black;
    position: relative;
    left: -2.5em;
    top: 8em;
    }

h3 { 
    font-size: 30px;
    color: Black;
    position: relative;
    left: -2.5em;
    top: 7em;
    }

section.titleslide1 h4 {
    font-size: 40px;
    color: Black;
    position: relative;
    left: 0em;
    bottom: 2em;    
}

section.titleslide2 h4 {
    font-size: 40px;
    color: Black;
    position: relative;
    left: 0em;
    bottom: 5.3em;    
}

section.titleslide3 h4 {
    font-size: 40px;
    color: Black;
    position: relative;
    left: 0em;
    bottom: 0em;    
}

section.titleslide4 h4 {
    font-size: 40px;
    color: Black;
    position: relative;
    left: 0em;
    bottom: 0em;    
}

section.titleslide5 h4 {
    font-size: 40px;
    color: Black;
    position: relative;
    left: 0em;
    bottom: -1em;    
}

</style>

# Лабораторная работа №5
## Artem Smirnov
### RUDN University, 2022 Moscow, Russia

---
<!--_class: titleslide2 -->
#### Цель выполнения лабораторной работы
Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

---
<!--_class: titleslide2 -->
#### SetGID бит
Благодаря SetUID-бит, то программе временно предоставляются
права владельца файла (суперпользователя). Поэтому программа может прочитать
файл с правами доступа только для владельца суперпользователя.

---
<!--_class: titleslide1 -->
#### Sticky-бит

Мне удалось удалить файл от имени пользователя, не являющегося его владельцем.
Это связано с тем, что Sticky-bit позволяет защищать файлы от случайного удаления, когда несколько пользователей имеют права на запись в один и тот же каталог. Если у файла атрибут t стоит, значит пользователь может удалить файл, только если он является пользователем-владельцем файла или каталога, в котором содержится файл. Если же этот атрибут не установлен, то удалить файл могут все пользователи, которым позволено удалять файлы из каталога.

---


<!--_class: titleslide1 -->
#### Вывод

В ходе данной лабораторной работы я изучила механизмы изменения
идентификаторов, применения SetUID-, SetGID- и Sticky-битов. Рассмотрела работу
механизма смены идентификатора процессов пользователей, а также влияние бита
Sticky на запись и удаление файлов.

---
# Спасибо за внимание