Laravel
=======


Project
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