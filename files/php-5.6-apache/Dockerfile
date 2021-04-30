# DockerFile
#FROM debian:8
#FROM ubuntu:latest
FROM ubuntu:20.04

#FROM debian:latest
#FROM debian:latest

#Variáveis de ambiente
ARG HOME
ARG URL_PROXY
ARG DEBIAN_FRONTEND=noninteractive
ARG PHP_VERSION

ENV PASTA_TEMPORARIA /tmp

#COPY ./source.list.ubuntu.20.04.txt /etc/apt/sources.list
#
#RUN cat /etc/resolv.conf
#
#RUN cat /etc/apt/sources.list

# Install.
RUN \
#  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y byobu curl git htop man unzip vim wget && \
  rm -rf /var/lib/apt/lists/*

RUN apt update
RUN apt upgrade -y

RUN echo $PHP_VERSION

# Utilities...
RUN apt-get install -y apt-utils
RUN apt install -y gnupg2
#RUN apt install gpgv -y
RUN apt install -y gnupg1
RUN apt install -y software-properties-common
RUN apt install -y zip
RUN apt install -y unzip
RUN apt install -y vim
RUN apt install -y lsof
RUN apt install -y net-tools
RUN apt install -y htop
RUN apt install -y curl
RUN apt install -y wget
RUN apt install -y git
RUN apt install -y ssh
RUN apt install -y iputils-ping
RUN apt install -y bash-completion
RUN apt install -y build-essential
RUN apt install -y gcc
RUN apt install -y gcc+
RUN apt install -y make
RUN apt install -y libaio1
RUN apt install -y telnet
RUN apt install -y lynx

# Biblioteca Xrender
RUN apt install -y libfontconfig1 libxrender1

#
# Caso seja definido a configuração de PROXY.
#
#ENV http_proxy ${URL_PROXY}
#ENV ftp_proxy ${URL_PROXY}
#ENV all_proxy ${URL_PROXY}
#ENV https_proxy ${URL_PROXY}
#ENV no_proxy localhost,127.0.0.1
#ENV HTTP_PROXY ${URL_PROXY}
#ENV FTP_PROXY ${URL_PROXY}
#ENV ALL_PROXY ${URL_PROXY}
#ENV HTTPS_PROXY ${URL_PROXY}

# Realiza a cópia do resolv para acessar a internet.
#COPY resolv.conf /etc/

#Ubuntu
RUN apt-get install -y software-properties-common
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/apache2
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php

# Debian
#RUN LC_ALL=C.UTF-8 add-apt-repository packages.sury.org/php
#RUN apt -y install lsb-release apt-transport-https ca-certificates
#RUN wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
#RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list

RUN apt-get update

# Instala as versões de PHP
#RUN apt install -y php${PHP_VERSION} php${PHP_VERSION}-cli php${PHP_VERSION}-dev php${PHP_VERSION}-xml \
#                   php${PHP_VERSION}-soap php${PHP_VERSION}-xmlrpc php${PHP_VERSION}-curl php${PHP_VERSION}-gd \
#                   php${PHP_VERSION}-mbstring php${PHP_VERSION}-zip php${PHP_VERSION}-opcache php${PHP_VERSION}-json \
#                   php${PHP_VERSION}-common php${PHP_VERSION}-ldap php${PHP_VERSION}-intl php${PHP_VERSION}-imap
#
#RUN apt install -y php php-cli php-dev php-cgi php-pear apache2 php-mysql php-pgsql php-odbc php-mail php-memcached php-memcache \
#                   php-gd php-xdebug php-bcmath php-sqlite3 php-soap php-curl php-xml php-xmlrpc php-mbstring \
#                   php-intl php-json php-zip php-apcu php-imagick php-redis php-common php-fpm libphp-phpmailer \
#                   php-cas php-db php-solr pear-channels libmcrypt-dev libaio1

# Instala as versões de PHP
RUN apt install -y php5.6 php5.6-cli php5.6-dev php5.6-xml php5.6-soap php5.6-xmlrpc php5.6-curl php5.6-gd php5.6-mbstring php5.6-mcrypt php5.6-zip php5.6-opcache php5.6-json php5.6-common php5.6-ldap php5.6-intl
#RUN apt install -y php7.0 php7.0-cli php7.0-dev php7.0-xml php7.0-soap php7.0-xmlrpc php7.0-curl php7.0-gd php7.0-mbstring php7.0-mcrypt php7.0-zip php7.0-opcache php7.0-json php7.0-common php7.0-ldap php7.0-intl
#RUN apt install -y php7.1 php7.1-cli php7.1-dev php7.1-xml php7.1-soap php7.1-xmlrpc php7.1-curl php7.1-gd php7.1-mbstring php7.1-mcrypt php7.1-zip php7.1-opcache php7.1-json php7.1-common php7.1-ldap php7.1-intl
#RUN apt install -y php7.2 php7.2-cli php7.2-dev php7.2-xml php7.2-soap php7.2-xmlrpc php7.2-curl php7.2-gd php7.2-mbstring               php7.2-zip php7.2-opcache php7.2-json php7.2-common php7.2-ldap php7.2-intl
#RUN apt install -y php7.3 php7.3-cli php7.3-dev php7.3-xml php7.3-soap php7.3-xmlrpc php7.3-curl php7.3-gd php7.3-mbstring               php7.3-zip php7.3-opcache php7.3-json php7.3-common php7.3-ldap php7.3-intl
#RUN apt-cache search php7.4
#RUN apt install -y php7.4 php7.4-cli php7.4-dev php7.4-xml php7.4-soap php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-mbstring               php7.4-zip php7.4-opcache php7.4-json php7.4-common php7.4-ldap php7.4-intl
#RUN apt-cache search php8.0
#RUN apt install -y php8.0 php8.0-cli php8.0-dev php8.0-xml php8.0-soap php8.0-curl php8.0-gd php8.0-mbstring                php8.0-zip php8.0-opcache php8.0-common php8.0-ldap php8.0-intl

RUN apt install -y php5.6-bcmath php5.6-curl php5.6-pgsql php5.6-mysql php5.6-memcache
#RUN apt install -y php7.0-bcmath php7.0-curl php7.0-pgsql php7.0-mysql
#RUN apt install -y php7.1-bcmath php7.1-curl php7.1-pgsql php7.1-mysql
#RUN apt install -y php7.2-bcmath php7.2-curl php7.2-pgsql php7.2-mysql
#RUN apt install -y php7.3-bcmath php7.3-curl php7.3-pgsql php7.3-mysql
#RUN apt install -y php7.4-bcmath php7.4-curl php7.4-pgsql php7.4-mysql
#RUN apt install -y php8.0-bcmath php8.0-curl php8.0-pgsql php8.0-mysql

#RUN apt install -y php php-cli php-dev php-cgi php-pear apache2 php-mysql php-pgsql php-odbc php-mail php-memcached php-memcache \
#                   php-gd php-xdebug php-bcmath php-sqlite3 php-soap php-curl php-xml php-xmlrpc php-mbstring \
#                   php-intl php-json php-zip php-apcu php-imagick php-redis php-common php-fpm libphp-phpmailer \
#                   php-cas php-db php-solr pear-channels libmcrypt-dev mysql-client sqlite3

# Instala a biblioteca em todas as versões.
RUN apt update
#RUN apt-get -y upgrade
#RUN apt install -y php5.6-bcmath php7.0-bcmath php7.1-bcmath php7.2-bcmath php7.3-bcmath php7.4-bcmath

# PECL proxy
#RUN pear config-set http_proxy ${URL_PROXY}
RUN pecl channel-update pecl.php.net

# Desabilita o módulo PHP no apache2.
RUN a2dismod php5.6
#RUN a2dismod php7.0
#RUN a2dismod php7.1
#RUN a2dismod php7.2
#RUN a2dismod php7.3
#RUN a2dismod php7.4
#RUN a2dismod php8.0

# Habilita o módulo PHP no apache2
RUN a2enmod php${PHP_VERSION}

# Define a versão a ser utilizada.
#RUN update-alternatives --set php /usr/bin/php${PHP_VERSION}
#RUN update-alternatives --set phar /usr/bin/phar${PHP_VERSION}
#RUN update-alternatives --set phar.phar /usr/bin/phar.phar${PHP_VERSION}
#RUN update-alternatives --set phpize /usr/bin/phpize${PHP_VERSION}
#RUN update-alternatives --set php-config /usr/bin/php-config${PHP_VERSION}
#RUN update-alternatives --config php

RUN apt-get install -y php${PHP_VERSION}-pgsql php${PHP_VERSION}-mysql php${PHP_VERSION}-odbc php${PHP_VERSION}-sqlite3

# Install the Oracle Instant Client
RUN mkdir /opt/oracle
#ADD oracle/instantclient-basiclite-linux.x64-12.2.0.1.0.zip /opt/oracle
ADD oracle/instantclient-basic-linux.x64-12.2.0.1.0.zip /opt/oracle
ADD oracle/instantclient-sdk-linux.x64-12.2.0.1.0.zip /opt/oracle
ADD oracle/instantclient-sqlplus-linux.x64-12.2.0.1.0.zip /opt/oracle

RUN unzip /opt/oracle/instantclient-basic-linux.x64-12.2.0.1.0.zip -d /opt/oracle
RUN unzip /opt/oracle/instantclient-sdk-linux.x64-12.2.0.1.0.zip -d /opt/oracle
RUN unzip /opt/oracle/instantclient-sqlplus-linux.x64-12.2.0.1.0.zip -d /opt/oracle

#Links simbólicos
RUN ln -s /opt/oracle/instantclient_12_2 /usr/local/instantclient
RUN ln -s /opt/oracle/instantclient_12_2 /opt/oracle/instantclient

RUN ln -s /opt/oracle/instantclient_12_2/libclntsh.so.12.1 /opt/oracle/instantclient_12_2/libclntsh.so
RUN ln -s /opt/oracle/instantclient_12_2/libocci.so.12.1 /opt/oracle/instantclient_12_2/libocci.so
RUN ln -s /opt/oracle/instantclient_12_2/sqlplus /usr/bin/sqlplus

RUN echo /opt/oracle/instantclient_12_2 > /etc/ld.so.conf.d/oracle-instantclient
RUN cd /opt/oracle && ldconfig

RUN chown -R root:www-data /opt/oracle

# Install the OCI8 PHP extension
#Use 'pecl install oci8' to install for PHP 8.
#
#Use 'pecl install oci8-2.2.0' to install for PHP 7.
#
#Use 'pecl install oci8-2.0.12' to install for PHP 5.2 - PHP 5.6.
#
#Use 'pecl install oci8-1.4.10' to install for PHP 4.3.9 - PHP 5.1.
#RUN echo 'shared,instantclient,/opt/oracle/instantclient_12_2' | pecl install -f oci8
RUN echo 'shared,instantclient,/opt/oracle/instantclient_12_2' | pecl install -f oci8-2.0.12

# Set up the Oracle environment variables
ENV ORACLE_HOME /opt/oracle/instantclient_12_2
ENV TNS_ADMIN /opt/oracle/instantclient_12_2
ENV LD_LIBRARY_PATH /opt/oracle/instantclient_12_2
ENV PATH=/opt/oracle/instantclient_12_2/bin:$PATH
ENV C_INCLUDE_PATH=/opt/oracle/instantclient_12_2/sdk/include

RUN echo "export LD_LIBRARY_PATH=/opt/oracle/instantclient_12_2" >> /etc/apache2/envvars
RUN echo "export ORACLE_HOME=/opt/oracle/instantclient_12_2" >> /etc/apache2/envvars
RUN echo "LD_LIBRARY_PATH=/opt/oracle/instantclient_12_2:$LD_LIBRARY_PATH" >> /etc/environment


# Install the uploadprogress PHP Function.
# Install php-apcu to running php-uploadprogress
#RUN apt install -y php-uploadprogress
#RUN pecl install uploadprogress
RUN apt install php5.6-uploadprogress

#Install mcrypt for PHP >= 7.2 and <= 8.0.0
#RUN pecl install mcrypt

# Configuracao XDEBUG e OCI8.
COPY xdebug.ini /etc/php/5.6/mods-available/
#COPY xdebug.ini /etc/php/7.0/mods-available/
#COPY xdebug.ini /etc/php/7.1/mods-available/
#COPY xdebug.ini /etc/php/7.2/mods-available/
#COPY xdebug.ini /etc/php/7.3/mods-available/
#COPY xdebug.ini /etc/php/7.4/mods-available/
#COPY xdebug.ini /etc/php/8.0/mods-available/
#COPY xdebug.ini /etc/php/${PHP_VERSION}/mods-available/

COPY oci8.ini /etc/php/5.6/mods-available/
#COPY oci8.ini /etc/php/7.0/mods-available/
#COPY oci8.ini /etc/php/7.1/mods-available/
#COPY oci8.ini /etc/php/7.2/mods-available/
#COPY oci8.ini /etc/php/7.3/mods-available/
#COPY oci8.ini /etc/php/7.4/mods-available/
#COPY oci8.ini /etc/php/8.0/mods-available/
#COPY oci8.ini /etc/php/${PHP_VERSION}/mods-available/

COPY uploadprogress.ini /etc/php/5.6/mods-available/
#COPY uploadprogress.ini /etc/php/7.0/mods-available/
#COPY uploadprogress.ini /etc/php/7.1/mods-available/
#COPY uploadprogress.ini /etc/php/7.2/mods-available/
#COPY uploadprogress.ini /etc/php/7.3/mods-available/
#COPY uploadprogress.ini /etc/php/7.4/mods-available/
#COPY uploadprogress.ini /etc/php/8.0/mods-available/
#COPY uploadprogress.ini /etc/php/${PHP_VERSION}/mods-available/


# Desabilita a obrigatoriedade do uso da tag <?php. Pode-se usar: <? -- SEI não funciona no padrão <?php
RUN find /etc/php -name php.ini -exec sed -i -e 's/short_open_tag = Off/short_open_tag = On/g' {} \;

# Insere a pasta (infra_php) no path de pesquisa no final do php.ini.
RUN find /etc/php -name php.ini -exec sed -i -e '$a\' -e 'include_path = ".:/var/www/html/sei/infra/infra_php"' {} \;

# Configura o ServerName para o apache2
RUN echo "ServerName 127.0.0.1" >> /etc/apache2/apache2.conf

# Enable Apache2 modules
RUN a2enmod rewrite

# Habilita modulos PHP
RUN phpenmod oci8
RUN phpenmod xdebug
RUN phpenmod uploadprogress
RUN phpenmod mcrypt

ENV PHP_DIR /etc/php

# Habilita o POST 80MB
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/post_max_size = 8M/post_max_size = 80M/g' {} \;

# Habilita upload de arquivos com 20MB
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/upload_max_filesize = 2M/upload_max_filesize = 20M/g' {} \;

# Habilita o número máximo de arquivos para upload em 4.
#RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/max_file_uploads = 20/max_file_uploads = 4/g' {} \;

# Habilita PHP a gravar a sessão no memcache
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/session.save_handler = files/session.save_handler = memcache/g' {} \;
#RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/session.save_handler = files/session.save_handler = memcached/g' {} \;

# Habilita o caminho da sessão para o memcache
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/;session.save_path = "\/var\/lib\/php\/sessions"/session.save_path = "tcp:\/\/memcached:11211"/g' {} \;
#RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/;session.save_path = "\/var\/lib\/php\/sessions"/session.save_path = "memcached:11211"/g' {} \;

# Habilita as mensagens de erros do PHP
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/display_errors = Off/display_errors = On/g' {} \;
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/display_startup_errors = Off/display_startup_errors = On/g' {} \;

# Define o TIMEZONE para America/Sao_Paulo
RUN find ${PHP_DIR} -name php.ini -exec sed -i -e 's/;date.timezone =/date.timezone = America\/Sao_Paulo/g' {} \;

# Define a versão a ser utilizada.
#RUN update-alternatives --set php /usr/bin/php${PHP_VERSION}

# Reinicializa os servicos
RUN service apache2 restart

# Set up the Apache2 environment variables
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

# Install NodeJS

# Last version
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -

#RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -

# Install NodeJS
RUN apt install -y nodejs

# Uso do NPM com proxy.
#RUN npm config set registry=http://registry.npmjs.org
#RUN npm config set proxy=${URL_PROXY}
#RUN npm config set https-proxy=${URL_PROXY}
#RUN npm config set http-proxy=${URL_PROXY}
#RUN npm config set strict-ssl=false

# Install source code
#RUN apt install -y build-essential

# Install NVM
#RUN curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh -o install_nvm.sh

#RUN bash install_nvm.sh
#RUN source ~/.profile

#Install yarn
RUN npm install -g yarn

# install dependency
RUN yarn install

# Build for development
#RUN yarn run dev
# or yarn run watch
#RUN yarn run prod # or yarn run watch

#Install Java
RUN apt-get install -y default-jre
RUN apt-get install -y default-jdk
RUN ln -s /usr /opt/java
RUN echo 'JAVA_HOME="/usr/lib/jvm/default-java"' >> /etc/environment
#RUN source /etc/environment#


#Retira a configuração de proxy.
#ENV http_proxy ''
#ENV ftp_proxy ''
#ENV all_proxy ''
#ENV https_proxy ''
#ENV no_proxy localhost,127.0.0.1
#ENV HTTP_PROXY ''
#ENV FTP_PROXY ''
#ENV ALL_PROXY ''
#ENV HTTPS_PROXY ''

# Add www-data user/group with uid/gid 1000.
# This is a workaround for boot2docker issue #581, see
# https://github.com/boot2docker/boot2docker/issues/581
#RUN adduser -u 1000 www-data

#USER www-data

# Instala o composer
COPY composer.phar /usr/bin/composer

RUN export PATH=${PATH}:~/.composer/vendor/bin

# Define o timezone.
ENV TZ 'America/Sao_Paulo'
RUN echo $TZ > /etc/timezone && \
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    apt-get update && apt-get install -y tzdata && \
    dpkg-reconfigure -f noninteractive tzdata

RUN service apache2 restart

WORKDIR /var/www

EXPOSE 80 443

# Run Apache2 in Foreground
CMD /usr/sbin/apache2ctl -D FOREGROUND

