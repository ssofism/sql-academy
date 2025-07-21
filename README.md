## sql-academy

[(Вывести имена всех людей, которые есть в базе данных авиакомпаний)](https://sql-academy.org/ru/trainer/tasks/1)

```mysql
SELECT name
FROM passenger;
```
[(Вывести названия всеx авиакомпаний)](https://sql-academy.org/ru/trainer/tasks/2)

```mysql
SELECT name
FROM Company
```

[(Вывести все рейсы, совершенные из Москвы)](https://sql-academy.org/ru/trainer/tasks/3)

```mysql
SELECT*
FROM Trip
WHERE town_from = 'Moscow'
```

[{Вывести имена людей, которые заканчиваются на "man")](https://sql-academy.org/ru/trainer/tasks/4)

```mysql
SELECT name
FROM Passenger
WHERE name LIKE  '%man'
```

[(Вывести количество рейсов, совершенных на TU-134)](https://sql-academy.org/ru/trainer/tasks/5)

```mysql
SELECT COUNT(plane) AS count
FROM Trip 
WHERE plae = "TU-134"
```
