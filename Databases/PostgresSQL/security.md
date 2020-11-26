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

<br/>

## Encryption For Specific Columns

The [pgcrypto](https://www.postgresql.org/docs/10/pgcrypto.html) module allows certain fields to be stored encrypted. This is useful if only some of the data is sensitive. The client supplies the decryption key and the data is decrypted on the server and then sent to the client.

The decrypted data and the decryption key are present on the server for a brief time while it is being decrypted and communicated between the client and server. This presents a brief moment where the data and keys can be intercepted by someone with complete access to the database server, such as the system administrator.

- [Reference](https://www.postgresql.org/docs/10/encryption-options.html)
