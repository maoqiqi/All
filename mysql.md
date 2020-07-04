Mac安装MySQL后，设置初始密码

```
2019-12-12T08:29:39.473967Z 1 [Note] A temporary password is generated for root@localhost: lAOvoNAX3K>0

If you lose this password, please consult the section How to Reset the Root Password in the MySQL reference manual.
```

```
mysql> show databases;
ERROR 1820 (HY000): You must reset your password using ALTER USER statement before executing this statement.
```

解决方式如下：

MySQL版本5.7.6版本以前用户可以使用如下命令：

```
SET PASSWORD = PASSWORD('root');
```

MySQL版本5.7.6版本开始的用户可以使用如下命令：

```
ALTER USER USER() IDENTIFIED BY 'root';
```


show databases;

use sys;

Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

show tables;

show tables from mysql;

select database();

create table stuinfo(id int,name varchar(20));

desc stuinfo;

select * from stuinfo;

insert into stuinfo(id,name) values(1,"jack");

update stuinfo set name='march' where id =1;

delete from stuinfo where id = 1;

select version();





mysql --version

mysql -V