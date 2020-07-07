## Listing databases
- \l or \list

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