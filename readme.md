# Laravel + Apache + Docker

## Description
Start developing a fresh Laravel application with `docker` using `docker-compose`.

The images used in this repo is `php:7.2-apache` and `mysql:5.7`. The goal is to make setting up the development as simple as possible.

IMPORTANT: this repo's purpose is mainly a tutorial to write docker development environment for Laravel projects. You're encouraged to replicate the setup on a more recent version of Laravel and its toolings.

## Up and running
Clone the repo:
```
$ git clone https://github.com/veevidify/laravel-apache-docker.git
$ cd laravel-apache-docker
```

Copy `.env.example` to `.env`
```
$ cp .env.example .env 
```

Build the images and start the services:
```
docker-compose build
docker-compose up -d
```

## Helper scripts
Running `composer`, `php artisan` or `phpunit` against the `php` container with helper scripts in the main directory:

### container
Running `./container` takes you inside the `laravel-app` container under user uid(1000) (same with host user)
```
$ ./container
devuser@8cf37a093502:/var/www/html$
```
### db
Running `./db` connects to your database container's daemon using mysql client.
```
$ ./db
mysql>
```

### composer
Run `composer` command, example:
```
$ ./composer dump-autoload
Generating optimized autoload files> Illuminate\Foundation\ComposerScripts::postAutoloadDump
> @php artisan package:discover --ansi
Discovered Package: beyondcode/laravel-dump-server
Discovered Package: fideloper/proxy
Discovered Package: laravel/tinker
Discovered Package: nesbot/carbon
Discovered Package: nunomaduro/collision
Package manifest generated successfully.
Generated optimized autoload files containing 3527 classes
```

### php-artisan
Run `php artisan` commands, example:
```
$ ./php-artisan make:controller BlogPostController --resource
php artisan make:controller BlogPostController --resource
Controller created successfully.
```

### phpunit
Run `./vendor/bin/phpunit` to execute tests, example:
```
$ ./phpunit --group=failing
vendor/bin/phpunit --group=failing
PHPUnit 7.5.8 by Sebastian Bergmann and contributors.



Time: 34 ms, Memory: 6.00 MB

No tests executed!
```
