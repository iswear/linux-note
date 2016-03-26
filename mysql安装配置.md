#mysql安装配置#
##安装##
			1、wget http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm
			2、rpm -Uvh mysql157-community-release-el7-7.noarch.rpm
			3、yum install mysql-community-server -y
配置文件路径/etc/my.cnf
##忘记密码修改##
			1、sudo vim /etc/my.cnf
			2、mysqld添加如下行skip-grant-tables
			3、保存退出重启登录mysql
			4、use mysql;
			5、update set Password=PASSWORD('yourpassword') WHERE User='root';
			6、改回配置然后新用户和密码登录

##参考##
1、[Mysql官方网站](http://dev.mysql.com/doc/mysql-yum-repo-quick-guide/en/)


