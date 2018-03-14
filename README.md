# Magento vanilla - Application (beta)

It's possible to deploy this application in two "enviroments":

- magento-vanilla
   + Simple deployment that builds a magento installation on the fly without persistence (removes everything in the drive and reinstall magento all the time )
   + Useful to have a magento vanilla to check things or test modules
- magento-vanilla-dev
   + Magento deployment with persistence
   + Volumes are mounted on the folder $HOME/var/data/k8s/ to let the developer work on the code
   + There's a port opened to connect to the DB 
   + 

Both enviroments are isolated in a kubernetes namespace splitting elements to avoid conflicts

## Common commands

### Deploy
~~~
bin/deploy {enviroment}
~~~

### Destroy
~~~
bin/destroy {enviroment}
~~~

## Docker images used
- docker.io/alphasocket/httpd-alpine - Webserver
- docker.io/alphasocket/php-fpm-alpine - PHP engine
- docker.io/alphasocket/magento-vanilla-alpine - Magento-cli ( cron, test, util runner )
- docker.io/alphasocket/redis-alpine - Session-cacher
- docker.io/alphasocket/varnish-alpine - Http-accelerator
- mariadb - DB
- docker.io/alphasocket/mariadb-alpine - Alternative DB 

## Next features
- Add varnish-dashboard
- Package application in helm chart


