## Drop all the tables 
```
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;

GRANT ALL ON SCHEMA public TO {postgres_user_name};
GRANT ALL ON SCHEMA public TO public;
```
