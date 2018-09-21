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
```bash
php artisan make:migration create_user_table
```

##### Creating a migration with a "table creation" template
```bash
php artisan make:migration create_users_table --create=users
```

##### Running all outstanding migrations
```bash
php artisan migrate
```

Rollback the last migration.

```bash
php artisan migrate:rollback
```


Models
--------------------------------------------------

Create a new model.

```bash
php artisan make:model Profile
```

Create a new model and a migration.

```bash
php artisan make:model Profile --migration
```


Model Observers
--------------------------------------------------

Create a new model observer.

```bash
php artisan make:observer ProfileObserver --model=Profile
```


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


Commands
--------------------------------------------------

Creating a new command

```bash
php artisan make:command SendTestEmail
```

Example command script:

```php
<?php

namespace App\Console\Commands;


use Mail;
use Illuminate\Console\Command;


class SendTestEmail extends Command
{
    /**
     * The name and signature of the console command.
     *
     * @var string
     */
    protected $signature = 'sendtestemail';

    /**
     * The console command description.
     *
     * @var string
     */
    protected $description = 'Send a test email.';

    /**
     * Create a new command instance.
     *
     * @return void
     */
    public function __construct()
    {
        parent::__construct();
    }

    /**
     * Execute the console command.
     *
     * @return mixed
     */
    public function handle()
    {
        $user = 'hello.world@example.com';
        $name = 'Hello World';

        Mail::send('emails.sendtestemail', ['user' => $user, 'name' => $name], function($mailer) {
            $mailer->from('contact@example.com', 'My Web Application');

            $mailer->to($user, $name)->subject('Your Reminder!');
        });
    }
}
```


Tests
--------------------------------------------------

Creating a unit test

```bash
php artisan make:test MailmanTest
```

Example unit test:

```php
<?php

use Illuminate\Foundation\Testing\WithoutMiddleware;
use Illuminate\Foundation\Testing\DatabaseMigrations;
use Illuminate\Foundation\Testing\DatabaseTransactions;


class MailmanTest extends TestCase
{
    /**
     * A basic test example.
     *
     * @return void
     */
    public function testSend()
    {
        $this->assertTrue(true);
    }
}
```