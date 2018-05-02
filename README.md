# DockerNMPLaravel

Create server structure Nginx + MySQL + PHP on Docker container.

### Docker images

Nginx   : nginx:latest
PHP-FPM : php:7.0-fpm
MySQL   : mysql/mysql-server:latest

### PHP Framework

Laravel 5.5.*

# Start service

Use docker-compose to manager multi-container.

### Command

    docker-compose up

# Laravel database create

Use command-line interface included with Laravel to create database.

### PHP-FPM container name

Use docker command to get PHP-FPM

    ubuntu@ubuntu:~$ docker container ls --filter "name=php-fpm"
    CONTAINER ID  IMAGE                     COMMAND                 CREATED         STATUS         PORTS     **NAMES**
    85b40af8b34d  dockernmplaravel_php-fpm  "docker-php-entryp..."  41 minutes ago  Up 30 minutes  9000/tcp  **dockernmplaravel_php-fpm_1**

PHP-FPM container name : **dockernmplaravel_php-fpm_1**

### Command

    docker exec **dockernmplaravel_php-fpm_1** php artisan migrate
