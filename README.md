# Notes
笔记

## 翻墙

浏览器插件：
SwitchyOmega（SwitchySharp　升级版） https://switchyomega.com/
	操作步骤：

1.	安装代理插件到浏览器

2. 插件设置：Protocol:SOCKS5   Server:127.0.0.1   Port:8080(可自行设置任意未占用端口)，具体参看插件网站帮助

3. 登录ssh并监听端口


	linux: 


	终端执行如下命令就ok：


	#ssh -qTfnN -D 8080 -p 22 user@47.90.63.13   #基于用户名密码


	该命令是一个后台命令，执行完毕后输入正确的密码（可以免密码登录）后就可以关闭终端。


	或者：


	#ssh -qTfnN -i ~/.ssh/id_rsa -D 8080 -p 22 user@47.90.63.13


	基于ssh秘钥认证的。


	参数解释：


	 -D ：监听本地端口，也就是socket端口


	 -i ：指定私钥文件


	 -p：ssh服务端口

## 其他软件使用代理

1. 安装tsocks
sudo apt-get install tsocks
2. 配置tsocks
 sudo vim /etc/tsocks.conf 
 
 ```
 local = 192.168.100.0/255.255.255.0
server = 127.0.0.1
server_type = 5 # SOCKS 服务版本
server_port = 1080 #SOCKS 服务使用的端口
 ```
 
 3. 连接ssh并监听后可以使用命令启动软件
 
 tsocks 你的软件 &
 
 tsocks firefox &
 
 & 是后台运行的意思
 
