# Dockerfiles

## php

A series of images based on https://gitlab.com/ric_harvey/nginx-php-fpm

* PHP 7.2
* Imagick
* GD
* BCMath
* Other stuff to make Laravel work

The base image is `lenderhomepage/php`

To use the base `fpm-nginx` image, the image name would be `lenderhomepage/php:fpm-nginx-latest`

### Tags

* `fpm-nginx-latest`
* `fpm-nginx-mongo-latest` - Includes the mongo PHP extension`
* `ci-latest`

### Building

Run the `build.sh` script found in each base directory

### Pushing to Docker Hub

Run `docker push lenderhomepage/php:${tag}`

You need to have a Docker Hub account and be a collaborator in the `lenderhomepage` team.

To log in, run `docker login` and enter your credentials
