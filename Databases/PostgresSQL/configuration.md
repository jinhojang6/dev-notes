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

## Memory Tuning
`postgresql.conf` should be updated to leverage the OS memory. 

- [Parameter tuning guidelines](https://severalnines.com/database-blog/architecture-and-tuning-memory-postgresql-databases)

For example, a VM with 32 cores and 128 GB RAM can be
```
// /var/lib/postgresql/data/postgresql.conf

shared_buffers: 16GB
temp_buffers: 2GB
work_mem = 32MB
max_connections: 512
maintenance_work_mem=2GB
```
