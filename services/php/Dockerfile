FROM php:7.1-fpm

# updates
RUN apt-get update && apt-get install -y \
			libmcrypt-dev \
			libxml2-dev \
			libssl-dev

# opcache
RUN docker-php-ext-install opcache

# zip
RUN docker-php-ext-install zip

# bz2
RUN apt-get install -y libbz2-dev
RUN docker-php-ext-install bz2

# iconv
RUN docker-php-ext-install iconv

# calendar
RUN docker-php-ext-install calendar

# dom
RUN docker-php-ext-install dom

# mbstring
RUN docker-php-ext-install mbstring

# mcrypt
RUN docker-php-ext-install mcrypt

# mysqli
RUN docker-php-ext-install mysqli

# mysql
RUN apt-get install -y libpq-dev && \
    docker-php-ext-install pdo pdo_mysql

# mark volume/s as externally mounted
VOLUME ["/var/www"]

# starting point
WORKDIR /var/www

# make web server listen to this port
EXPOSE 9000

CMD ["php-fpm"]
