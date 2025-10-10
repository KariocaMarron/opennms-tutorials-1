# README

## wordpress

simple docker compose example for wordpress using the officiel docker wordpress image


The docker community provides a wordpress image maintained by docker

* docker hub page : https://hub.docker.com/_/wordpress
* git repo: https://github.com/docker-library/wordpress/

This is the Git repo of the Docker "Official Image" for wordpress (not to be confused with any official wordpress image provided by wordpress upstream)

the docker init file is modified to allow environment injection

https://github.com/docker-library/wordpress/blob/master/wp-config-docker.php

also possible to inject additional config using WORDPRESS_CONFIG_EXTRA:
https://github.com/docker-library/wordpress/pull/142  Here's an excerpt from a multisite docker-compose.yaml with
``` 
WORDPRESS_CONFIG_EXTRA: |
        /* Multisite */
        define('WP_ALLOW_MULTISITE', true );
        define('MULTISITE', true);
        define('SUBDOMAIN_INSTALL', false);
        define('DOMAIN_CURRENT_SITE', 'localhost'); // TODO: change to actual domain when deploying
        define('PATH_CURRENT_SITE', '/');
        define('SITE_ID_CURRENT_SITE', 1);
        define('BLOG_ID_CURRENT_SITE', 1);
```