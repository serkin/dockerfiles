FROM serkin/php7-fpm

MAINTAINER serkin.alexander@gmail.com

RUN docker-php-ext-install pdo pdo_mysql


# Install Phalcon 3

RUN git clone --depth=1 -b 3.0.x https://git@github.com/phalcon/cphalcon.git \
 	&& cd cphalcon/build \
  && ./install
RUN echo "extension=phalcon.so" > $PHP_INI_DIR/conf.d/phalcon.ini


# Install Phalcon 3 dev tools

RUN cd /tmp && git clone --depth=1 -b 3.0.x https://git@github.com/phalcon/phalcon-devtools.git \
 	&& cd phalcon-devtools \
  && cp phalcon.php phalcon \
  && chmod ugo+x phalcon

ENV PATH=$PATH:/tmp/phalcon-devtools
