Laravel
=======


Installation
--------------------------------------------------

#### Download the Laravel PHAR archive
`http -d http://laravel.com/laravel.phar`

**NOTE**: The `http` tool requires HTTPie

#### Move and rename to bin directory
`sudo mv laravel.phar /usr/local/bin/laravel`

#### Set permissions
`sudo chmod 755 /usr/local/bin/laravel`


Composer Installation
--------------------------------------------------

#### Download composer
`php -r "readfile('https://getcomposer.org/installer');" | php`

#### Move and rename to bin directory
`sudo mv composer.phar /usr/local/bin/composer`


Projects
--------------------------------------------------

#### Creating a project
`laravel new [myproject]`

#### Allow write permission to the `app/storage` directory
`chmod -R 755 [myproject]/app/storage`


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