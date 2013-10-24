Laravel 4
=========


Composer
--------------------------------------------------

##### Installing composer
1.  Download the composer executable
        curl -sS https://getcomposer.org/installer | php
2.  Move the executable where it can be accessed globally
        sudo mv composer.phar /usr/local/bin/composer


Projects
--------------------------------------------------

##### Creating a project
`composer create-project laravel/laravel sampleproject --prefer-dist`


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