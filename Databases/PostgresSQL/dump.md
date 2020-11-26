## Backup the database

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

## Dump and restore specific table

```
pg_dump -d <database_name> -t <table_name> > file.sql
```

- Reference: https://stackoverflow.com/questions/3682866/how-to-create-a-backup-of-a-single-table-in-a-postgres-database

<br/>
