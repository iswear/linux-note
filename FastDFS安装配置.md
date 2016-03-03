#FastDFS安装配置#
##安装##
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
		/usr/bin/fdfs_test /etc/fdfs/client.conf upload <filepath>
##注意##
1、libevent安装之后链接设置；   
2、storage  tracker地址设置不能设置为127.0.0.1(5.05版本)；   
3、启动tracker、storage之后可以看下日志确认是否存在异常退出的情况；   
4、其他配置可以详见配置文件(很详细)；