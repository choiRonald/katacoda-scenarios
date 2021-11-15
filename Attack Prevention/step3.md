## Privilege Abuse (Continue)

## MySQL encryption
Besides access Control and Account Management in database,we could also encrypt data at rest by using the folling command:

`UPDATE wordpress.wp_users SET user_email=HEX(AES_ENCRYPT(first_name, '1234'));`{{execute}}

Sample result:
![sqlencrypt](./assets/sqlencrypt.png)

Without the right key, even if user have access to the senitive information, they still could not decrypt the data.
