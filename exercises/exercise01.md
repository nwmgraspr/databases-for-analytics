# Exercise 01: World Database SQL Practice

- Name: Ralph Massaquoi
- Course: Database for Analytics
- Module: 1
- Database Used: World Database

---

See:

[MySQL: Setting Up the World Database](https://dev.mysql.com/doc/world-setup/en/)

---

## Instructions

- Answer each question below.
- All SQL commands **must be executed** against the World database.
- For each SQL command:
  - Include the SQL in a fenced code block
  - Include a **screenshot** showing the command and results
- Store screenshots in the `screenshots/` folder and embed them below each answer.

---

## Question 1

**Compare and contrast the data types used for:**
- country.Populate uses integer data type, while country.LifeExpectancy uses decimal data type.

Why were these data types selected?

### Answer

- `country.Population`- population is an integer because it represents a count of people and it is represented by a whole number.
- `country.LifeExpectancy`- life expectancy is a decimal because, it is an estimate and can therefore be represented by a decimal number.


### Screenshot

_Show the table structure or DESCRIBE output._

```sql
DESCRIBE country;
```
![Q1 Screenshot](screenshots/q1_datatypes.png)

---

## Question 2

**What is the data type of `country.IndepYear`?**
- The country.IndepYear uses the SMALLINT data type.
Why do you think this data type was selected?
### Answer
-This data type was selected because an independence year is a whole number without decimal places. It stores the range of years needed while using less storage than regular INT.

### Screenshot

```sql
DESCRIBE country;
```

![Q2 Screenshot](screenshots/q2_indepyear.png)

---

## Question 3

**Make a case for a different data type for `country.IndepYear`.**
Explain why your proposed data type might be better in some situations.

### Answer

_Year can be used as another data type for country.IndepYear because it will indicates that the column stores a calendar year rather than a number. This can help to valid year values.

---

## Question 4

Write a SQL command to **list the names of all cities in alphabetical order**.

### SQL

```sql
SELECT Name
FROM city
ORDER BY Name;
```

### Screenshot

![Q4 Screenshot](screenshots/q4_cities_sorted.png)

---

## Question 5

Write a SQL command to
**list all forms of government from the `country` table**,
showing **each only once**, sorted alphabetically.

### SQL

```sql
SELECT DISTINCT GovernmentForm
FROM country
ORDER BY GovernmentForm;
```

### Screenshot

![Q5 Screenshot](screenshots/q5_government_forms.png)

---

## Question 6

Write a SQL command to **list all countries in the `Oceania` continent**.

### SQL

```sql
SELECT Name
FROM country
WHERE Continent = 'Oceania';
```

### Screenshot

![Q6 Screenshot](screenshots/q6_oceania.png)

---

## Question 7

Write a SQL command to **list the names and country code of all cities**.

### SQL

```sql
SELECT Name, CountryCode
FROM city;
```

### Screenshot

![Q7 Screenshot](screenshots/q7_city_countrycode.png)

---

## Question 8

Write a SQL command to **update the city named `"Nashville-Davidson"` to `"Nashville"`**.

### SQL

```sql
UPDATE city
SET Name = 'Nashville'
WHERE Name = 'Nashville-Davidson';
```

### Screenshot

![Q8 Screenshot](screenshots/q8_update_city.png)

---

## Question 9

Write a SQL command to **insert a new country named `"Narnia"`**
with a country code of `"NAR"`.
Use reasonable values for the remaining columns.

### SQL

```sql
INSERT INTO country (
    Code, Name, Continent, Region, SurfaceArea, IndepYear,
    Population, LifeExpectancy, GNP, GNPOld, LocalName,
    GovernmentForm, HeadOfState, Capital, Code2
)
VALUES (
    'NAR', 'Narnia', 'Europe', 'Fantasy', 100000.00, NULL,
    1000000, 75.0, 5000.00, NULL, 'Narnia',
    'Monarchy', 'King Tirian', NULL, 'NA'
);
```

### Screenshot

![Q9 Screenshot](screenshots/q9_insert_narnia.png)

---

## Question 10

Write a SQL command to **delete the country with the country code `"NAR"`**.

### SQL

```sql
DELETE FROM country
WHERE Code = 'NAR';
```

### Screenshot

![Q10 Screenshot](screenshots/q10_delete_narnia.png)
