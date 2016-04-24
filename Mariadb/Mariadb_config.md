Mariadb config
===================

----------
#### <i class="icon-file"></i> Add user

> **Note:**

> - use mysql;
> - insert into mysql.user(Host,User,Password) values("localhost","xiejdm",password("pass"));
> - insert into mysql.user(Host,User,Password) values("127.0.0.1","xiejdm",password("pass"));


> **Tip:** 此处的"localhost"，是指该用户只能在本地登录，不能在另外一台机器上远程登录。

----------

#### <i class="icon-file"></i> update password
> - use mysql;
> - update mysql.user set password=password('pass') where User="xiejdm" and Host="localhost";
> - flush privileges;

----------

#### <i class="icon-file"></i> grant privileges
> - 格式：grant 权限 on 数据库.* to 用户名@登录主机 identified by "密码";　
> - use mysql;
> - # 授权所有first_db的所有权限给xiejdm
> - GRANT ALL PRIVILEGES ON first_db.* TO xiejdm@localhost IDENTIFIED BY 'pass';
> - # 授权first_db的SELECT, UPDATE权限给xiejdm
> - GRANT SELECT, UPDATE ON first_db.* TO xiejdm@localhost IDENTIFIED BY 'pass';
> - # 授予xiejdm用户以密码为pass在IP为：10.10.10.103下远程登陆权限
> - GRANT ALL PRIVILEGES ON *.* TO 'xiejdm'@'10.10.10.103' IDENTIFIED BY 'pass' WITH GRANT OPTION;
> - flush privileges;

> **Tip:** ALL PRIVILEGES = SELECT, DELETE, UPDATE, CREATE, DROP.

#### <i class="icon-file"></i> Ubuntu System update to 16.04

> **error info:** ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory

reslove method
: ```
xiejdm@xiejdm:~$ sudo apt-get install libmysqlclient18
xiejdm@xiejdm:~$ sudo apt autoremove
```

	> reference by: [serverfault.com](http://serverfault.com/questions/339334/screwed-libmysqlclient-dev-in-ubuntu)
	 
----------




### Support By Xiejdm

> **E-mail:** [xiejdm@gmail.com](mailto:xiejdm@gmail.com)    **Tel:**010-64089654
