#linux管理相关
##centos(7.0)
###1.为其他用户配置sudo权限
*   1.$su(切换root账号)
*   2.$visudo(打开编辑sudo配置文件)
*   3.root ALL=(ALL) ALL 后面添加 (您的账号) ALL=(ALL) ALL wq保存退出即可

###2.gcc g++编译器安装
    sudo yum install gcc gcc-c++ -y

###3.references
1.[centos普通用户设置sudo权限](http://jingyan.baidu.com/article/49ad8bce77a0365834d8fa95.html)
##ubuntu