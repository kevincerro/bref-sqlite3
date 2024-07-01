FROM composer:2 AS composer
FROM bref/extra-gd-php-80 as gdextra
FROM bref/extra-redis-php-80 as redisextra
FROM bref/php-80-fpm-dev
COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY --from=gdextra /opt /opt
COPY --from=redisextra /opt /opt

# Install unzip and git (required by composer)
RUN yum install -y unzip git

# Update SQLite3
RUN yum -y groupinstall "Development Tools" && yum -y install tar
RUN curl -O https://www.sqlite.org/2024/sqlite-autoconf-3460000.tar.gz && tar xzf sqlite-autoconf-3460000.tar.gz \
        && cd sqlite-autoconf-3460000 && ./configure && make && make install \
        && cd .. && rm -r ./sqlite-autoconf-3460000

WORKDIR /var/task
