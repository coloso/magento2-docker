# Magento2 Docker Development Stack
This is an lightweight stack, based on Alpine Linux for running Magento2 into Docker containers using docker-compose.

### Prerequisites
 - [Docker](https://www.docker.com/)

### Container
 - [nginx](https://hub.docker.com/_/nginx/) 1.15.+
 - [php-fpm](https://hub.docker.com/_/php/) 7.2.+
 - [mysql](https://hub.docker.com/_/mysql/) 5.7.+

### Installing

#### get your authentication keys
First get your authentication keys [here](https://devdocs.magento.com/guides/v2.3/install-gde/prereq/connect-auth.html). 
<br>You will need your `public key` as user and `private key` as password.

#### run docker and connect to container:

```
docker-compose up --build
```

```
docker-compose exec php sh
```

#### install with composer:
```
composer create-project --repository=https://repo.magento.com/ magento/project-community-edition .
``` 

#### replace in magento/nginx.conf.sample the fast
`fastcgi_backend` with `php-upstream`

#### using web setup wizard
http://localhost/setup