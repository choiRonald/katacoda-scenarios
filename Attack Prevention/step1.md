Setting up scenario environment:

`touch docker-compose.yml`{{execute}}

Click this button to open the docker-compose file:

`docker-compose.yml`{{open}}

Enter the template into the docker-compose file:

```sh
version: '3.2'
services:
    mysql-server:
      container_name: mysql
      command: mysqld --general-log=1 --log-output=TABLE

      ports:
        - "13306:3306"
      environment:
        MYSQL_ROOT_PASSWORD: 12345
        MYSQL_DATABASE: wordpress
        MYSQL_USER: wordpress_user
        MYSQL_PASSWORD: secret
      image: mysql/mysql-server

    wordpress:
      image: wordpress:latest
      container_name: wordpress
      ports:
        - "20080:80"
      environment:
        WORDPRESS_DB_HOST: mysql-server:3306
        WORDPRESS_DB_USER: wordpress_user
        WORDPRESS_DB_PASSWORD: secret
      depends_on:
        - mysql-server
```{{copy}}

Run the following command:

`docker-compose up -d`{{execute}}

In Katacoda, visit the WordPress website:

https://[[HOST_SUBDOMAIN]]-20080-[[KATACODA_HOST]].environments.katacoda.com/

Setup Wordpress following the instructions.