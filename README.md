# proxifier-linux

proxyfier alternative for linux using redsocks. Proxify all linux applications through SOCKS4/5, HTTP proxy

命令行代理全局流量，通过iptables规则转发。

本地会监听 `12345` 端口，默认仅转发`80`、`443`端口。要转发其他端口，自行修改 `set-iptables`中`OUTPUT`部分。

Http/socks5的代理服务，推荐使用clash，支持docker运行，并且可以自定义配置域名/ip流量指向，来达到 windows/mac下单 proxifier的功能。

## Installation

Install [redsocks](https://github.com/darkk/redsocks#packages).

```shell
# 安装
sudo apt-get install redsocks
# 开机自启
sudo systemctl enable redsocks
# 启动服务
sudo systemctl start redsocks
# 重启服务
sudo systemctl restart redsocks
# 停止服务
sudo systemctl stop redsocks
```

## Usage

1. Setup redsocks.conf (Example config given)  
   `/etc/redsocks.conf`

 ```shell
 # 编辑配置信息
 vim resocks.conf
 # 将配置信息复制到系统配置位置
 cp resocks.conf /etc/resocks.conf
 ```

2. Open Terminal and run  
   `sudo ./start-proxifier.sh`

Done. [Check IP](https://ifconfig.me/)

3. Stop proxy and flush iptables  
   `sudo ./stop-proxifier.sh`

   