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

1. Create a configuration file of your site (virtualhost) on the path: discoDocker/apache/conf.
2. Activate your site:

$ vagrant ssh

$ sudo docker-compose exec php-apache sh -c "a2ensite meu.site"

$ sudo docker-compose exec php-apache sh -c "service apache2 reload"

3. Change your local file hosts:
    - Windows: 
      - \Windows\System32\drivers\etc\hosts
    - Linux: 
      - /etc/hosts   

4. Access by browser your application.

This scripts contains:
  - info.php
    - Information abou your Apache Server.
    
  - mysqltest.php
    - A brief test on your MySQL Server.
    
  - oracletest.php
    - A brief test on you Oracle Server.

  - postgrestest.php
    - A brief test on your PostGreSQL Server.
    
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

