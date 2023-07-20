# MySQL

This note targeting at recoding all notes related to MySQL set up process, usages, and thinking.

## What is MySQL?


## Why should we use MySQL?


## How to set up MySQL?

## How to use MySQL in node.js?

### Set up a new MySQL account
Easy way:
```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```
To grant a specific privilege on a particular database and table, just run:
```
GRANT [type of privilege] ON [database name].[table name] TO '[username]'@'localhost';
```
If you ever need to deny or revoke a certain privilege, just run:
```
REVOKE [type of permission] ON [database name].[table name] FROM '[username]'@'localhost';
```

[Source](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql)
