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

## Drop a database
- DROP DATABASE {dbname}

<br/>

## Alter existing user's permission
```
ALTER USER username WITH OPTION1 OPTION2 OPTION3;
options: CREATEDB, CREATEROLE, CREATEUSER, SUPERUSER, etc.
```

<br/>

## Drop all the records 
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