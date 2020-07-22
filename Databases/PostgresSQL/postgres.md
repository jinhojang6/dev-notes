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

<br/>

## Security

1. HOST_AUTH_METHOD

docker_container_name:
  container_name: something
  environment:
    POSTGRES_USER: {username}
    POSTGRES_DB: {dbma,e|
    POSTGRES_HOST_AUTH_METHOD: password
    
2. pg_hba.conf

Location:  /var/lib/postgresql/[version]/

```
# TYPE  DATABASE        USER            ADDRESS                 METHOD

# "local" is for Unix domain socket connections only
local   all             all                                     trust
# IPv4 local connections:
host    all             all             127.0.0.1/32            trust
# IPv6 local connections:
host    all             all             ::1/128                 trust
# Allow replication connections from localhost, by a user with the
# replication privilege.
local   replication     all                                     trust
host    replication     all             127.0.0.1/32            trust
host    replication     all             ::1/128                 trust

host all all all password
```

The `host all all all password` line at the end of pg_hba.conf set the authentication for public access. It should be `password`.
