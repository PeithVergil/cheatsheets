PostgreSQL
==========


Installation
--------------------------------------------------
`sudo apt-get install postgresql postgresql-contrib`


Psql Client
--------------------------------------------------

#### Running psql
`sudo -u postgres psql`

#### Exiting psql
`\q`


Users, Groups, and Privileges
--------------------------------------------------

#### Creating a user
`CREATE ROLE myusername LOGIN PASSWORD 'mypassword' CREATEDB VALID UNTIL 'infinity';`

#### Creating a super user
`CREATE ROLE myusername LOGIN PASSWORD 'mypassword' SUPERUSER VALID UNTIL '2020-10-20 20:00';`

#### Creating a group
`CREATE ROLE mygroup INHERIT;`

#### Assigning a user to a group
`GRANT mygroup TO myusername;`

#### Change user password
`\password myusername`

#### Another way of creating a user
`CREATE USER myusername WITH PASSWORD 'mypassword';`

#### Granting privileges to the new user
`GRANT ALL ON DATABASE mydatabase TO myusername;`


Databases
--------------------------------------------------

#### Creating a database
`sudo -u postgres createdb [mydatabase]`

#### Deleting a database
`sudo -u postgres dropdb [mydatabase]`

#### Selecting database
`sudo -u postgres psql [mydatabase]`

#### Listing databases
`[mydatabase]=# \l`

#### Listing tables
    [mydatabase]=# \d+
    [mydatabase]=# \d

#### Importing an SQL dump
`sudo -u postgres psql mydatabase < mydatabasedump`


Backup and Restore
--------------------------------------------------

#### Options
*   **-h, --host=HOSTNAME**      database server host or socket directory
*   **-p, --port=PORT**          database server port number
*   **-U, --username=NAME**      connect as specified database user
*   **-F, --format=c|d|t|p**     output file format (custom, directory, tar, plain text)
*   **-b, --blobs**              include large objects in dump
*   **-v, --verbose**            verbose mode
*   **-f, --file=FILENAME**      output file or directory name


#### Create a plain text backup
`pg_dump -h localhost -p 5432 -U myusername -F p -b -v -f mydatabase.sql mydatabase`

#### Create a plain text backup of a set of tables
`pg_dump -h localhost -p 5432 -U myusername -F p -b -v -t mytable1 -t mytable2 -t mytable3 -f mydatabase.sql mydatabase`

#### Restore a plain text backup
`psql -U postgres -f mydatabase.sql`

#### Restore a plain text backup to a specific database
`psql -U postgres -d mydatabase -f mydatabase.sql`