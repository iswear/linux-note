#nginx相关
##centos(7.0)
### nginx安装
+   1.$wget  http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm(下载nginx包)
+   2.$sudo rpm -ivh nginx-release-centos-7-0.el7.ngx.noarch.rpm(建立nginx的yum仓库)
+   3.$sudo yum install nginx -y(安装nginx)
+   4.$sudo systemctl start nginx(开启nginx服务)
+   5.$wget 127.0.0.1:80(测试nginx默认端口为80端口，配置文件/etc/nginx)

### nginx反向代理和负载均衡配置

### references
1.[nginx安装](http://jingyan.baidu.com/article/aa6a2c14dc36640d4d19c47e.html)
##ubuntu