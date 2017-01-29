MySQL
=====

## Installation
`sudo apt-get install mysql-server`


## Configuration

1.  Edit the config file
        vim /etc/mysql/my.cnf

2.  Change the following values
        bind-address = 0.0.0.0
        default-storage-engine = INNODB


## Restarting the server
`sudo service mysql restart`


## Stopping the server
`sudo service mysql stop`


## Check if the server is running
`sudo netstat -tap | grep mysql`


## Connecting to the server
`mysql --host=[localhost] --user=[root] --password='[password]' --database='[database]'`


## Creating a new user
`CREATE USER '[user]'@'localhost' IDENTIFIED BY '[password]';`


## Changing a user's password
`SET PASSWORD FOR '[user]'@'localhost' = PASSWORD('[password]');`


## Granting privileges
* **ALL PRIVILEGES** - all access to a designated database
* **CREATE**         - create new tables or databases
* **DROP**           - delete tables or databases
* **DELETE**         - delete rows from tables
* **INSERT**         - insert rows into tables
* **SELECT**         - read through databases
* **UPDATE**         - update table rows
* **GRANT OPTION**   - grant or remove other users' privileges

### Applying privileges
`GRANT ALL PRIVILEGES ON [database].[table] TO '[user]'@'localhost';`

### Reloading privileges
`FLUSH PRIVILEGES;`


## Listing available users
`SELECT User, Host FROM mysql.user;`


## Listing user permissions
`SHOW GRANTS FOR '[user]'@'localhost';`


## Revoking permissions
`REVOKE ALL PRIVILEGES ON [database].[table] TO '[user]'@'localhost';`


## Remove a user
`DROP USER '[user]'@'localhost';`


## Creating a database
```mysql
CREATE DATABASE [database] CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```


## Displaying results vertically
`SELECT * FROM [table]\G`


Alter Tables
--------------------------------------------------

## Renaming a table
`RENAME TABLE [old_name] TO [new_name];`


## Modifing table definition
`ALTER TABLE [table] MODIFY COLUMN [column] [column definition];`

## Droping foreign key constraints
`ALTER TABLE [mytable] DROP FOREIGN KEY [foreign key constraint];`

Adding a foreign key to an existing table (`user`) that references another table (`profile`).

```sql
ALTER TABLE user ADD profile_id INT NOT NULL DEFAULT 0;
```

```sql
ALTER TABLE user ADD CONSTRAINT fk_profile_id FOREIGN KEY (profile_id) REFERENCES profile(id);
```


Backup and Restore
--------------------------------------------------

### Backup a single database
`mysqldump -h [localhost] -u [root] -p[password] [database] > [database].sql`

### Backup multiple databases
`mysqldump -h [localhost] -u [root] -p[password] --databases [database1] [database2] > databases.sql`

### Backup all databases
`mysqldump -h [localhost] -u [root] -p[password] --all-databases > all-databases.sql`

### Backup a specific table
`mysqldump -h [localhost] -u [root] -p[password] [database] [table] > [database]_table.sql`

### Restoring backups
`mysql -u root -p[password] [database] < [database].sql`