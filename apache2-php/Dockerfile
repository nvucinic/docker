FROM nvucinic/base
MAINTAINER Neven Vucinic [neven.vucinic@gmail.com]

## Set noninteractive deb env

ENV DEBIAN_FRONTEND noninteractive

## Install apache2 

RUN apt-get update \ 
    && apt-get install -y apache2 \
     php5 \
     php5-json \
     php5-mysql \
     php5-xmlrpc \
     libxml2 \
     python-ctypes \
     python-ctypeslib \ 
    && apt-get clean \ 
    && rm -rf /var/lib/apt/lists/*

## Let's set the default timezone in apache config

RUN sed -i 's/\;date\.timezone\ \=/date\.timezone\ \=\ Europe\/Zagreb/g' /etc/php5/apache2/php.ini


## Set apache2 env

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/
ENV APACHE_LOCK_DIR /var/lock/
ENV APACHE_SERVERADMIN admin@localhost
ENV APACHE_SERVERNAME  myserver
ENV APACHE_SERVERALIAS  myserver.localhost
ENV APACHE_DOCUMENTROOT /var/www/html


## Expose ports 

EXPOSE 80 443

## Run apache 
CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]
