Ubuntu Cheatsheet
=================

## Get system info
`uname -a`

## View users
`cat /etc/passwd`

## Create user
`sudo adduser _username_`

## Delete user
`sudo deluser _username_`

## Set user password
`passwd _username_`

## Lock a user account
`sudo passwd -l _username_`

## Unlock a user account
`sudo passwd -u _username_`

## Add a personalized group
`sudo addgroup _groupname_`

## Delete a personalized group
`sudo delgroup _groupname_`

## Add user to a group
`sudo adduser username _groupname_`

## Remove user from a group
`sudo deluser _username_ _groupname_`

## View user account status
`sudo chage -l _username_`

## Change user account status
sudo chage _username_

## Change owner of file or folder
sudo chown -R root:root /home/username/

####################################
# Removing Apps
####################################

## Remove package
sudo apt-get remove _packagename_

## Remove package and all configuration files
sudo apt-get --purge remove _packagename_

####################################
# Processes
####################################

############################
# ps

# See every process on the system
ps -A

# See process run by user
ps -u _username_

############################
# top

# Real-time view of a running system
top

# Save Process Snapshot to a file
top -b -n1 > ~/process.log

############################
# htop

# Installing htop
apt-get install htop

# Running htop
htop

####################################
# Grep
####################################

# Search _file_ for _keyword_
grep _keyword_ _file_

# Case insensitive searching
grep -i _keyword_ _file_

# Search recursively
grep -r _keyword_ _folder_

# Match whole word
grep -w _keyword_ _file_

# List just the filenames
grep -l _keyword_ *.txt

####################################
# Adding repositories
####################################

sudo add-apt-repository ppa:rwky/redis

############################
# If add-apt-repository: command not found

## Install apt-file
sudo apt-get install apt-file

## Update apt-file index
sudo apt-file update

## Search for the add-apt-repository package
sudo apt-file search add-apt-repository package

## Install the software-properties-common package
## When completed, retry installing the PPA package
sudo apt-get install software-properties-common

Installing the LAMP stack
--------------------------------------------------

#### Update the repo
`sudo apt-get update`

#### Install Apache
1.  Install the apache server
        sudo apt-get install apache2
2.  Enable apache's mod_rewrite
        sudo a2enmod rewrite

#### Install MySQL
`sudo apt-get install mysql-server`

#### Install PHP5
`sudo apt-get install php5 php5-curl php5-mysql php5-mcrypt`

#### Install mod_php5
    sudo apt-get install libapache2-mod-php5

#### Installing phpMyAdmin
    sudo apt-get install phpmyadmin
    sudo vim /etc/apache2/apache2.conf
    Include /etc/phpmyadmin/apache.conf

#### Installing phpPgAdmin
1.  Download and install phpPgAdmin
        sudo apt-get install phppgadmin
2.  Edit the phpPgAdmin configuration file
        sudo vim /etc/apache2/conf.d/phppgadmin
3.  Uncomment the following line
        # allow from all
3.  Edit the Apache configuration file
        sudo vim /etc/apache2/apache2.conf
4.  Add the following code at the end of the Apache configuration file
        Include /etc/phppgadmin/apache.conf
5.  Restart the Apache server
        sudo service apache2 restart