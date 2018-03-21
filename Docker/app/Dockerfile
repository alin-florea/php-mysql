FROM ubuntu:16.04
MAINTAINER alin.i.florea@gmail.com

ENV WEB_DOCUMENT_ROOT=/app \
    WEB_DOCUMENT_INDEX=index2.php \
    WEB_ALIAS_DOMAIN=*.vm \
    WEB_PHP_TIMEOUT=600 \
    WEB_PHP_SOCKET=""

COPY conf/ /opt/docker/

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install curl -y 
RUN set -x \
    # Install php environment
    && apt-get install \
        # Install tools
        imagemagick -y \
        graphicsmagick -y \
        ghostscript -y \
        # Install php (cli/fpm)
        php7.0-cli -y \
        php7.0-fpm -y \
        php7.0-json -y \
        php7.0-intl -y \
        php7.0-curl -y \
        php7.0-mysql -y \
        php7.0-mcrypt -y \
        php7.0-gd -y \
        php7.0-sqlite3 -y \
        php7.0-ldap -y \
        php7.0-opcache -y \
        php7.0-soap -y \
        php7.0-zip -y \
        php7.0-mbstring -y \
        php7.0-bcmath -y \
        php7.0-xmlrpc -y \
        php7.0-xsl -y \
        php7.0-bz2 -y \
        php-pearl -y \
        php-apcu -y \
        php-redis -y \
        php-memcached -y \
    && pecl channel-update pecl.php.net \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer \

EXPOSE 80
