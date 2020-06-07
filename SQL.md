




## SQL 

Statement  + clases   + action
the end of the line is with ;

####SELECT
```
SELECT fieldName1, FieldName2 , * from tableName    
```
wild card  *
some information 

### WHERE
```
SELECT fieldName1, FieldName2 , * from tableName   
WHERE fileldNameX = ' ';
```
#### AND
```
SELECT	first_name, last_name 
FROM	people 
WHERE	first_name = 'Jack'
	AND
	last_name = 'Dean';
```
* IS  _or_ = 
* IS NOT _or_ !=

#### LIKE
to use a wild card in a field. with  %
```
WHERE fieldName LIKE 'letter%'
```
#### LIMIT and OFFSET
the max responce of responces.
```
LIMIT n OFFSET m;
```

#### ORDER BY
Arrange the data
```
ORDER BY fieldName DESC, fieldName2 ASC;
```
ASC -  Ascending
DESC - Desecrating 

#### LENGTH

size of field
````
SELECT LENGTH(fieldName) FROM tableName
~~~

####DISTINCT
Unique fields
````
SELECT DISTINCT(fieldName) FROM tableName
~~~
#### COUNT
````
Number of field
SELECT COUNT(*) FROM tableName
~~~


### JOIN
```
SELECT	first_name, state
FROM	people
JOIN	states
ON 		people.state = states.state_abbrev;
```

### RIGHT JOIN and LEFT JOIN
Joins data base and returns a table with  null were value is missing (left or right )
```
SELECT		first_name, state
FROM		people
LEFT JOIN	states
ON 			people.state = states.state_abbrev;
```

FULL OUTER JOIN -  shows both result 

#### GROUP BY
```
SELECT people.first_name,people.state, COUNT(people.state)
FROM people
GROUP BY people.state
ORDER BY COUNT(people.state) ASC;
```

#### SQL Data Types

* Binary
	*	BINARY
	*	BINARY LARGE OBJECT
	*	BINARY VARYING
* Date/Time
	* DATA	
	* INTERVAL
	* TIME
	* TIMESTAMP
* Numbers
	* BIGINT
	* DECIMAL
	* DOUBLE PRECISION
	* FLOAT
	* INTEGER
	* NUBERIC
	* SMALLINT
	* REAL
* Text
	* CHARACTER
	* CHARACTER LARGE OBJECT
	* VARCHAR
	* NCHAR
	* NCHAR VARYING
* Other
	* BOOLEAN

Null is a special - not 0, 1 

#### Number function
MIN, MAX, SUM
####String function
LOWER
UPPER
SUBSTR (st1, st2, strat, end)
REPLACE (st1, replaceString, withString)
#### SELECT -2 

Get a list of all people that score the MAX on the quiz
```
SELECT people.first_name, people.last_name , people.quiz_points
FROM people
WHERE people.quiz_points = (SELECT MAX(people,quiz_points FROM people);
```

#### Change var type
CAST ( var as varType)

#### INSERT
```
INSERT INTO tableNAme (field1, field2) 
VALUE (value1a, value2a), (value1b, value2b);
```

#### UPDATE
```
UPDATE tableNAme SET field1 = value1, field2 = value2,
WHERE condition;
```

#### DELETE
```
DELETE FROM tableNAme WHERE condition;
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1MDUyNTU0Ml19
-->