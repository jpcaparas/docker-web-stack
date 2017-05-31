FROM php:7.1-fpm

# updates
RUN apt-get update && apt-get install -y \
			libmcrypt-dev \
			libxml2-dev \
			libssl-dev \
			libpq-dev \
			libbz2-dev \
			libpng-dev

# extensions
RUN docker-php-ext-install opcache && \
    docker-php-ext-install zip && \
    docker-php-ext-install bz2 && \
    docker-php-ext-install iconv && \
    docker-php-ext-install calendar && \
    docker-php-ext-install dom && \
    docker-php-ext-install gd && \
    docker-php-ext-install mbstring && \
    docker-php-ext-install mcrypt && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install pdo pdo_mysql

# mark volume/s as externally mounted
VOLUME ["/var/www"]

# starting point
WORKDIR /var/www

# make web server connect to this port
EXPOSE 9000

CMD ["php-fpm"]
