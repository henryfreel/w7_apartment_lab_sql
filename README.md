# Apartment Lab (SQL Practice)

For these challenges, you'll be working with two tables, `owners` and `properties`. Keep this relationship in mind when designing your schema: **one owner can have many properties**.

## Getting Started

1. Create a database called `apartmentlab`.
2. Using the `apartmentlab` database, create two tables, one for `owners` and one for `properties`. See the next section for schema specs.

## Schema

* The `owners` table should consist of:
	* **id** (this should be the primary key as well as a unique number that increments automatically)
	* **name**
	* **age**

* The `properties` table should consist of:
	* **id** (this should be the primary key as well as a unique number that increments automatically)
	* **name**
	* **num_units**
	* **owner_id** (this should be a foreign key that references the owners table)

## Challenges

In a <a href="https://help.github.com/articles/markdown-basics" target="_blank">markdown</a> file, write the SQL statements required to solve the following tasks. Make sure to test your queries in the `psql` terminal! Remember you can type `\?` in the `psql` terminal for a list of commands.

1. Show all the psql users. (**Hint:** Look for a command to show `roles`)
	```
	\du
	```
2. Show all the tables in your `apartmentlab` database.
	```
	\dt
	```
3. Show all the data in the `owners` table.
	```
	SELECT * FROM owners
	```
4. Add three owners: Donald (age 56), Elaine (age 24), and Emma (age 36).
	```
	INSERT INTO owners (name, age)
		VALUES
		('Donald', 56),
		('Elaine', 24),
		('Emma', 36);
	```
5. Show the names of all owners.
	```
	SELECT name FROM owners;
	```
6. Show the ages of all of the owners in ascending order.
	```
	SELECT age FROM owners ORDER BY age ASC;
	```
7. Show the name of an owner whose name is Donald.
	```
	SELECT * FROM owners
		WHERE name = 'Donald';
	```
8. Show the age of all owners who are older than 30.
	```
	SELECT age  FROM owners
		WHERE age > 30;
	```
9. Show the name of all owners whose name starts with an "E".
	```
	SELECT name FROM owners
		WHERE name LIKE 'E%';
	```
10. Add an owner named John who is 33 years old.
	```
	INSERT INTO owners
		(name, age)
		VALUES
		('John', 33);
	```
11. Add an owner named Jane who is 43 years old.
	```
	INSERT INTO owners
		(name, age)
		VALUES
		('Jane', 43);
	```
12. Change Jane's age to 30.
	```
	UPDATE owners
		SET age = 30
		WHERE name = 'Jane';
	```
13. Change Jane's name to Janet.
	```
	UPDATE owners
		SET name = 'Janet'
		WHERE name = 'Jane';
	```
14. Delete the owner named Janet.
	```
	DELETE FROM owners
		WHERE name <> 'Janet';
	```
15. Add a property named Archstone that has 20 units.
	```
	INSERT INTO properties
		(name, num_units)
		VALUES
		('Archstone', 20);
	```
16. Add two more properties with names and number of units of your choice.
	```
	INSERT INTO properties
	(name, num_units)
	VALUES
	('Collingwood', 10),
	('Florida Street', 1);
	```
17. Show all of the properties in alphabetical order that are not named Archstone.
18. Count the total number of rows in the properties table.
19. Show the highest age of all the owners.
20. Show the names of the first three owners in your owners table.
21. Use a `FULL OUTER JOIN` to show all of the information from the owners table and the properties table.
22. Update at least one of your properties to belong to the owner with id 1.
23. Use an `INNER JOIN` to show all of the owners with associated properties.
24. Use a `CROSS JOIN` to show all possible combinations of owners and properties.

## Stretch Challenges

**Note:** You may need to research documentation for these challenges.

1. In the `properties` table, change the name of the column `name` to `property_name`.
2. Count the total number of properties where the `owner_id` is between 1 and 3.
