## Listing databases
- \l or \list

<br/>

## Listing tables
- \dt

<br/>

## Listing users
- \du

<br/>

## Connecting to another database
- \connect {dbname}

<br/>

## Creating a table
```
Source: https://www.postgresqltutorial.com/postgresql-create-table/

CREATE TABLE table_name (
	column_name TYPE column_constraint,
	table_constraint table_constraint
) INHERITS existing_table_name;
```
Example:
```
CREATE TABLE account(
	user_id serial PRIMARY KEY,
	username VARCHAR (50) UNIQUE NOT NULL,
	password VARCHAR (50) NOT NULL,
	email VARCHAR (355) UNIQUE NOT NULL,
	created_on TIMESTAMP NOT NULL,
	last_login TIMESTAMP
);
```

<br/>

## Inserting a record
```
Source: https://www.postgresqltutorial.com/postgresql-insert/

INSERT INTO table(column1, column2, …)
VALUES
	(value1, value2, …);
```
Example:
```
INSERT INTO link (url, name)
VALUES
	('https://www.postgresqltutorial.com','PostgreSQL Tutorial');
```

<br/>

## Updating a record
```
Source: https://www.postgresqltutorial.com/postgresql-update/

UPDATE table_name
SET column1 = value1,
    column2 = value2,
    ...
WHERE condition;
```
Example:
```
UPDATE courses
SET published_date = '2020-08-01' 
WHERE course_id = 3;
```

<br/>

## Order by
```
Source: https://www.postgresqltutorial.com/postgresql-order-by/

SELECT
	select_list
FROM
	table_name
ORDER BY
	sort_expression1 [ASC | DESC],
        ...
	sort_expressionN [ASC | DESC];
```
Example:
```
SELECT
	first_name,
	last_name
FROM
	customer
ORDER BY
	first_name ASC;
```


<br/>

## Drop a database
- DROP DATABASE {dbname}

<br/>

## Alter existing user's permission
```
ALTER USER username WITH OPTION1 OPTION2 OPTION3;
options: CREATEDB, CREATEROLE, CREATEUSER, SUPERUSER, etc.
```

<br/>

## Drop all tables
```
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;

GRANT ALL ON SCHEMA public TO {postgres_user_name};
GRANT ALL ON SCHEMA public TO public;
```

<br/>

## Disconnect sessions
You can use pg_terminate_backend() to kill a connection. You have to be superuser to use this function. This works on all operating systems the same.
```
SELECT 
    pg_terminate_backend(pid) 
FROM 
    pg_stat_activity 
WHERE 
    -- don't kill my own connection!
    pid <> pg_backend_pid()
    -- don't kill the connections to other databases
    AND datname = 'database_name'
    ;
```

- https://stackoverflow.com/questions/5108876/kill-a-postgresql-session-connection
