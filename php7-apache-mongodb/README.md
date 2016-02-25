# Docker container for PHP7 + MongoDB #

This docker consists of: php:latest(PHP7), MongoDB driver for HHVM and PHP7, GIT, Composer


## Usage ##

I use it for testing

Run `mongo` container first

  docker run -d --name mongo -i -t -p 27017:27017 mongo

Now run any code

  docker run --link mongo:mongo -v "$PWD":/var/src/ serkin/php7-mongodb php -r '$manager = new MongoDB\Driver\Manager("mongodb://mongo");'


## Build container ##

  docker build -t php-fpm .
