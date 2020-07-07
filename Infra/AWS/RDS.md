## RDS

Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security and compatibility they need.

- https://aws.amazon.com/rds/?nc1=h_ls

<br/>

## Connecting to a PostgreSQL DB

Configuration

1. Network & Security
- Select a security group
- Public accessibility should be `Yes`

Connect

Unix
```
psql ^
   --host=<DB instance endpoint> ^
   --port=<port> ^
   --username=<master user name> ^
   --password ^
   --dbname=<database name> 
```

or

```
psql --host=mypostgresql.c6c8mwvfdgv0.us-west-2.rds.amazonaws.com --port=5432 --username=awsuser --password --dbname=mypgdb
```


References
- [Connecting to a DB Instance Running the PostgreSQL Database Engine](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToPostgreSQLInstance.html)