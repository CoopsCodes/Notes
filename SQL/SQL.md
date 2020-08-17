# Stuff

SQL is relational database, meaning all tables are related in some way. i.e a customer id number will relate to the customer id column in the orders table/

A semicolon must be used at the end of a query.

## Comments

To comment out a query line, preface a query with a double hyphen.

e.g. the **WHERE** line will be ignored

```
SELECT *
FROM customers
-- WHERE customer_id = 1
ORDER BY first_name
```

# Queries

### USE keyword

```
USE db_database;
```

Use indicates what database will be utilised.

### SELECT keyword

```
SELECT *
```

Used to select, the asterisk is an indicator of 'all'.

---

```
SELECT last_name, first_name
```

Instead of \* we can chose the columns and in the order to display them.

---

### FROM keyword

```
SELECT *
FROM customers
```

While **FROM** selects the table.

---

### WHERE keyword

```
SELECT *
FROM customers
WHERE customer_id = 1
```

**WHERE** is a filter clause, this filters to the customer with the ID equalling 1 in the customers table.

**WHERE** uses the comparison operators

```
> greater than
>= greater than or equal to
< less than
<=less than or equal to
!= or <> is not equal to
```

Filter by a state, if a table uses strings searches must be wrapped in quotations

```
SELECT *
FROM customers
WHERE state = 'VA'
```

Filter where a grade is higher than X

```
SELECT *
FROM students
WHERE points > 3000
```

Search by date, follows the American dateString of 'yyyy-mm-dd'

```
SELECT *
FROM customers
WHERE birthDate > '1985-12-31'
```

**AND**

```
SELECT *
FROM customers
WHERE birth_date > '1990-01-01' AND points > 1000
```

Using the **AND** keyword adds extra conditions to the filter to return the search if both are true.

**OR**

```
SELECT *
FROM customers
WHERE birth_date > '1990-01-01' OR points > 1000
```

Same with OR but will filter if one of the conditions are met rather than both

Filtering can be chained, beware of order of operations, AND is always evaluated first. Can use parenthesis like maths to change order of operation.

```
WHERE birth_date > '1990-01-01' OR points > 1000 AND state = 'WA'
```

In this equation **points > 1000 AND state = 'WA'** gets evaluated first!

**NOT**

```
WHERE NOT birth_date > '1990-01-01'
```

Negates and reverses the search by finding the people who are NOT greater then the birth date

**IN**
To search for multiple parameters the **IN** keyword can be used to shorten searches from

```
WHERE state = 'WA' AND state = 'NSW' AND state = 'VIC'
```

We use the IN keyword to include all the searches in one column

```
WHERE state IN ('WA', 'NSW', 'VIC')
```

**Between**
Used to filter by range

```
WHERE points BETWEEN 1000 AND 3000
```

Is a more efficient way of

```
WHERE points >= 1000 and points <= 3000
```

**LIKE**
Like is used as a regex to search for combinations, and is **NOT** case sensitive.

```
WHERE last_name LIKE 'B%'
```

Will search for a string that starts with **b** and is any length long.

```
WHERE last_name LIKE 'BERG%'
```

Will search for a string that starts with **berg** and is any length long

```
WHERE last_name LIKE '%y'
```

Will search for a string that ends in a **y** and is any length long

```
WHERE last_name LIKE '%y%'
```

Searches for a string with **y** in any location and and length long

```
WHERE last_name LIKE '_y'
```

Underscore indicates a length, this will search for a any string that is two letters in length and ends in **y**

---

### ORDER BY keyword

```
SELECT *
FROM customers
WHERE customer_id = 1
ORDER BY first_name
```

**ORDER BY** is a sort clause that will sort the order by the (first_name) column

---

### Arithmetic

```
SELECT last_name, first_name, points + 10
```

**Arithmetic** can be used to make adjustments, here the numerical column of _points_ would have 10 added to them.

Uses the standard formulas

```
+ addition
- subtraction
* multiplication
\ division
% (modulo) for remainder.
```

```
SELECT
	last_name,
	first_name,
	points * 10 + 100
FROM customers
```

If queries get too long, they can be placed on a new line a tab in.

Calculations work off the mathematical order of operation, not order of the equation unless using parentheses.

---

### Alias

```
SELECT
	last_name,
	first_name,
	points * 10 + 100 AS discount_value
FROM customers
```

By using the **AS** keyword the column title can be renamed for readability.

```
SELECT
	last_name AS 'Last Name',
	first_name,
FROM customers
```

If a space is required in the title it must be surrounded by single or double quotes

---

### Distinct

Used to display a distinct list without any duplicates

```
SELECT DISTINCT state
FROM customer
```

This will display all states but not repeat duplicates.

---
