FROM alpine

MAINTAINER Kwok Yao Chim <yaochim8@gmail.com>
LABEL Description="Funkykit Wordpress container" Author="Kwok Yao Chim <yaochim8@gmail.com>"

RUN apk update && apk upgrade && apk add apache2 php7-apache2 curl ca-certificates git \
	php7 \
	php7-xdebug \
	php7-phar \
	php7-mcrypt \
	php7-soap \
	php7-openssl \
	php7-gmp \
	php7-pdo_odbc \
	php7-json \
	php7-dom \
	php7-pdo \
	php7-zip \
	php7-mysqli \
	php7-sqlite3 \
	php7-pdo_pgsql \
	php7-bcmath \
	php7-gd \
	php7-odbc \
	php7-pdo_mysql \
	php7-pdo_sqlite \
	php7-gettext \
	php7-xmlreader \
	php7-xmlrpc \
	php7-bz2 \
	php7-iconv \
	php7-pdo_dblib \
	php7-curl \
	php7-ctype \
	php7-session \
	&& cp /usr/bin/php7 /usr/bin/php \
    && rm -f /var/cache/apk/* \
    &&  echo "ServerName localhost" >> /etc/apache2/httpd.conf  \
    && mkdir -p /run/apache2

EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
