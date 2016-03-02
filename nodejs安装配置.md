# nodejs安装配置
## centos(7.0)
### nodejs安装
			1.cd /usr/local/software
			2.wget http://nodejs.org/dist/v0.12.7/node-v0.12.7-linux-x64.tar.gz
			3.$tar zxvf node-v0.12.7-linux-x64.tar.gz
			4.vim /etc/profile 加上(export NODE_HOME=/usr/local/software/node-v0.12.7-linux-x64 export PATH=$NODE_HOME/bin:$PATH)
			5.$source /etc/profile
			6.$node -v

### helloworld测试
			$vim helloworld.js(输入console.log("hello world"); wq保存退出)
			$node helloworld.js
   
### references
1.[nodejs安装](http://www.runoob.com/nodejs/nodejs-install-setup.html)
## ubuntu
### nodejs安装
			1.$sudo apt-get install nodejs   

### references