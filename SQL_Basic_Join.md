
## Basic Join

### [Asian Populations](https://www.hackerrank.com/challenges/asian-population/problem)

Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.


#### Solution
```sql
SELECT SUM(CITY.POPULATION) 
FROM CITY, COUNTRY
WHERE CITY.COUNTRYCODE = COUNTRY.CODE 
AND COUNTRY.CONTINENT = 'Asia';
```

### [African Cities](https://www.hackerrank.com/challenges/african-cities/problem?h_r=next-challenge&h_v=zen)

Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

#### Solution
```sql
SELECT CITY.NAME
FROM CITY, COUNTRY
WHERE CITY.COUNTRYCODE = COUNTRY.CODE AND COUNTRY.CONTINENT = "Africa";
```

### [Average Population of Each Continent](https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?h_r=next-challenge&h_v=zen)

Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

#### Solution
```sql
SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION))
FROM CITY INNER JOIN COUNTRY
ON CITY.COUNTRYCODE = COUNTRY.CODE
GROUP BY COUNTRY.CONTINENT;
```

### [The Report](https://www.hackerrank.com/challenges/the-report/problem)

You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.
    
Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.

#### Solution
```sql
SELECT IF (S.Marks < 70, 'NULL', S.Name), G.Grade, S.Marks
FROM Students AS S, Grades AS G
WHERE S.Marks BETWEEN G.Min_Mark AND G.Max_Mark
ORDER BY G.GRADE DESC, S.NAME;
```


```python

```
