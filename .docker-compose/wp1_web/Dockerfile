FROM wordpress:4.8-php7.1-apache

MAINTAINER Majid Abdolhosseini <majid8911303@gmail.com>

ARG WWW_DATA_USER_ID

RUN usermod -u ${WWW_DATA_USER_ID} www-data \
    && groupmod -g ${WWW_DATA_USER_ID} www-data

RUN apt-get update && \
	apt-get install -y  --no-install-recommends ssl-cert && \
	rm -r /var/lib/apt/lists/* && \
	a2enmod ssl && \
	a2ensite default-ssl && \
	a2enmod rewrite && \
    echo "\nServerName localhost\n" >> /etc/apache2/apache2.conf

EXPOSE 80
EXPOSE 443
