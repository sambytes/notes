## Project Postgres Notes

Postgres cheatsheet as I go though a project

<a name="UUID"></a>
#### UUIDs

There are d[ifferent types of UUIDs](https://www.postgresql.org/docs/9.4/uuid-ossp.html) you can generate with postgres I used uuid_generate_v4();

To install run `CREATE EXTENSION IF NOT EXISTS "uuid-ossp";` * Only works for postgres 9.1 or higher

Then create a table using:
```
CREATE TABLE User("id" uuid DEFAULT uuid_generate_v4() not null,"name" text not null,"username" text not null,"password" text not null);

CREATE TABLE habits("id" uuid DEFAULT uuid_generate_v4() not null,"userid" text not null,"created" date not null,"target" int not null,"description" text,"title" text not 
```

#### Insert Data into a table

Some examples

```
INSERT INTO users (name, username, password)
VALUES
('Mike', 'mikke', 'nammmmeeeepassowrd');

INSERT INTO users (name, username, password)
VALUES
 ('Mike','testusername', 'password');
 ```

 #### See information in a table

```
SELECT * FROM information_schema.columns WHERE table_name ='users';
```

#### Use a database

In the world of mongodb I'm used to the command `use database`, however postgres is a bit different. Instead use `\c database`. Then you can start running table commands like insert and select. Before you select a database **this will not work**

