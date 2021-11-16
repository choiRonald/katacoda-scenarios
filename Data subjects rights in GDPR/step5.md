## Example of empolyee

Logout admin account

`exit`{{execute}}

Login by using empolyee account

`mysql -u empolyee -p empolyee_password`{{execute}}

Show the databases and choose that

`show databases`{{execute}}

`use onlineshop.buyers`{{execute}}

We can insert a new product and buyers as a empolyee.
`insert into table product(product_id, quantity, details, price, product_name) values (123456789, 20, 'phone', 95714, iHome 87);`{{execute}}

`insert into table buyers(buyers_id, address, phone_no, buyers_name, number_buylist) values (20211116, 'Hell', 21800000, 'aka Harris', 1);`{{execute}}
