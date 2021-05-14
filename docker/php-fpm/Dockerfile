FROM ubuntu:latest

# Install selected extensions
RUN apt-get update && apt-get -y install curl
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && apt-get install nodejs

RUN apt-get update \
    && apt-get install -y software-properties-common \
    && add-apt-repository ppa:ondrej/php \
    && apt-get update \
    && apt-get -y install php7.4-cli php7.4-fpm wget curl


RUN apt-get -y install  \
        php-apcu                \
        php-pear                \
        php-xdebug              \
        php-yaml                \
        php7.4-common           \
        php7.4-curl             \
        php7.4-intl             \
        php7.4-json             \
        php7.4-mbstring         \
        php7.4-opcache          \
        php7.4-phpdbg           \
        php7.4-readline         \
        php7.4-sqlite3          \
        php7.4-xml              \
        php7.4-zip              \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && rm composer-setup.php \
    && mv composer.phar /usr/bin/composer


RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

ADD ./php-fpm/pool-prod.conf /etc/php/7.4/fpm/pool.d/www.conf



WORKDIR "/var/www/demo"

RUN mkdir /run/php/
RUN npm install --global yarn

#COPY ./php-fpm/php-fpm-startup /usr/bin/php-fpm

CMD ["php-fpm7.4", "-F", "-R"]

