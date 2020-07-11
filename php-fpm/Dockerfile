FROM julioarteta/php-fpm:7.2
MAINTAINER Julio R. Arteta<julioarteta93@gmail.com>

ARG uid
ARG gid

RUN echo "assigning www-data the uid $uid and gid $gid" && \
    usermod -u $uid www-data && \
    groupmod -g $gid www-data

RUN service php7.2-fpm start

COPY php-fpm.conf /etc/php/7.2/fpm/pool.d/www.conf
COPY php.ini /etc/php/7.0/mods-available/php.ini

WORKDIR /etc/php/7.2/fpm/conf.d/
RUN ln -s /etc/php/7.2/mods-available/php.ini 00-php.in


WORKDIR /var/www/html

CMD ["/usr/sbin/php-fpm7.2"]

