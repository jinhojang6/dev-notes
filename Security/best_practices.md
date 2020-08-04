## Referencese

- [11 Web Application Security Best Practices](https://www.keycdn.com/blog/web-application-security-best-practices)

<br/>

## DB port should be blocked

The DB port (e.g., 5432 of PostgreSQL) enabling remote access should be blocked unless you think it is necessary. 

<br/>

## Docker container network

The DB port bridging the host machine and docker container should not be set `0.0.0.0:5432->5432/tcp`.
