FROM php:8-apache

ENV ACCEPT_EULA=Y

RUN a2enmod rewrite

RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    libxslt-dev \
    gnupg

RUN DEBIAN_FRONTEND=noninteractive apt-get update \
    && curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
    && curl https://packages.microsoft.com/config/debian/11/prod.list \
        > /etc/apt/sources.list.d/mssql-release.list \
    && apt-get install -y --no-install-recommends \
        locales \
        apt-transport-https \
    && echo "en_US.UTF-8 UTF-8" > /etc/locale.gen \
    && locale-gen \
    && apt-get update \
    && apt-get -y --no-install-recommends install \
        unixodbc-dev \
        msodbcsql17

RUN docker-php-ext-install mbstring exif pcntl bcmath gd xsl \
&& pecl install sqlsrv pdo_sqlsrv \
&& docker-php-ext-enable sqlsrv pdo_sqlsrv

COPY 000-default.conf /etc/apache2/sites-available/000-default.conf

RUN chown www-data:www-data /var/*

RUN chmod 777 /var/*

COPY --chown=www-data:www-data QuickDbTest.php /var/www/html/

CMD ["apache2-foreground"]