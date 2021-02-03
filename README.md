# `Postgresql` database basic operations

#### How to install PostgreSQL on a Mac with Homebrew and Lunchy?
`$ brew update`
`$ brew doctor`

#### Install Postgres
`$ brew install postgresql`

#### Create/Upgrade a database
`$ initdb /usr/local/var/postgres -E utf8`

#### Install Lunchy
`$ gem install lunchy`

#### Start/Stop Postgres
`$ mkdir -p ~/Library/LaunchAgents` 
`$ cp /usr/local/Cellar/postgresql/9.2.1/homebrew.mxcl.postgresql.plist ~/Library/LaunchAgents/`

Since we're using Lunchy, we don't need to run this third command:
`$ launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist`

Instead, we'll simply use this to start Postgres:
`$ lunchy start postgres`

To stop Postgres:
`$ lunchy stop postgres`

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

##### Export be simular 
`pg_dump -U macair -h localhost mydb >> ~/Desktop/mydb.sql`
Here `macair` means my database username.


### How to use `postgress` database in `Django` web app?
1) First you active your virtualenv
then ```pip install django psycopg2```

2) Then configuration `Django setting.py` file look like this:

````
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'my_db',
        'USER': 'db_user',
        'PASSWORD': '123',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
````

#### create a database user which we will use to connect to and interact with the database.
`CREATE USER mbrsagor WITH PASSWORD 'sagor123';`

#### we need to do is give our database user access rights to the database we created:
`GRANT ALL PRIVILEGES ON DATABASE my_db TO my_user;`


###### How to create table?
```
CREATE TABLE student (
id INT NOT NULL PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
gender VARCHAR(10) NOT NULL,
email VARCHAR(75),
date DATE);
```
Then show table `data` using `\d`

###### List of relations in table.
` \d table_name;`
`\dt`

###### How to drop table?
`DROP TABLE table_name;`

###### Insert data into table.
```
INSERT INTO student(first_name, last_name, gender, date, email)
VALUES('mbr', 'sagor', 'yes', date '2020-10-10', 'mbrsagor@gmail.com');
```
###### How to Query data from the table?
`SELECT * FROM table_name;`

###### Select from `WHERE`.
`SELECT FROM table_name WHERE table_field='value'; `

