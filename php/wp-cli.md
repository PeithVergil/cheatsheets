WP-CLI
======


Installing WP-CLI.
--------------------------------------------------

Install WP-CLI globally using Composer:

```bash
composer global require "wp-cli/wp-cli" --update-with-dependencies
```


Download and configure Wordpress.
--------------------------------------------------

Download the latest Wordpress release:
`wp core download`


Configure Wordpress:
`wp core config --dbname=[mydb] --dbuser=[myuser] --dbpass=[mypass]`


Create a new database using the configuration above:
`wp db create`


Finalize the Wordpress installation:
`wp core install --url="[www.mysite.com]" --title="[My Site]" --admin_user=[myadmin] --admin_email=[myemail@mysite.com] --admin_password=[mypass]`


Install Plugins
--------------------------------------------------
`wp plugin install [woocommerce]`


Create plugin tests scaffold
--------------------------------------------------
`wp scaffold plugin-tests [myplugin]`