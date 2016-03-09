#FastDFS安装配置#
##安装##
###autotool安装###
			sudo yum install autoconf(因安装libevent时需要)
###automake安装###
			sudo yum install automake(因安装libevent时需要)
###libtool安装###
			sudo yum install libtool(因安装libevent时需要)
###libevent安装(见文档)###
			sudo ./autogen.sh
			sudo ./configure
			sudo make
			sudo make install
###libfastcommon(见文档)###
			sudo ./make.sh
			sudo ./make.sh install
###安装步骤(请预先安装libevent libfastcommon)测试配置###
		./make.sh
		./make.sh install   
安装之后配置文件位于/etc/fdfs路径下，拷贝默认配置client.conf、storage.conf、tracker.conf，修改这三个配置文件:   
    1、client.conf主要配置tracker服务器地址、日志存放路径;   
    2、storage配置tracker服务器路径(不能设置为127.0.0.1可采用内网地址)、http端口、日志存放路径；   
    3、tracker配置绑定端口号、http端口号、日志存放路径;   
    4、启动tracker服务器和storage服务器:   
		
    	/usr/bin/fdfs_trackerd /etc/fdfs/tracker.conf restart
    	/usr/bin/fdfs_storaged /etc/fdfs/storage.conf restart
    	
###参考###
1、[libevent github链接](https://github.com/nmathewson/Libevent)   
2、[libfastcommon github链接](https://github.com/happyfish100/libfastcommon)   
3、[FastDfs github链接](https://github.com/happyfish100/fastdfs/releases)   
4、[http://www.cnblogs.com/adolfmc/p/4239575.html](http://www.cnblogs.com/adolfmc/p/4239575.html)(注意libevent软链接的添加否则可能会导致编译失败)  
5、压缩包内部INSTALL说明
##测试##
一、(OK)完成两台FastDFS F1、F2、F3的安装和配置；   
二、(OK)集群测试storage添加tracker添加等   
&nbsp;&nbsp;&nbsp;&nbsp;1、F1\_tracker作为tracker，F2\_tracker作为tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;2、F1\_storage、F2\_storage为group1，F3\_storage为group2;   
&nbsp;&nbsp;&nbsp;&nbsp;3、添加F1\_storage测试上传:tracker\_server为F1\_tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;4、添加F2\_storage测试上传:tracker\_server为F1\_tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;5、添加F3\_storage测试上传:tracker\_server为F1\_tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;6、添加F1\_storage测试上传:tracker\_server为F1\_tracker和F2\_tracker，分别测试F1\_tracker和F2\_tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;7、添加F2\_storage测试上传:tracker\_server为F1\_tracker和F2\_tracker，分别测试F1\_tracker和F2\_tracker;   
&nbsp;&nbsp;&nbsp;&nbsp;8、添加F3\_storage测试上传:tracker\_server为F1\_tracker和F2\_tracker，分别测试F1\_tracker和F2\_tracker;   

> 测试结果：同一个group的storage服务器之前互相复制，但是需要添加到同一个tracker服务器，否则上传时不会自动复制，但重启之后可能会自动拷贝同步,原则上一次性配置好,细节需要详读文档和配置文件,轮训应该是并发情况下轮训分发；   


##注意##
1、libevent安装之后链接设置；   
2、storage  tracker地址设置不能设置为127.0.0.1(5.05版本)；   
3、启动tracker、storage之后可以看下日志确认是否存在异常退出的情况；   
4、其他配置可以详见配置文件(很详细)；