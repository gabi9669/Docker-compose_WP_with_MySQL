# Wordpress connected to MySQL with docker-compose file

This is a web hosting project with WordPress, that's connected to MySQL database.
After `vagrant up` it my takes some time until connections between containers stand up (like 5 min),
and after that your new WordPress is avaliable on localhost.

You can use this docker-compose file to stand up container on one machine, or you can use it on different computers, upping just one service.

In this case you have to specify one more environmental variable, what gives to your Wordpress the database address.

    WORDPRESS_DB_HOST: YOUR_DB_IP:3306;
In this case you dont nedd the `depends_on` part in the docker-compose yaml file

With these environmental variables you can specify your home page's URL.

    WORDPRESS_CONFIG_EXTRA: |-
      define('WP_HOME', 'YOUR_DOMAIN');
      define('WP_SITEURL', 'YOUR_DOMAIN');


!!!On linux system, you may have to change in the Vagratnfile the hosts port from 80 to something higher than 1024!!!

**Base requirements:**

 - git (https://git-scm.com/downloads)
 - Vagrant (https://www.vagrantup.com/downloads)
 - Virtualbox (https://www.virtualbox.org/wiki/Downloads)