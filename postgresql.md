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


Users and Groups
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


Databases
--------------------------------------------------

#### Creating a database
`sudo -u postgres psql createdb [mydatabase]`

#### Deleting a database
`sudo -u postgres psql dropdb [mydatabase]`

#### Selecting database
`sudo -u postgres psql [mydatabase]`

#### Listing databases
`[mydatabase]=# \l`

#### Listing tables
    [mydatabase]=# \d+
    [mydatabase]=# \d

#### Importing an SQL dump
`sudo -u postgres psql mydatabase < mydatabasedump`