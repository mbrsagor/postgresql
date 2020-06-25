# `Postgresql` database basic operations

### How to access postgrad shell?
`psql postgres`

### How to create database?
`CREATE DATABASE db_name;`

### List of Database.
`\l`

### How to drop database ?
`DROP DATABASE db_name;`

### How to switch database?
`\c db_name`


### How to create `User`?
`CREATE USER user_name;`

### How to drop User?
`DROP USER user_name;`

### List of users.
`\du`


Many time we need to `import` or `export` database. In this `tutorial` I will show you how to `import` and `export` the postgress database.

### Import database
Open your terminal then run the command
`psql -U db_user db_name < ~/Desktop/db/my_db.sql`

`` Export be simular ``
`pg_restore -d db_name /path/dump_name.tar -c -U db_user`



### How to use `postgress` database in `Django` web app?
1) First you active your virtualenv
then ```pip install django psycopg2```

