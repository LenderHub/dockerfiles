# Dockerfiles

## nginx-php-fpm

A series of images based on https://gitlab.com/ric_harvey/nginx-php-fpm

* PHP 7.2
* Imagick
* GD
* BCMath
* Other stuff to make Laravel work

`lenderhub/nginx-php-fpm:latest` - Base image for usage on most services

`lenderhub/nginx-php-fpm-mongo` - Image to use if you need MongoDB support
