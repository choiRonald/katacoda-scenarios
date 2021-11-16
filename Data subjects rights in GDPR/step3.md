## About the privilege 

We would like use Onlineshop as a example to show you how to give difference privilege for difference users.

By using this command create the container.
`docker exec -it mysql /bin/sh`{{execute}}

We login the mysql with root and use 12345 as password
`mysql -u root -p 12345`{{execute}}

`create database onlineshop`{{execute}}

After that, we can create a table for onlineshop and with all these user or product, we give them some privilege. 

`create table employee(emp_id int NOT null, emp_name varchar(100) NOT null, gender varchar(5), position varchar(10), joining_date date)`{{execute}}

`create table product(product_id int, quantity int, details varchar(20), price int)`{{execute}}

`create table buyers(buyers_id int NOT null, address varchar(100), phone_no int, buyers_name varchar(50) NOT null, number_buylist int`{{execute}}


`create user 'admin'@'localhost' identified by 'admin_password';`{{execute}}

`create user 'manager'@localhost' identified by 'manager_password';`{{execute}}

`create user 'empolyee'@'localhost' identified by 'empolyee_password';`{{execute}}


`grant all privileges on onlineshop.* TO 'admin'@'localhost';`{{execute}}

`grant insert, delete, update, select on onlineshop.* TO 'manager'@'localhost';`{{execute}}

`grant update, insert, select on onlineshop.* TO 'empolyee'@'localhost';`{{execute}}

`flush privileges;`{{execute}}



