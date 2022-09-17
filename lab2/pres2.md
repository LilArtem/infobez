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

# Лабораторная работа №2
## Смирнов Артем
### Российский университет дружбы народов, 2022 Москва, Россия

---
<!--_class: titleslide2 -->
#### Цель выполнения лабораторной работы
Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

---
<!--_class: titleslide2 -->

#### Установленные права и разрешенные действия
# ![ls -l /home/](image/13.png)


---
<!--_class: titleslide2 -->
#### Установленные права и разрешенные действия
# ![ls -l /home/](image/14.png)


---
<!--_class: titleslide2 -->
##### Минимальные права для совершения операций
| Операция               | Мин. права на дир. | Мин. права на файл |
| ---------------------- | ------------------------------- | ------------------------- |
| Создание файла         | d-wx------ (300)                | --------- (000)           |
| Удаление файла         | d-wx------ (300)                | --------- (000)           |
| Чтение файла           | d--x------ (100)                | r-------- (400)           |
| Запись в файл          | d--x------ (100)                | -w------- (200)           |
| Переименование файла   | d-wx------ (300)                | --------- (000)           |
| Создание поддиректории | d-wx------ (300)                | --------- (000)           |
| Удаление поддиректории | d-wx------ (300)                | --------- (000)           |


---

<!--_class: titleslide2 -->
#### Вывод

В ходе данной лабораторной работы мы получили практические навыки работы в консоли с атрибутами файлов, закрепили теоретические основы разграничения доступа на базе ОС Linux.

