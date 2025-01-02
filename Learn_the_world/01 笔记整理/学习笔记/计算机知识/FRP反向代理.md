FRP（Fast Reverse Proxy）即快速反向代理，是一款广受欢迎的开源内网穿透工具

老版本教学博客（0.15.1）： https://developer.aliyun.com/article/834336
## 1.搭建：
#### 1.1下载
frp软件的github： https://github.com/fatedier/frp/releases

0.61.1版本的frp软件包中有服务端（frps）和配置文件 frps.toml ; 客户端（frpc）和配置文件frpc.toml。

#### 1.2配置
服务端需要在配置文件frps.toml中设置frp软件监听的端口号，这个端口号和反向代理的端口没有关系，只是客户端连接服务端访问的端口号（以7000为例）。
```
bind_port = 7000
```
客户端除了设置服务端的ip地址和端口，还要设置反向代理对应的端口，Minecraft的多人游戏使用协议为TCP协议，端口为25565。为了保证其他人只用输入代理服务器地址即可登陆本地mc服务器，此处本机端口和映射端口都设置为25565

```
serverAddr = "xxx.xxx.xxx.xxx"
serverPort = 7000      #与服务端bind_port保持一致


[[proxies]]
name = "Minecraft"
type = "tcp"
localIP = "xxx.xxx.xxx.xxx"   #本机ip地址
localPort = 25565
remotePort = 25565
```

#### 3.启动
服务端： `./frps -c frps.toml` （注意不要漏./）
客户端： `./frpc -c frpc.toml`


## 2.问题：
无法持续连接，一个小时之后客户端会连接不到服务端
大佬博客： https://blog.csdn.net/momo_mutou/article/details/85000056
内容如下：
1. 在/lib/systemd/system下创建frps.service
```
[Unit]
Description=fraps service
After=network.target syslog.target
Wants=network.target
 
[Service]
Type=simple
#启动服务的命令（此处写你的frps的实际安装目录）
ExecStart=/your/path/frps -c /your/path/frps.ini
 
[Install]
WantedBy=multi-user.target
```
2. 然后启动frps 
`sudo systemctl start frps `

3. 再打开自启动 
`sudo systemctl enable frps`
