MySQL
=====

## Installation
```bash
sudo apt-get install mysql-server
```

Or to install MariaDB

```bash
sudo apt-get install mariadb-server
```


## Configuration

1.  Edit the config file
        vim /etc/mysql/my.cnf

2.  Change the following values
        [mysqld]
        bind-address = 0.0.0.0
        default-storage-engine = INNODB


## Restarting the server
`sudo service mysql restart`


## Stopping the server
`sudo service mysql stop`


## Check if the server is running
`sudo netstat -tap | grep mysql`


## Connecting to the server
```bash
mysql --host=[localhost] --user=[root] --password='[password]' --database='[database]'
```

On Ubuntu 16.04, logging in as `root@localhost` to the MariaDB server requires `sudo`.

```bash
sudo mysql -u root
```


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


Stored Procedures
--------------------------------------------------

## List all stored procedures

```sql
SHOW PROCEDURE STATUS;
```

## List all stored procedures from a specific database

```sql
SHOW PROCEDURE STATUS WHERE db = 'mydatabase';
```

## Show stored procedure code.

```sql
SHOW CREATE PROCEDURE mystoredprocedure;
```

## Delete a stored procedure.

```sql
DROP PROCEDURE IF EXISTS mystoredprocedure;
```


Backup and Restore
--------------------------------------------------

##### Options for `mysqldump`
*   **-d, --no-data**
*   **-R, --routines**
*   **-n, --no-create-db**
*   **-t, --no-create-info**

### Backup a single database
`mysqldump -h [localhost] -u [root] -p[password] [database] > [database].sql`

### Backup multiple databases
`mysqldump -h [localhost] -u [root] -p[password] --databases [database1] [database2] > databases.sql`

### Backup all databases
`mysqldump -h [localhost] -u [root] -p[password] --all-databases > all-databases.sql`

### Backup a specific table
`mysqldump -h [localhost] -u [root] -p[password] [database] [table] > [database]_table.sql`

### Backup a stored procedure
`mysqldump -R -d -n -t -h [localhost] -u [root] -p[password] [database] > [database]_routines.sql`

### Restoring backups
`mysql -u root -p[password] [database] < [database].sql`


Character Set and Collation
--------------------------------------------------

Display character sets.

```sql
SHOW VARIABLES LIKE 'char%';
```

Display collations.

```sql
SHOW VARIABLES LIKE 'collation%';
```

Troubleshooting
--------------------------------------------------

Error: "Specified key was too long; max key length is 767 bytes"

```
innodb_default_row_format=dynamic
innodb_file_format=barracuda
innodb_file_per_table=true
innodb_large_prefix=true
```