PostgreSQL
==========


Installation
--------------------------------------------------
`sudo apt-get install postgresql postgresql-contrib`


Clients
--------------------------------------------------

### psql

##### Options for `psql`
*   **-U, --username=USERNAME**
*   **-h, --host=HOSTNAME**
*   **-p, --port=PORT**
*   **-W, --password**

##### Running psql
`sudo -u postgres psql`

##### Quiting psql
`\q`


### pgadmin

##### Installation
`sudo apt-get install pgadmin3`


Users, Groups, and Privileges
--------------------------------------------------

##### Options for `createuser`
*   **-d, --createdb**
*   **-D, --no-createdb**
*   **-r, --createrole**
*   **-R, --no-createrole**
*   **-s, --superuser**
*   **-S, --no-superuser**
*   **-P, --pwprompt**
*   **-e, --echo**

#### Creating a user using the `createuser` command line utility
`sudo -u postgres createuser -D -R -P -S -e [myusername]`

#### Creating a superuser using the `createuser` command line utility
`sudo -u postgres createuser -P -s -e [myusername]`

#### Deleting a user using the `dropuser` command line utility
`sudo -u postgres dropuser [myusername]`

#### Altering a user's privilege
`ALTER USER [myusername] CREATEDB`

#### Creating a group
`[mydatabase]=# CREATE ROLE [mygroup] INHERIT;`

#### Assigning a user to a group
`[mydatabase]=# GRANT [mygroup] TO [myusername];`

#### Change user password
`[mydatabase]=# \password [myusername];`

#### Another way of creating a user
`[mydatabase]=# CREATE USER [myusername] WITH PASSWORD '[mypassword]';`

Change the user password:

```sql
ALTER ROLE [myusername] WITH PASSWORD '[mypassword]';
```

#### Granting privileges to the new user
`[mydatabase]=# GRANT ALL ON DATABASE mydatabase TO [myusername];`

#### Display a list of roles
`[mydatabase]=# \du`


Databases
--------------------------------------------------

#### Creating a database
`sudo -u postgres createdb [mydatabase]`

#### Deleting a database
`sudo -u postgres dropdb [mydatabase]`

#### Selecting database
`sudo -u postgres psql [mydatabase]`

#### Listing databases via psql
`sudo -u postgres psql -l`

#### Listing databases
`[mydatabase]=# \l`


#### Importing an SQL dump
`sudo -u postgres psql [mydatabase] < mydatabasedump`

Change the database owner:

```sql
ALTER DATABASE [mydatabase] OWNER TO [myusername];
```


Tables
--------------------------------------------------

#### Listing tables
`[mydatabase]=# \dt`

#### Show table details
`[mydatabase]=# \d+ [mytable]`

#### Altering a table

##### Change owner
`ALTER TABLE [mytable] OWNER TO [myusername];`

##### Dropping constraint
`ALTER TABLE [mytable] DROP CONSTRAINT "[constraint_name]";`


Views
--------------------------------------------------

#### Listing views
`[mydatabase]=# \dv`


Backup and Restore
--------------------------------------------------

#### Options for `pg_dump`
*   **-h, --host=HOSTNAME**      database server host or socket directory
*   **-p, --port=PORT**          database server port number
*   **-U, --username=NAME**      connect as specified database user
*   **-F, --format=c|d|t|p**     output file format (custom, directory, tar, plain text)
*   **-b, --blobs**              include large objects in dump
*   **-v, --verbose**            verbose mode
*   **-f, --file=FILENAME**      output file or directory name

#### Create a plain text backup
`pg_dump -h localhost -p 5432 -U [myusername] -F p -b -v -f [mydatabase].sql [mydatabase]`

#### Create a plain text backup of a set of tables
`pg_dump -h localhost -p 5432 -U [myusername] -F p -b -v -t [mytable1] -t [mytable2] -t [mytable3] -f [mydatabase].sql [mydatabase]`

#### Restore a plain text backup
`psql -U postgres -f [mydatabase].sql`

#### Restore a plain text backup to a specific database
`psql -U postgres -d [mydatabase] -f [mydatabase].sql`


Host-based Authentication
--------------------------------------------------

    # Allow any user on the local system to connect to any database with
    # any database user name.
    # TYPE  DATABASE        USER            ADDRESS                 METHOD
    host    all             all             127.0.0.1/32            trust

    # The same as above, but using a host name.
    host    all             all             localhost               trust