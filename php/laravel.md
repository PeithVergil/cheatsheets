Laravel
=======


Ubuntu
--------------------------------------------------

Update packages.

```bash
sudo apt-get update -y && sudo apt-get upgrade -y
```


Apache
--------------------------------------------------

Install the Apache Web Server.

```bash
sudo apt-get install -y apache2
```

Enable `mod_rewrite`.

```bash
sudo a2enmod rewrite
```

Restart the server.

```bash
sudo service apache2 restart
```

#### Development Environment

Edit `envvars`.

```bash
sudo vim /etc/apache2/envvars
```

Change system user.

```bash
export APACHE_RUN_USER=vagrant
export APACHE_RUN_GROUP=vagrant
```

Edit the enabled virtual host file.

```bash
sudo vim /etc/apache2/sites-available/000-default.conf
```

Update some of the values.

```xml
<VirtualHost *:80>
        ...
        
        DocumentRoot /vagrant/myproject/public

        <Directory "/vagrant/myproject/public">
            Options Indexes FollowSymLinks
            AllowOverride All
            Require all granted
        </Directory>

        ...

        ErrorLog /vagrant/logs/error.log
        CustomLog /vagrant/logs/access.log combined
        
        ...
</VirtualHost>
```

Restart the server.

```bash
sudo service apache2 restart
```


MySQL
--------------------------------------------------

Install the MySQL server.

```bash
sudo apt-get install -y mysql-server
```

#### Development Environment

Root Password: **abcdef**

Edit config file.

```bash
sudo vim /etc/mysql/my.cnf
```

Listen to all address.

```ini
bind-address = 0.0.0.0
```

Restart the server.

```bash
sudo service mysql restart
```


PHP
--------------------------------------------------

Install build tools.

```bash
sudo apt-get install build-essential curl libcurl3 libcurl3-dev
```

Install PHP 7.0.

```bash
sudo apt-get install -y php7.0
```

Install some PHP 7.0 extensions.

```bash
sudo apt-get install -y php7.0-gd php7.0-xml php7.0-zip php7.0-curl php7.0-mysql php7.0-mcrypt php7.0-mbstring
```


Composer
--------------------------------------------------

Download `composer`.

```bash
php -r "readfile('https://getcomposer.org/installer');" | php
```

Move `composer` to `/usr/local/bin/`.

```bash
sudo mv composer.phar /usr/local/bin/composer
```


Laravel Installation and Setup
--------------------------------------------------

Download and install Laravel.

```bash
composer global require "laravel/installer"
```

Edit `.bashrc`

```bash
vim ~/.bashrc
```

Add composer's bin directory to the system path.

```bash
export PATH=~/.composer/vendor/bin:$PATH
```


Laravel Usage
--------------------------------------------------

Creating a project.

```bash
laravel new myproject
```

Allow write permission to the `storage` directory.

```bash
chmod -R 755 myproject/storage
```

Allow write permission to the `cache` directory.

```bash
chmod -R 755 myproject/bootstrap/cache
```


Controllers
--------------------------------------------------

##### Creating a controller
`php artisan controller:make SampleController`


Migrations
--------------------------------------------------

##### Creating a migration
`php artisan migrate:make create_user_table`

##### Creating a migration with a "table creation" template
`php artisan migrate:make create_users_table --table=users --create`

##### Running all outstanding migrations
`php artisan migrate`


Autoloading Libraries
--------------------------------------------------
1.  Edit the **composer.json** file. Add the path to your library folder in the *classmap* list.
        "autoload": {
            "classmap": [
                "app/commands",
                "app/controllers",
                "app/libraries",
                "app/models",
                "app/database/migrations",
                "app/tests/TestCase.php"
            ],
        },
2.  Enter the following command at the command line:
        composer dump-autoload