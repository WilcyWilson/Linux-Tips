## Installing PostgreSQL in Arch

- Install postgresql using pacman package manager.
  
```console
[wilson@wilson-pc ~]$ sudo pacman -S postgresql
```

- Switch to postgres user
  
```console
[wilson@wilson-pc ~]$ sudo -u postgres -i
```

```console
[postgres@wilson-pc ~]$ initdb --locale $LANG -E UTF8 -D '/var/lib/postgres/data'
```
- Exit the postgres user

```console
[postgres@wilson-pc ~]$ exit
```

- Enable and Start postgresql.service

```console
[wilson@wilson-pc ~]$ sudo systemctl enable postgresql.service
[wilson@wilson-pc ~]$ sudo systemctl start postgresql.service
```

## Accessing PostgreSQL through Console

```console
[wilson@wilson-pc ~]$ sudo -u postgres -i
```

- Create a database

```console
[postgres@wilson-pc ~]$ createdb wil
```

- Login to that database and check the user.


```console
[postgres@wilson-pc ~]$ psql wil
psql (13.4)
Type "help" for help.

wil=# select current_user;
 current_user 
--------------
 postgres
(1 row)
```

- Create a new role with necessary privileges and set it.

```console
wil=# create role wilcy with superuser login createdb;
CREATE ROLE
wil=# set role wilcy;
SET
```
- Select the current user we just created.

```console
wil=# select current_user;
 current_user 
--------------
 wilcy
(1 row)
```

- List roles

```console
wil=# \du
                                   List of roles
 Role name |                         Attributes                         | Member of 
-----------+------------------------------------------------------------+-----------
 postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}
 wilcy     | Superuser, Create DB                                       | {}

```

- List databases,tables and users

```console
wil=# \l
                                  List of databases
   Name    |  Owner   | Encoding |   Collate   |    Ctype    |   Access privileges   
-----------+----------+----------+-------------+-------------+-----------------------
 dvdrental | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 postgres  | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 template0 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
 wil       | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
(5 rows)
```






