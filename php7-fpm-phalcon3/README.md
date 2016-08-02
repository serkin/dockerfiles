## Docker container for PHP7 + Phalcon 3

This docker consists of: php:fpm(PHP7), PDO driver, GIT, Composer, Deployer, Phalcon 3


## Usage ##


Run `mysql` container first

  docker run --name mysql -d -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=test mysql

Now run any code

  docker run --link mysql:mysql -v "$PWD":/var/src/ serkin/php7-fpm-phalcon3 php -r 'print_r(get_loaded_extensions());'
