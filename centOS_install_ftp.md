# 安装FTP 
* 1 安装命令

 > yum -y install vsftpd 

* 2 使用如下命令增加账户，其中 /var/www/html 是我们的 ftp 目录，ftpadmin 为 ftp 用户名。 

> useradd -d /var/www/html -s /sbin/nologin ftpadmin  

* 3 给 ftpadmin 这个用户设置密码 

> passwd ftpadmin  


* 4 给 ftp 目录修改权限，否则无法上传文件  

> chmod o+w /var/www/html/  

* 5 为安全起见，我们还需要使用 vi 命令编辑 vsftpd 的配置文件。    

修改如下内容：禁止匿名用户登录，不可以让 ftp 用户跳出自己的家目录（前两项修改，最后一项新增

> anonymous_enable=NO  

> chroot_local_user=YES  

> allow_writeable_chroot=YES   


* 6 启动 vsftpd 服务。启动完毕后我们就可以使用 FTP 工具来连接了


> systemctl start vsftpd

* 7 设置开机启动FTP 服务

	
> systemctl enable vsftpd


