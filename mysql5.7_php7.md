# mysql
## check temporary password
```
sudo grep 'temporary' /var/log/mysqld.log
```

## change password
```
mysql -u root -p
alter user 'root'@'localhost' identified by 'NewPassword';
create user 'user-name' identified by 'Password';
create database 'db_name';
grant all on db_name.* to user-name;
```

# php
```
sudo mkdir /var/log/php-fpm
sudo systemctl start php70-php-fpm
```

