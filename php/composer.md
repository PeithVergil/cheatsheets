Composer
========


Installation
--------------------------------------------------

Download `composer`.

```bash
php -r "readfile('https://getcomposer.org/installer');" | php
```

Move `composer` to `/usr/local/bin/`.

```bash
sudo mv composer.phar /usr/local/bin/composer
```

Usage
--------------------------------------------------

Create a file called `composer.json` with the following sample content.

```json
{
    "require": {
        "bshaffer/oauth2-server-php": "1.8.0"
    }
}
```

Install the packages specified in the composer file.

```bash
composer install
```

Creating a `composer.json`:

```bash
composer init
```

Install a single package.

```bash
composer require firebase/php-jwt
```