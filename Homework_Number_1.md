# Домашнее задание №1

*	создать новый проект в Google Cloud Platform, Яндекс облако или на любых ВМ, докере
*	далее создать инстанс виртуальной машины с дефолтными параметрами
*	добавить свой ssh ключ в metadata ВМ
*	зайти удаленным ssh (первая сессия), не забывайте про ssh-add
*	поставить PostgreSQL
*	зайти вторым ssh (вторая сессия)
*	запустить везде psql из под пользователя postgres
*	выключить auto commit

Создана виртуальная машина c Ubuntu 22.04 LTS на Яндекс Облаке.
![Альт-текст](Images/HW1/1.png)

В Ubuntu cозданы два пользователя: sanni и testuser. Для каждого сгенерированы пары ключей для подключения по ssh.
![Альт-текст](Images/HW1/2.png)

Подключение к ВМ по ssh идёт через программу Putty.
![Альт-текст](Images/HW1/3.png)

![Альт-текст](Images/HW1/4.png)

Установлен PostgreSQL. 
Везде запущен psql из под пользователя postgres
![Альт-текст](Images/HW1/5.png)

![Альт-текст](Images/HW1/6.png)

*	выключить auto commit

С этим пунктом я немного повозился, просто командой в терминале мне не удалось отключить AUTOCOMMIT.
Пробовал команды:
set AUTOCOMMIT OFF;
\set AUTOCOMMIT OFF;
и их вариации, но они не срабатывали.
В итоге отключил через файл ~/.psqlrc, создав в нём запись:
![Альт-текст](Images/HW1/7.png)
Просьба научить как это делается. И какой командой в терминале можно увидеть статус у AUTOCOMMIT (ON или OFF)?

*	сделать

в первой сессии новую таблицу и наполнить ее данными create table persons(id serial, first_name text, second_name text); insert into persons(first_name, second_name) values('ivan', 'ivanov'); insert into persons(first_name, second_name) values('petr', 'petrov'); commit;
![Альт-текст](Images/HW1/8.png)

*	посмотреть текущий уровень изоляции: show transaction isolation level
![Альт-текст](Images/HW1/9.png)


![Альт-текст](Images/HW1/10.png)
![Альт-текст](Images/HW1/11.png)
![Альт-текст](Images/HW1/12.png)
![Альт-текст](Images/HW1/13.png)
![Альт-текст](Images/HW1/14.png)
![Альт-текст](Images/HW1/15.png)
![Альт-текст](Images/HW1/16.png)
![Альт-текст](Images/HW1/17.png)
![Альт-текст](Images/HW1/18.png)
![Альт-текст](Images/HW1/19.png)
