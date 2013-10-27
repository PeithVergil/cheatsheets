PostgreSQL
==========


Installation
--------------------------------------------------
`sudo apt-get install postgresql postgresql-contrib`


Psql Client
--------------------------------------------------

##### Options for `psql`
*   **-U, --username=USERNAME**
*   **-h, --host=HOSTNAME**
*   **-p, --port=PORT**
*   **-W, --password**

#### Running psql
`sudo -u postgres psql`

#### Quiting psql
`\q`


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
`sudo -u postgres createuser -D -R -P -S -e myusername`

#### Creating a super user using the `createuser` command line utility
`sudo -u postgres createuser -P -s -e myusername`

__________________________________________________

The commands below must be entered from within `psql`.

#### Creating a group
`CREATE ROLE mygroup INHERIT;`

#### Assigning a user to a group
`GRANT mygroup TO myusername;`

#### Change user password
`\password myusername;`

#### Another way of creating a user
`CREATE USER myusername WITH PASSWORD 'mypassword';`

#### Granting privileges to the new user
`GRANT ALL ON DATABASE mydatabase TO myusername;`


#### Display a list of roles from within psql.
`\du`


Databases
--------------------------------------------------

#### Creating a database
`sudo -u postgres createdb mydatabase`

#### Deleting a database
`sudo -u postgres dropdb mydatabase`

#### Selecting database
`sudo -u postgres psql mydatabase`

#### Listing databases
`[mydatabase]=# \l`

#### Listing tables
    [mydatabase]=# \d+
    [mydatabase]=# \d

#### Importing an SQL dump
`sudo -u postgres psql mydatabase < mydatabasedump`


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
`pg_dump -h localhost -p 5432 -U myusername -F p -b -v -f mydatabase.sql mydatabase`

#### Create a plain text backup of a set of tables
`pg_dump -h localhost -p 5432 -U myusername -F p -b -v -t mytable1 -t mytable2 -t mytable3 -f mydatabase.sql mydatabase`

#### Restore a plain text backup
`psql -U postgres -f mydatabase.sql`

#### Restore a plain text backup to a specific database
`psql -U postgres -d mydatabase -f mydatabase.sql`