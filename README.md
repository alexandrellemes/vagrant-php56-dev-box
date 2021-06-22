# vagrant-php56-dev-box
Vagrant box com PHP56 para atender projetos antigos em PHP.

Set up a PHP development box super fast
=======================================

Installation
------------

* Install vagrant using the installation instructions in the [Getting Started document](http://vagrantup.com/v1/docs/getting-started/index.html)

* Clone this repository
* After running ```vagrant up``` 

* To activate a site:

Tree of this project


/vagrant-php56-dev-box
     
          /discoDocker

  +----- docker

         +---- Esse projeto.. Vagrant...

  +----- apache

         +---- conf
               +--- meu.projeto.dev.conf

         +---- projetos
     
               +------ meu.projeto.dev
         

vagrant ssh

sudo docker-compose exec php-apache sh -c "a2ensite meu.site.desenv"

sudo docker-compose exec php-apache sh -c "service apache2 reload"


Installed components
--------------------

* [Nginx](http://nginx.org) using puppet module (https://github.com/example42/puppet-nginx)
* [Apache](http://httpd.apache.org/) using puppet module (https://github.com/example42/puppet-apache)
* [php-fpm](http://php-fpm.org) using puppet module (https://github.com/saz/puppet-php)
* [git](http://git-scm.com/)
* [pear](http://pear.php.net/) using puppet module (https://github.com/rafaelfelix/puppet-pear)
* [Node.js](http://nodejs.org/)
* [npm](http://npmjs.org/)
* [less](http://lesscss.org/)
* [Symfony2 Standard Edition](https://github.com/symfony/symfony-standard)
* [MySQL](http://dev.mysql.com/downloads/mysql/) using puppet module (https://github.com/example42/puppet-mysql)
* [MongoDB](http://www.mongodb.org/) using puppet module (https://github.com/puppetlabs/puppetlabs-mongodb)
* [Capistrano](https://github.com/capistrano/capistrano)
* [capifony](http://capifony.org/)
* Most of the [phpqatools](http://www.phpqatools.org) using puppet module (https://github.com/rafaelfelix/puppet-phpqatools)

