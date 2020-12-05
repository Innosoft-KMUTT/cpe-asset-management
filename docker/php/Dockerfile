#php ใช้ version 7.1 สามารถเปลี่ยนได้ตามที่เราต้องการแต่ต้องเป็นตัว fpm นะครับ เพื่อที่จะให้กับ nginx
FROM php:7.4-fpm 

#Install required package from laravel
RUN apt-get update \
	&& apt-get install -y \
	cron \
	libfreetype6-dev \
	libicu-dev \
	libjpeg62-turbo-dev \
	libmcrypt-dev \
	libpng12-dev \
	libxslt1-dev \
	openssh-server \
	openssh-client \
	rsync

RUN docker-php-ext-configure \
	gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

#Install php package
RUN docker-php-ext-install \
	bcmath \
	gd \
	intl \
	mbstring \
	mcrypt \
	pdo_mysql \
	soap \
	xsl \
	zip

#Install composer php package manager
RUN curl -sS https://getcomposer.org/installer | \
	php -- --install-dir=/usr/local/bin --filename=composer