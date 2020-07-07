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
grant all privileges on database {dbname} to {username};
```

<br/>

## Change the password
```
postgres=# ALTER USER {username} PASSWORD 'myPassword';
```

<br/>

## Backup a database

1. Log in as the postgres user
```
su - postgres
```

2. Dump the contents of a database to a file by running the following command. Replace dbname with the name of the database to be backed up.
```
pg_dump dbname > dbname.bak
```

3. To demonstrate restoring lost data, delete your example database and create an empty database in its place
```
dropdb dbname
createdb dbname
```

4. Restore the database using psql
```
psql test < dbname.bak
```

- Reference: [How to Back Up Your PostgreSQL Database](https://www.linode.com/docs/databases/postgresql/how-to-back-up-your-postgresql-database/)
