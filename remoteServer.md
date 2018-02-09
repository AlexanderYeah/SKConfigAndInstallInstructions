# 远程连接云服务器操作指南
一  基本操作

* 登录云服务器  远程连接 输入密码就行 格式就是username@ip 地址

> ssh root@47.97.xxx.195 

* 上传文件到服务器  

> scp /path/filename username@servername:/path/

* 从服务器下载文件  

> scp username@servername:/path/filename /var/www/local_dir（本地目录）   

* 从服务器下载整个目录  
> scp -r username@servername:/var/www/remote_dir/（远程目录） /var/www/local_dir（本地目录）  

* 上传目录到服务器  
> scp -r local_dir username@servername:remote_dir 
