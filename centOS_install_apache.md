# centOS 安装Apache 环境

* 1 安装Apache服务。Apache在centos7中是Apache HTTP server，所以想安装Apache其实是要安装httpd。

> yum install httpd

* 2 启动和关闭Apache 服务

> systemctl start httpd.service 

> systemctl stop httpd.service


* 3 配置Apache服务。在开启httpd服务之前，需要手动配置httpd服务的一些参数。用vi打开httpd的配置文件。 

> vi /etc/httpd/conf/httpd.conf  

找到 #Listen 12.34.56.78:80 这一行，模仿注释在下面添加 Listen 你的IP地址或域名:你要监听的端口号，本地访问IP地址为127.0.0.1  

* 4 测试一下，输入服务器的ip地址。如果显示Apache的测试页面，说明httpd服务已经成功启动了。

> /etc/httpd是httpd的根目录

> /var/www/html是放置请求页面的目录 