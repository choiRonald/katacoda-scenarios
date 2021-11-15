## Privilege Abuse

It is known as abusing privilegs when a user misuses privilegs granted to them. To prevent user abuse privileges to access senitive data, appropriate access control should be done.

Access control could be done on Database and Woocommerce.

## Database Access Control and Account Management

To access the database:

`docker exec -it mysql bash`{{execute}}

`mysql -u root -p`{{execute}}

Use the password **12345** to login.

Different accounts should be set up as separation of duty so that no one have unnecessary privilege.

To create an account, use the following command(Note: Have a strong password):

`create user 'sample'@'localhost' identified by 'sample';`{{copy}}

In our case, we might have two different account, one for operation team and one for sales/marketing team.

`create user 'oper'@'localhost' identified by 'sample';`{{execute}}

`create user 'sales'@'localhost' identified by 'sample';`{{execute}}

Different privileges should be grant to these accounts. For example, operation team should have database administration power:

`grant all privileges on wordpress.* to 'oper'@'localhost';`{{execute}}

On the other hand, the sales team should not have such privileges, the sales team should not have the privileges to access customer PII and alter tables. Therefore, one of the privileges that could be grant to the sales team is:

`grant select on wordpress.wp_comments to 'sales'@'localhost';`{{execute}}