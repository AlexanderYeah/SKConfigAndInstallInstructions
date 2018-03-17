# 使用Terminal 连接FTP 

####Tips:  
1 通过!进入本地主机的shell，然后通过exit退出本地主机进入远程服务器shell  
2 要把文件下载到哪一个目录 就要先cd 到 哪个目录，再去进行ftp 连接，这样 执行 get 文件 自动下载到目录

3 下载的文件的时候，会出现交互命令，用prompt 关闭交互模式
> ftp prompt # 输入一次 是 关闭 再次输入prompt 是打开交互模式
4  verbose 控制文件传输过程是否显示

* 1 远程登录 根据提示输入用户名和密码

> ftp 115.159.204.xxx  

* 2 下载单个文件用get

> get play.png 获取远程的单个文件 直接进行下载到本地

* 3 下载多个文件用 mget 

  1> mget *  下载当前路径下的所有文件以及文件夹  
  2> mget *.png 下载当前路径下所有文件后缀为.png 格式的文件  
  3> mget 文件名: 下载当前路径下的固定文件 单个  
  4> mget 文件名 文件名 :下载当前路径下的多个文件  
 
 
* 4 put 上传文件
> put play.png 将单个文件上传至服务器

* 5 mput 上传多个文件
  1> mput *  上传当前路径下的所有文件以及文件夹  
  2> mput *.png 上传当前路径下所有文件后缀为.png 格式的文件  
  3> mput 文件名: 上传当前路径下的固定文件 单个  
  4> mput 文件名 文件名 :上传当前路径下的多个文件  


* 6 删除单个文件

> delete play.png  


* 7 批量删除文件

  1> mdelete *  删除当前路径下的所有文件以及文件夹  
  2> mdelete *.png 删除当前路径下所有文件后缀为.png 格式的文件  
  3> mdelete 文件名: 删除当前路径下的固定文件 单个  
  4> mdelete 文件名 文件名 : 删除当前路径下的多个文件    
  
  
* 8 rename 重命名文件 
> rename wee.png weed.png

* 9 文件传输格式的控制

> ascii  设置为ascii 模式，为文字传输模式  
> binary  为二进制模式   
> image  模式直接为Binary模式  
> type  更改传输文件的模式


* 10 连接命令

> open 连接某个FTP服务器  

> close 关闭当前的连接  

> disconnect 相当于 close  

> user  再次输入一次用户名和密码
 