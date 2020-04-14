## Install on Ubuntu
```
sudo apt update
sudo apt install postgresql postgresql-contrib

# Verification
sudo -u postgres psql -c "SELECT version();"
```

<br/>

## Login as a default user
```
sudo -u postgres psql

# In case of authentication error
sudo vim /etc/postgresql/{version}/main/pg_hba.conf
local all postgres peer

reference: https://stackoverflow.com/questions/18664074/getting-error-peer-authentication-failed-for-user-postgres-when-trying-to-ge
```

<br/>



## Create a user and database
```
sudo su - postgres -c "createuser {username}"
sudo su - postgres -c "createdb {dbname}"
```

<br/>

## Grant privileges
```
sudo -u postgres psql
grant all privileges on database johndb to john;
```

<br/>

## Changing the password
```
postgres=# ALTER USER {username} PASSWORD 'myPassword';
```

<br/>

## Alter existing user's permission
```
ALTER USER username WITH OPTION1 OPTION2 OPTION3;
options: CREATEDB, CREATEROLE, CREATEUSER, SUPERUSER, etc.
```

## Drop all the tables 
```
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;

GRANT ALL ON SCHEMA public TO {postgres_user_name};
GRANT ALL ON SCHEMA public TO public;
```
