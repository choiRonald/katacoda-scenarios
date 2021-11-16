## Example of admin 

Logout root account

`exit`{{execute}}

Login by using admin account

`mysql -u admin -p admin_password`{{execute}}

Show the databases and choose that

`show databases`{{execute}}

`use onlineshop`{{execute}}

As a admin, he is able to insert a table on the database, for example, he can insert a new table on the database.

`INSERT table order_list(product_name int, product_no int NOT null, date date, buyer_address varchar(100) NOT null)`{{execute}}

`INSERT table total_storage(quantity int, store_location int, product_left int)`{{execute}}

You can input these command to see all privileges of each users such as empolyee, manager, admin.

`show grants for 'empolyee'@'localhost';`{{execute}}

`show grants for 'manager'@'localhost';`{{execute}}

`show grants for 'admin'@'localhost';`{{execute}}