Ubuntu
======

System Info
--------------------------------------------------

`uname -a`


Users and Groups
--------------------------------------------------

#### View users
`cat /etc/passwd`

#### Create user
`sudo adduser username`

#### Delete user
`sudo deluser username`

#### Set user password
`passwd username`

#### Lock a user account
`sudo passwd -l username`

#### Unlock a user account
`sudo passwd -u username`

#### Add a personalized group
`sudo addgroup groupname`

#### Delete a personalized group
`sudo delgroup groupname`

#### Add user to a group
`sudo adduser username groupname`

#### Remove user from a group
`sudo deluser username groupname`

#### View user account status
`sudo chage -l username`

#### Change user account status
`sudo chage username`

#### Change owner of file or folder
`sudo chown -R root:root /home/username/`


Packages
--------------------------------------------------

#### Removing a package
`sudo apt-get remove packagename`

#### Removing a package and all its configuration files
`sudo apt-get --purge remove packagename`

#### Listing all installed packages
    dpkg --list
    dpkg --list | less
    dpkg --list | grep -i keyword


Processes
--------------------------------------------------

### ps

#### See every process on the system
`ps -A`

#### See process run by user
`ps -u username`


### top

#### Real-time view of a running system
`top`

#### Save Process Snapshot to a file
`top -b -n1 > ~/process.log`


### htop

#### Installing htop
`apt-get install htop`

#### Running htop
`htop`


Grep
--------------------------------------------------

#### Search _file_ for _keyword_
`grep keyword file`

#### Case insensitive searching
`grep -i keyword file`

#### Search recursively
`grep -r keyword folder`

#### Match whole word
`grep -w keyword file`

#### List just the filenames
`grep -l keyword *.txt`


Repositories
--------------------------------------------------

#### Adding repositories
`sudo add-apt-repository ppa:rwky/redis`

If you get an error saying "add-apt-repository: command not found":

#### Install apt-file
`sudo apt-get install apt-file`

#### Update apt-file index
`sudo apt-file update`

#### Search for the add-apt-repository package
`sudo apt-file search add-apt-repository package`

Install the **software-properties-common** package. When completed, retry installing the PPA package.

`sudo apt-get install software-properties-common`


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


SSH Keys
--------------------------------------------------

#### Generating a new SSH Key
`ssh-keygen -t rsa -C "myemail@mydomain.com"`


Restarting the system
--------------------------------------------------
`sudo shutdown -h now`