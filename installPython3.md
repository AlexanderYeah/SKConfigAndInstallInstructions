# 基于Linux的 Python3 环境的安装  
最近买了一台centOS 阿里云轻量级服务器 自带Python2 准备安装Python3.6 版本的  
## Step  
* 1 查看当前版本python 的路径  使用以下命令,以便后面安装完毕 建立软链接
> which python  
正常情况下会显示python 路径，例如：/usr/bin/python  

* 2 首先安装依赖包 以下命令  
> yum -y groupinstall "Development tools"  
> yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel  

* 3 通过命令行下载python3.6的安装包，也可以去官网进行下载，使用winScp 放到服务器上面
> wget https://www.python.org/ftp/python/3.6.2/Python-3.6.2.tar.xz  

* 4 单独建立一个文件夹，放到此文件夹下面    
> mkdir /usr/local/python3   

* 5 进入该文件夹 ，解压安装包   
> tar -xvJf  Python-3.6.2.tar.xz  

* 6 解压完毕，进行配置路径和安装 以下两个命令. 注意 路径是安装python3的路径 不是写死的，安装到哪个路径 就写什么路径
> ./configure --prefix=/usr/local/python3  

> make && make install  

* 7 最后一步创建软链接 ，同理 路径是安装python的路径 ，python2 安装的路径若为local/bin/python 则 建立软连接到 local/bin/python3
> ln -s /usr/local/python3/bin/python3 /usr/bin/python3  

> ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3
