FROM php:7.2-apache

#COPY src/ /var/www/html/

# Install mysql-server
RUN apt update
RUN apt upgrade -y
RUN apt install -y zlib1g-dev libzip-dev libpng-dev
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install zip
RUN docker-php-ext-install gd

# Install limesurvey
RUN curl -o /tmp/limesurvey.tar.gz https://download.limesurvey.org/latest-stable-release/limesurvey3.17.8+190722.tar.gz 
RUN tar xvzf /tmp/limesurvey.tar.gz -C /var/www/html
RUN rm -rf /tmp/limesurvey.tar.gz
RUN chmod -R 777 /var/www/html/limesurvey/tmp
RUN chmod -R 777 /var/www/html/limesurvey/upload
RUN chmod -R 777 /var/www/html/limesurvey/application/config
