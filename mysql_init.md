修改默认数据库
==============

依次执行下面命令

关闭 MySQL，启动 mysqld_safe

```sh
sudo /etc/init.d/mysqld start
sudo /etc/init.d/mysqld stop
cd /alidata/server/mysql-5.6.21/
sudo bin/mysqld_safe --skip-grant-tables &
```

进入数据库开始修改密码

```sh
mysql -u root
use mysql;
update user set password=PASSWORD("root") where User='root';
flush privileges;
quit
```


重启 MySQL

```sh
sudo /etc/init.d/mysqld stop
sudo /etc/init.d/mysqld start
```

参考文章：[MySQL - Resetting a lost MySQL root password](http://www.rackspace.com/knowledge_center/article/mysql-resetting-a-lost-mysql-root-password)
