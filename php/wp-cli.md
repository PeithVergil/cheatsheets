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

```bash
wp core download
```

Check the version that was downloaded:

```bash
wp core version
```

Configure Wordpress:

```bash
wp core config --dbname=[mydb] --dbuser=[myuser] --dbpass=[mypass]
```


Create a new database using the configuration above:
`wp db create`


Finalize the Wordpress installation:

```bash
wp core install --url="[www.mysite.com]" --title="[My Site]" --admin_user=[myadmin] --admin_email=[myemail@mysite.com] --admin_password=[mypass]
```


Themes
--------------------------------------------------

Check the status of available themes:

```bash
wp theme status
```


Plugins
--------------------------------------------------

Install a WordPress plugin:

```bash
wp plugin install [woocommerce]
```

Update a WordPress plugin:

```bash
wp plugin update [woocommerce]
```


Tests
--------------------------------------------------

Create tests for your plugin:

```bash
wp scaffold plugin-tests [myplugin]
```