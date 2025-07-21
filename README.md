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

[(Какие компании совершали перелеты на Boeing)](https://sql-academy.org/ru/trainer/tasks/6)

```mysql
SELECT DISTINCT Company.name
FROM Trip, Company
WHERE Trip.company = Company.id AND
Trip.plane = 'Boeing'
```

[(Вывести все названия самолётов, на которых можно улететь в Москву (Moscow))](https://sql-academy.org/ru/trainer/tasks/7)

```mysql
SELECT DISTINCT plane
FROM Trip
WHERE town_to = 'Moscow'
```

[(В какие города можно улететь из Парижа (Paris) и сколько времени это займёт?)](https://sql-academy.org/ru/trainer/tasks/8)

```mysql
SELECT town_to,
       DATE_FORMAT(TIMEDIFF(time_in, time_out), '%H:%i:%s') AS flight_time 
FROM Trip
WHERE town_from = 'Paris'
```

[(Какие компании организуют перелеты из Владивостока (Vladivostok)?)](https://sql-academy.org/ru/trainer/tasks/9)

```mysql
SELECT DISTINCT Company.name
FROM Trip, Company
WHERE Trip.company = Company.id AND
town_to = 'Vladivostok'
```

[(В какие города летал Bruce Willis)](https://sql-academy.org/ru/trainer/tasks/14)

```mysql
SELECT town_to FROM Trip, Pass_in_trip, Passenger
WHERE Trip.id = Pass_in_trip.trip AND
Passenger.id = Pass_in_trip.passenger AND
Passenger.name = 'Bruce Willis'
```

[(Выведите идентификатор пассажира Стив Мартин (Steve Martin) и дату и время его прилёта в Лондон (London))](https://sql-academy.org/ru/trainer/tasks/15)

```mysql
SELECT Passenger.id AS id, Trip.time_in
FROM Trip, Pass_in_trip, Passenger
WHERE Trip.id = Pass_in_trip.trip AND
Passenger.id = Pass_in_trip.passenger AND
Passenger.name = 'Steve Martin' AND
Trip.town_to = "London"
```

[(Определить, кто из членов семьи покупал картошку (potato))](https://sql-academy.org/ru/trainer/tasks/19)

```mysql
SELECT DISTINCT status
FROM FamilyMembers, Payments, Goods
WHERE FamilyMembers.member_id = Payments.family_member AND
Goods.good_id = Payments.good AND 
good_name = 'potato'
```

[(Найти имена всех матерей (mother))](https://sql-academy.org/ru/trainer/tasks/22)

```mysql
SELECT  member_name
FROM FamilyMembers
WHERE status = "mother"
```

[(Выведите фамилию, имя и дату рождения студентов, кто был рожден в мае)](https://sql-academy.org/ru/trainer/tasks/75)
```mysql
SELECT last_name, first_name, birthday
FROM Student
WHERE MONTH(birthday) = 05
```

[(Посчитай доход с женской аудитории)](https://sql-academy.org/ru/trainer/tasks/99)

```mysql
SELECT SUM(price*items) AS income_from_female
FROM Purchases
WHERE user_gender IN ('female', 'f')
```
