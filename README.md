# ss-python

### 如果安装过程中提示master.zip下载失败，就把脚本中的链接改为本repo的source/master.zip

本脚本适用环境：

系统支持：CentOS 6，7，Debian，Ubuntu

内存要求：≥128M

使用方法：

使用root用户登录，运行以下命令：

wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/binghe3337/ss-python/master/shadowsocks.sh

chmod +x shadowsocks.sh

./shadowsocks.sh 2>&1 | tee shadowsocks.log

卸载方法：

使用root用户登录，运行以下命令：

./shadowsocks.sh uninstall

单用户配置文件示例：

配置文件路径：/etc/shadowsocks.json

{

    "server":"0.0.0.0",
    
    "server_port":your_server_port,
    
    "local_address":"127.0.0.1",
    
    "local_port":1080,
    
    "password":"your_password",
    
    "timeout":300,
    
    "method":"your_encryption_method",
    
    "fast_open": false
    
}

多用户多端口配置文件示例：

配置文件路径：/etc/shadowsocks.json

{

    "server":"0.0.0.0",
    
    "local_address":"127.0.0.1",
    
    "local_port":1080,
    
    "port_password":{
    
         "8989":"password0",
         
         "9001":"password1",
         
         "9002":"password2",
         
         "9003":"password3",
         
         "9004":"password4"
         
    },
    
    "timeout":300,
    
    "method":"your_encryption_method",
    
    "fast_open": false
    
}

使用命令：

启动：/etc/init.d/shadowsocks start

停止：/etc/init.d/shadowsocks stop

重启：/etc/init.d/shadowsocks restart

状态：/etc/init.d/shadowsocks status
