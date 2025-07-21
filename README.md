## sql-academy

1. [(Вывести имена всех людей, которые есть в базе данных авиакомпаний)](https://sql-academy.org/ru/trainer/tasks/1)

```mysql
SELECT name
FROM passenger;
```

2. Вывести названия всеx авиакомпаний
-SELECT name
-FROM Company

3. Вывести все рейсы, совершенные из Москвы
-SELECT*
-FROM Trip
-WHERE town_from = 'Moscow'

4. Вывести имена людей, которые заканчиваются на "man"
-SELECT name
-FROM Passenger
-WHERE name LIKE  '%man'

5. Вывести количество рейсов, совершенных на TU-134
-SELECT COUNT(plane) AS count
-FROM Trip 
-WHERE plae = "TU-134"
-ИЛИ
-SELECT COUNT(*) AS count 
-FROM Trip 
-WHERE plane = "TU-134"

6. Какие компании совершали перелеты на Boeing
SELECT DISTINCT Company.name
FROM Trip, Company 
WHERE Trip.company = Company.id AND
Trip.plane = 'Boeing'
ИЛИ
SELECT DISTINCT cp.name
FROM company cp
         JOIN trip tr ON cp.id = tr.company
WHERE plane = 'Boeing';

7. Вывести все названия самолётов, на которых можно улететь в Москву (Moscow)
SELECT DISTINCT plane
FROM Trip
WHERE town_to = 'Moscow'

8. В какие города можно улететь из Парижа (Paris) и сколько времени это займёт?
SELECT town_to,
DATE_FORMAT(TIMEDIFF(time_in, time_out), '%H:%i:%s') AS flight_time 
FROM Trip

9. Какие компании организуют перелеты из Владивостока (Vladivostok)?
SELECT DISTINCT Company.name
FROM Trip, Company
WHERE Trip.company = Company.id AND
town_to = 'Vladivostok'
WHERE town_from = 'Paris'

14. В какие города летал Bruce Willis
SELECT town_to
FROM Trip, Pass_in_trip, Passenger
WHERE Trip.id = Pass_in_trip.trip AND
Passenger.id = Pass_in_trip.passenger AND
Passenger.name = 'Bruce Willis'
