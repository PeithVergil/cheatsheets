PostgreSQL
==========

## Installation
`sudo apt-get install postgresql postgresql-contrib`


## Run client
`sudo -u postgres psql`

## Exit client
`\q`


## Creating users and groups

#### Creating a user
`CREATE ROLE myusername LOGIN PASSWORD 'mypassword' CREATEDB VALID UNTIL 'infinity';`

#### Creating a super user
`CREATE ROLE myusername LOGIN PASSWORD 'mypassword' SUPERUSER VALID UNTIL '2020-10-20 20:00';`

#### Creating a group
`CREATE ROLE mygroup INHERIT;`

#### Assigning a user to a group
`GRANT mygroup TO myusername;`


## Change user password
`\password myusername`

## Creating a database
`sudo -u postgres createdb [mydatabase]`

## Deleting a database
`sudo -u postgres dropdb [mydatabase]`

## Selecting database
`sudo -u postgres psql [mydatabase]`

## Listing databases
`[mydatabase]=# \l`

## Listing tables
    [mydatabase]=# \d+
    [mydatabase]=# \d
