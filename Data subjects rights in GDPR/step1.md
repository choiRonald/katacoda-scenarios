There are two ways to run Wordpress in docker, by using command line or using docker-compose. Docker-compose is recommended in this scenario because our application includes mulitple container. It is easier to manage and reuse using docker-compose.

To create a docker-compose file, run the following command:

touch docker-compose.yml

Click this button to open the docker-compose file:

docker-compose.yml

Enter the template into the docker-compose file:

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
The docker-compose file specify the port, environment configuration and image for each container. To run docker compose, run the following command:

docker-compose up -d

In Katacoda, visit the WordPress website:

https://2886795282-20080-elsy05.environments.katacoda.com/

