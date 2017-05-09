## MySQL install

https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-16-04
#Config remote acess
```
    Edit /etc/mysql/mysql.conf.d/mysqld.cnf
    bind-address            = 127.0.0.1
    and change it to:

    bind-address            = 0.0.0.0
    and restart mysql.

    on debian/ubuntu:

    /etc/init.d/mysql restart
    Open port for mysql: fefault is 3306
```

###Common command

- Login
    ```sh
    $ mysql -u root -p
    ```

- Add user
    ```sh
    mysql> CREATE USER 'panova'@'localhost' IDENTIFIED BY '******';
    ```

- Show database
    ```sh
    mysql> show datbases;
    ```
- Show users
    ```sh
    mysql> SELECT User FROM mysql.user;
    ```
- Grant on a database for a user
    ```sh
    mysql> GRANT ALL PRIVILEGES ON database_name.* TO 'panova'@'localhost';
    ```

- Grant all database for a user
    ```sh
    mysql> GRANT ALL ON *.* TO 'myuser'@'localhost';
    ```
- Grant all database for a user

    ```sh
    mysql>SHOW GRANTS FOR 'panova'@'localhost';
    mysql>FLUSH PRIVILEGES;
    ```

## SSH
```sh
ssh -i "panova-ubuntu01.pem" ubuntu@ec2-52-77-228-197.ap-southeast-1.compute.amazonaws.com
```

## HA configuration

### Reference

```
http://physalix.com/reverse-proxy-for-nodejs-in-production-with-apache2-haproxy-and-monit/
https://www.digitalocean.com/community/tutorials/how-to-use-haproxy-to-set-up-http-load-balancing-on-an-ubuntu-vps
https://www.upcloud.com/support/haproxy-load-balancer-centos/
https://evancarmi.com/writing/load-balance-multiple-ssl-sites-with-haproxy/
```