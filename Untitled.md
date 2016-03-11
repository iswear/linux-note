#Redis相关
##CENTOS安装##
			wget http://download.redis.io/releases/redis-stable.tar.gz
			tar -zxvf redis-stable.tar.gz
			sudo make
			sudo make install
			cd utils
			sudo ./install_server.sh
			cd /etc/init.d
			./redis_xxxx start
			./redis_xxxx stop