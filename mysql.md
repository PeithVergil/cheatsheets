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
`CREATE DATABASE [database] CHARACTER SET utf8;`


## Displaying results vertically
`SELECT * FROM [table]\G`


## Renaming a table
`RENAME TABLE [old_name] TO [new_name];`


## Modifing table definition
`ALTER TABLE [table] MODIFY COLUMN [column] [column definition];`
