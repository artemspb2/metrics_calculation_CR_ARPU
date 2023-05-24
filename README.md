Итоговый проект курса "Аналитика данных" / The final project of the course "Data Analytics" (English comments are after Russian)

Задание выполнено в 3 файлах .ipynb + 2 презентациях PowerPoint

1 задание
first_task.ipynb 
New payment method

2 задание
SQLtask.ipynb
CR ARPU students AB test

3 задание
Auto_function_task3.ipynb

Описание задания:

Проект: вариант 2
Задание 1. A/B–тестирование
1.1 Условие

Одной из основных задач аналитика в нашей команде является корректное проведение экспериментов. Для этого мы применяем метод A/B–тестирования. В ходе тестирования одной гипотезы целевой группе была предложена новая механика оплаты услуг на сайте, у контрольной группы оставалась базовая механика. В качестве задания Вам необходимо проанализировать итоги эксперимента и сделать вывод, стоит ли запускать новую механику оплаты на всех пользователей.

1.2 Входные данные

В качестве входных данных Вы имеете 4 csv-файла:

groups.csv - файл с информацией о принадлежности пользователя к контрольной или экспериментальной группе (А – контроль, B – целевая группа) 
groups_add.csv - дополнительный файл с пользователями, который вам прислали спустя 2 дня после передачи данных
active_studs.csv - файл с информацией о пользователях, которые зашли на платформу в дни проведения эксперимента. 
checks.csv - файл с информацией об оплатах пользователей в дни проведения эксперимента. 
1.3 Вопросы

Предлагаем Вам ответить на следующие вопросы:

На какие метрики Вы смотрите в ходе анализа и почему?
Имеются ли различия в показателях и с чем они могут быть связаны?
Являются ли эти различия статистически значимыми?
Стоит ли запускать новую механику на всех пользователей?
Данный список вопросов не является обязательным, и Вы можете при своём ответе опираться на собственный план.

1.4 Требования к ответу

При выполнении тестового задания необходимо использовать язык программирования Python. 
В файле обязательно должны быть комментарии к тем действиям, которые Вы выполняете с данными. 
Файл должен представлять собой законченный отчёт с выводами, сделанными в ходе исследования.
Задание 2. SQL
2.1 Очень усердные ученики.

2.1.1 Условие

Образовательные курсы состоят из различных уроков, каждый из которых состоит из нескольких маленьких заданий. Каждое такое маленькое задание называется "горошиной".

Назовём очень усердным учеником того пользователя, который хотя бы раз за текущий месяц правильно решил 20 горошин.

2.1.2 Задача

Дана таблица default.peas:

Название атрибута	Тип атрибута	Смысловое значение
st_id	int	ID ученика
timest	timestamp	Время решения карточки
correct	bool	Правильно ли решена горошина?
subject	text	Дисциплина, в которой находится горошина


Необходимо написать оптимальный запрос, который даст информацию о количестве очень усердных студентов.NB! Под усердным студентом мы понимаем студента, который правильно решил 20 задач за текущий месяц.

2.2 Оптимизация воронки

2.2.1 Условие

Образовательная платформа предлагает пройти студентам курсы по модели trial: студент может решить бесплатно лишь 30 горошин в день. Для неограниченного количества заданий в определенной дисциплине студенту необходимо приобрести полный доступ. Команда провела эксперимент, где был протестирован новый экран оплаты.

2.2.2 Задача

Дана таблицы: default.peas (см. выше), default.studs:

Название атрибута	Тип атрибута	Смысловое значение
st_id	int	 ID ученика
test_grp	text	 Метка ученика в данном эксперименте
и default.final_project_check:

Название атрибута	Тип атрибута	Смысловое значение
st_id	int 	ID ученика
sale_time	timestamp	Время покупки
money	int	Цена, по которой приобрели данный курс
subject	text 	
Необходимо в одном запросе выгрузить следующую информацию о группах пользователей:

