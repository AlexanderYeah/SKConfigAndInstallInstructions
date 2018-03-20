# centOS 安装A M P 环境

[参考简书作者,非常感谢！！！](https://www.jianshu.com/p/bc14ff0ab1c7)
## 一 Apache 环境安装 
1 安装Apache
> yum install httpd
 
2 操作指令一览
> systemctl start httpd      //启动apache  
> systemctl stop httpd       //停止apache  
> systemctl restart httpd    //重启apache   
> systemctl enable httpd     //设置apache开机启动   


# 二 安装MariaDB (MySQL的一个开源分支)

1 安装 
> yum install mariadb mariadb-server  

2 配置命令
>  systemctl start mariadb //启动MariaDB   
>  systemctl stop mariadb //停止MariaDB  
>  systemctl restart mariadb //重启MariaDB   
>  systemctl enable mariadb //设置开机启动  

3 设置root 账户密码
> mysql_secure_installation  
根据提示 点击回车设置root 账号密码  
进行重启设置
> systemctl restart mariadb.service

# 三 安装PHP 以及 PHP扩展
1 安装PHP 以及扩展  
> yum install php php-mysql php-gd libjpeg* php-ldap php-odbc php-pear php-xml php-xmlrpc php-mbstring php-bcmath php-mhash  

2 安装完成 重启服务
> systemctl restart httpd.service

3 测试PHP 安装结果
> vi /var/www/html/index.php   
> <?php
  phpinfo();
?>

4 浏览器输入服务器ip 地址，成功显示PHP 版本信息即可

# 四 安装phpmyadmin 
1 安装phpMyAdmin
> yum install phpmyadmin php-mcrypt

2 修改配置文件 能够远程连接
> vi /etc/httpd/conf.d/phpMyAdmin.conf

```<Directory /usr/share/phpMyAdmin/>
   AddDefaultCharset UTF-8

   <IfModule mod_authz_core.c>
     # Apache 2.4
     <RequireAny>
      # Require ip 127.0.0.1 #修改的地方 注释掉
      # Require ip ::1  #修改的地方 注释掉
      Require all granted #修改的地方 增加
     </RequireAny>
   </IfModule>
   <IfModule !mod_authz_core.c>
     # Apache 2.2
     Order Deny,Allow
     Deny from All
     Allow from 127.0.0.1
     Allow from ::1
   </IfModule>
</Directory>

<Directory /usr/share/phpMyAdmin/setup/>
   <IfModule mod_authz_core.c>
     # Apache 2.4
     <RequireAny>
      # Require ip 127.0.0.1 #修改的地方 注释掉
     #  Require ip ::1 #修改的地方 注释掉
     Require all granted #修改的地方 增加
     </RequireAny>
   </IfModule>
   <IfModule !mod_authz_core.c>
     # Apache 2.2
     Order Deny,Allow
     Deny from All
     Allow from 127.0.0.1
     Allow from ::1
   </IfModule>
</Directory>
```
3  重启服务器
> systemctl restart httpd


然后通过浏览器访问 http://服务器ip地址/phpMyAdmin访问 出现phpMyAdmin 界面即代表成功


