# vagrant-php56-dev-box
Vagrant box com PHP56 para atender projetos antigos em PHP.

Configure uma caixa de desenvolvimento de PHP super rápido
===============================================

Instalação
------------

* Instale o vagrant usando as instruções de instalação no [documento Getting Started] (http://vagrantup.com/v1/docs/getting-started/index.html)

* Clone este repositório
* Depois de executar o `` `vagrant up```

* Para ativar um site:

1. Crie um arquivo de configuração do seu site (virtualhost) no caminho: discoDocker / apache / conf.
2. Ative seu site:

$ vagrant ssh

$ sudo docker-compose exec php-apache sh -c "a2ensite meu.site"

$ sudo docker-compose exec php-apache sh -c "service apache2 reload"

3. Altere seus hosts de arquivos locais:
    - Janelas:
        - \ Windows \ System32 \ drivers \ etc \ hosts
    - Linux:
        - / etc / hosts

4. Acesse pelo navegador seu aplicativo.

Este script contém:
- info.php
    - Informações sobre o seu servidor Apache.

- mysqltest.php
    - Um breve teste em seu servidor MySQL.

- oracletest.php
    - Um breve teste em seu servidor Oracle.

- postgrestest.php
    - Um breve teste em seu servidor PostGreSQL.

Componentes instalados
--------------------

* [Nginx] (http://nginx.org) usando o módulo fantoche (https://github.com/example42/puppet-nginx)
* [Apache] (http://httpd.apache.org/) usando o módulo fantoche (https://github.com/example42/puppet-apache)
* [php-fpm] (http://php-fpm.org) usando o módulo fantoche (https://github.com/saz/puppet-php)
* [git] (http://git-scm.com/)
* [pear] (http://pear.php.net/) usando o módulo fantoche (https://github.com/rafaelfelix/puppet-pear)
* [Node.js] (http://nodejs.org/)
* [npm] (http://npmjs.org/)
* [menos] (http://lesscss.org/)
* [Symfony2 Standard Edition] (https://github.com/symfony/symfony-standard)
* [MySQL] (http://dev.mysql.com/downloads/mysql/) usando o módulo fantoche (https://github.com/example42/puppet-mysql)
* [MongoDB] (http://www.mongodb.org/) usando o módulo fantoche (https://github.com/puppetlabs/puppetlabs-mongodb)
* [Capistrano] (https://github.com/capistrano/capistrano)
* [capifony] (http://capifony.org/)
* A maioria dos [phpqatools] (http://www.phpqatools.org) usando o módulo fantoche (https://github.com/rafaelfelix/puppet-phpqatools)