ARPU 
ARPAU 
CR в покупку 
СR активного пользователя в покупку 
CR пользователя из активности по математике (subject = ’math’) в покупку курса по математике
ARPU считается относительно всех пользователей, попавших в группы.

Активным считается пользователь, за все время решивший больше 10 задач правильно в любых дисциплинах.

Активным по математике считается пользователь, за все время решивший 2 или больше задач правильно по математике.

Все данные находятся в табличном виде в ClickHouse
Задание 3. Python
3.1 Задача

Реализуйте функцию, которая будет автоматически подгружать информацию из дополнительного файла groups_add.csv (заголовки могут отличаться) и на основании дополнительных параметров пересчитывать метрики.
Реализуйте функцию, которая будет строить графики по получаемым метрикам.


The final project of the course "Data Analytics"

Assignment completed in 3 .ipynb files + 2 PowerPoint presentations

1 task
first_task.ipynb 
New payment method

2 task
SQLtask.ipynb
CR ARPU students AB test

3 task
Auto_function_task3.ipynb

Task Description:

Project: option 2.
Assignment 1: A/B Testing
1.1 Prerequisite

One of the main tasks of an analyst on our team is to conduct experiments correctly. To do this we use the A/B testing method. During one hypothesis testing, the target group was offered a new payment mechanics on the site, while the control group was left with the basic mechanics. As a task you need to analyze the results of the experiment and conclude whether to run the new payment mechanics on all users.

1.2 Input data

As input data you have 4 csv files:

groups.csv - file with information about user's membership in control or experimental group (A - control, B - target group) 
groups_add.csv - an additional file with users that was sent to you 2 days after the data transfer
active_studs.csv - file with information about users who have logged on to the platform during the experiment. 
checks.csv - file with information about users' payments on the experiment days. 
1.3 Questions

We suggest you answer the following questions:

What metrics are you looking at in your analysis and why?
Are there differences in the metrics and what might they be related to?
Are the differences statistically significant?
Is it worth running the new mechanics on all users?
This list of questions is not required, and you can base your answer on your own plan.

1.4 Answer Requirements

You must use the Python programming language to complete the test assignment. 
The file must contain comments on what you do with the data. 
The file must be a complete report with the conclusions drawn from the research.
Task 2. SQL
2.1 Very hard students.

2.1.1 Condition.

Educational courses consist of various lessons, each of which consists of several small assignments. Each such small assignment is called a "pea."

Let's call a user who solved 20 peas correctly at least once during the current month a very hard learner.

2.1.2 Task.

A default.peas table is given:

Attribute name Attribute type Meaning
st_id int student ID
timest timestamp Time of solving the card
correct bool Is the pea solved correctly?
subject text Discipline the pea is in


You need to write an optimal query that will give you information about the number of very hard students. NB! By hard student we mean a student who solved 20 problems correctly in the current month.

2.2 Optimizing the Funnel

2.2.1 Condition.

The educational platform offers students courses based on the trial model: a student can solve only 30 peas a day for free. For an unlimited number of assignments in a particular discipline, the student must purchase full access. The team conducted an experiment where the new payment screen was tested.

2.2.2 Task.

Given tables: default.peas (see above), default.studs:

Attribute name Attribute type Meaning
st_id int student ID
test_grp text The label of the student in this experiment
and default.final_project_check:

Attribute name Attribute type Meaningful value
st_id int student ID
sale_time timestamp Time of purchase
money int price at which the course was purchased
subject text 	
You need to upload the following information about user groups in one request

ARPU 
ARPAU 
CR into purchase 
CR of the active user in a purchase 
CR of the user from the math activity (subject = 'math') into the purchase of the math course
ARPU is counted relative to all users in the groups.

A user who solved more than 10 problems correctly in any discipline at all times is considered active.

Active in Math is a user who solved 2 or more math problems correctly over time.

All data is in tabular form in ClickHouse.
Problem 3: Python
3.1 Task.

Implement a function that will automatically load information from additional groups_add.csv file (headings may vary) and recalculate metrics based on additional parameters.
Implement a function that will plot the metrics it receives.
