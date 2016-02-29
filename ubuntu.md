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

#### Add user to the "sudo" group
`sudo adduser username sudo`

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

#### ERROR: Failed to fetch...

Remove all the contents in `/var/lib/apt/lists`:

```bash
sudo rm -vf /var/lib/apt/lists/*
```

Update cache:

```bash
sudo apt-get clean
sudo apt-get update
```


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


Repositories
--------------------------------------------------

Adding a repository:

```bash
sudo add-apt-repository ppa:rwky/redis
```

Removing a repository:

```bash
sudo add-apt-repository --remove ppa:rwky/redis
```

If you get an error saying "add-apt-repository: command not found":

#### Install apt-file
`sudo apt-get install apt-file`

#### Update apt-file index
`sudo apt-file update`

#### Search for the add-apt-repository package
`sudo apt-file search add-apt-repository package`

Install the **software-properties-common** package. When completed, retry installing the PPA package.

`sudo apt-get install software-properties-common`


File Permissions
--------------------------------------------------

#### Options
| Option | Meaning      |
|:------:|:------------:|
| **u**  |  owner       |
| **g**  |  group       |
| **o**  |  other       |
| **r**  |  read (4)    |
| **w**  |  write (2)   |
| **x**  |  execute (1) |

#### Adding file permissions
`chmod ugo+rwx filename`

#### Setting file permissions
`chmod ugo=rwx filename`

#### Removing file permissions
`chmod ugo-rwx filename`

#### Setting file permissions recursively
`chmod ugo=rwx -R directoryname`


File Sharing
--------------------------------------------------

#### Install the Samba server
`sudo apt-get install samba samba-common`

#### Install Samba configuration utility
`sudo apt-get install python-glade2 system-config-samba`

#### File sharing using NFS

Check if the NTF server is already installed:

```bash
dpkg -l | grep nfs-kernel-server
```

Install the NFS server:

```bash
sudo apt-get install nfs-kernel-server
```

Edit the `/etc/exports` file and add the directory to be exported:

```
/path/to/directory1 *(rw,sync,no_subtree_check,no_root_squash)
/path/to/directory2 192.168.254.105(rw,sync,no_subtree_check,no_root_squash)
```

Options for `/etc/exports`:
| Option               | Description           |
|:--------------------:|:---------------------:|
| **rw**               | read and write access |
| **sync**             |                       |
| **no_root_squash**   |                       |
| **no_subtree_check** |                       |

Run this command everytime the `/etc/exports` file is updated:

```bash
sudo exportfs -a
```

Restart the NFS server:

```bash
sudo service nfs-kernel-server restart
```

Install the NFS client:

```bash
sudo apt-get install nfs-common
```

Mount the shared directories to a local directory:

```bash
sudo mount 192.168.254.105:/path/to/directory1 /path/to/local/directory1
sudo mount 192.168.254.105:/path/to/directory2 /path/to/local/directory2
```

Display all mounted NFS directories:

```bash
mount -t nfs
```


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


SSH
--------------------------------------------------

#### Logging in to a remote server
`ssh myusername@192.168.111.222`

#### Logging in to a remote server with a different private key
`ssh myusername@192.168.111.222 -i ~/myprivatekey`

#### Generating a new SSH Key
`ssh-keygen -t rsa -b 4096`

#### Add the new SSH key to the remote server's authorized_keys file
`ssh-copy-id myusername@192.168.111.222`

#### Remove host key
`ssh-keygen -f "/home/$USER/.ssh/known_hosts" -R 192.168.111.222`

#### SSH important configurations

    # Disable password authentication
    PasswordAuthentication no

    # Enable public key authentication
    PubkeyAuthentication yes
    RSAAuthentication yes


Restarting the system
--------------------------------------------------
`sudo shutdown -h now`


Create a Certificate Signing Request (CSR)
--------------------------------------------------

Create the directory where the keys will be created:

```bash
sudo mkdir -p /etc/nginx/ssl
```

Create the private key and certificate signing request. The `-nodes` option means there will be no passphrase:

```bash
sudo openssl req -nodes -newkey rsa:2048 -out /etc/nginx/ssl/mysite.com.csr -keyout /etc/nginx/ssl/mysite.com.key
```

Use the following command to use SHA256:

```bash
sudo openssl req -nodes -sha256 -newkey rsa:2048 -out /etc/nginx/ssl/mysite.com.csr -keyout /etc/nginx/ssl/mysite.com.key
```

When prompted for the **Common Name**, be sure to enter the **fully qualified domain name**. Example: `mysite.com` or `*.mysite.com` for multiple (wildcard) subdomains.