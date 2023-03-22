FROM php:7.1-fpm

RUN apt-get update -yqq && \
    curl -sL https://deb.nodesource.com/setup_12.x | bash -

RUN apt-get install -yqq \
    curl \
    nodejs

RUN curl -sSLf \
    -o /usr/local/bin/install-php-extensions \
    https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
    chmod +x /usr/local/bin/install-php-extensions
RUN install-php-extensions gd
RUN install-php-extensions intl curl json
RUN install-php-extensions mysqli pdo_mysql
RUN install-php-extensions pdo_odbc pdo_sqlsrv pdo_dblib odbc sqlsrv
RUN install-php-extensions ldap
RUN install-php-extensions bz2
RUN install-php-extensions decimal
RUN install-php-extensions exif
RUN install-php-extensions gettext gmp gnupg imagick imap memcache
RUN install-php-extensions oauth opcache opcache
RUN install-php-extensions pgsql redis
RUN install-php-extensions soap
RUN install-php-extensions xml
RUN install-php-extensions zip
RUN install-php-extensions snappy && \
    apt-get update -yqq && apt-get install wkhtmltopdf -yqq

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer self-update --1

ARG TIMEZONE
RUN ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && echo ${TIMEZONE} > /etc/timezone \
    && printf '[PHP]\ndate.timezone = "%s"\n', ${TIMEZONE} > /usr/local/etc/php/conf.d/tzone.ini \
    && "date"

ADD ./laravel.ini /usr/local/etc/php/conf.d
RUN rm -r /var/lib/apt/lists/*
RUN usermod -u 1000 www-data

WORKDIR /var/www/html

EXPOSE 9000
CMD ["php-fpm"]
