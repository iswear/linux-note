#nginx相关#
##centos(7.0)##
###nginx安装###
			1.wget http://nginx.org/packages/centos/7/norach RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
			2.sudo rpm -ivh nginx-release-centos-7-0.el7.ngx.noarch.rpm
			3.sudo yum install nginx-y
			4.systemctl start nginx
			5.wget 127.0.0.1:80(测试)
			6.配置目录(/etc/nginx)

###nginx反向代理和负载均衡配置###
			1.sudo vim default.conf
			2.基本配置如下
			    upstream nodejsservers { 
			        127.0.0.1:8081;
			        127.0.0.1:8082;
			        127.0.0.1:8083;
			    }
			    server {
			        location / {
			            proxy_pass http://nodejsservers;
			            ....
			        }
			    }
		   3.反向代理错误(connect() to 127.0.0.1:8080 failed (13: Permission denied) while connect)
		       selinux造成，解决如下:[连接](http://www.hpboys.com/827.html)
		       最简单执行命令：setsebool -P httpd_can_network_connect 1
###references###
1.[nginx安装](http://jingyan.baidu.com/article/aa6a2c14dc36640d4d19c47e.html)

2.[nginx代理详细配置项](http://nginx.org/en/docs/http/ngx_http_proxy_module.html)
##ubuntu##