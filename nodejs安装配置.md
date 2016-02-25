# nodejs安装配置
## centos(7.0)
### nodejs安装
*   $cd /usr/local/software
*   $wget http://nodejs.org/dist/v0.12.7/node-v0.12.7-linux-x64.tar.gz
*   $tar zxvf node-v0.12.7-linux-x64.tar.gz
*   $vim /etc/profile 加上(export NODE_HOME=/usr/local/software/node-v0.12.7-linux-x64 export PATH=$NODE_HOME/bin:$PATH)
*   $source /etc/profile
*   $node -v

### helloworld测试
			$vim helloworld.js(输入console.log("hello world"); wq保存退出)
			$node helloworld.js
   
### references
1.[nodejs安装](http://www.runoob.com/nodejs/nodejs-install-setup.html)
## ubuntu
### nodejs安装
*   1.$sudo apt-get install nodejs   

### references