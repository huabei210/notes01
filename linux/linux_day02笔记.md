# 课前命令

```
1) 查看操作系统版本
	getconf LONG_BIT 
2) alt +P 进入 sftp 窗口可以 上传文件
```

# jdk

```
1) 查看java 版本
	java –version
2) 查看已安装jdk 版本
	rpm -qa | grep java
3) 删除opendjdk
	rpm -e --nodeps java-1.6.0-openjdk-1.6.0.35-1.13.7.1.el6_6.i686
	rpm -e --nodeps java-1.7.0-openjdk-1.7.0.79-2.5.5.4.el6.i686
4) 解压 jdk (将jdk压缩包 上传至 /usr/local/jdk)
	tar -zxvf  jdk-7u71-linux-i586.tar.gz
5) 修改配置文件
  	vim /etc/profile
  	在末尾行添加
	#set java environment
	JAVA_HOME=/usr/local/jdk/jdk1.7.0_71
	CLASSPATH=.:$JAVA_HOME/lib.tools.jar
	PATH=$JAVA_HOME/bin:$PATH
	export JAVA_HOME CLASSPATH PATH
6) source /etc/profile  使更改的配置立即生效
```

openjdk和oraclejdk有什么区别

	1.授权协议的不同：OpenJDK采用GPL V2协议放出，而SUN JDK则采用JRL放出。两者协议虽然都是开放源代码的，但是在使用上的不同在于GPL V2允许在商业上使用，而JRL只允许个人研究使用。
	
	2.OpenJDK不包含Deployment（部署）功能：部署的功能包括：Browser Plugin、Java Web Start、以及Java控制面板，这些功能在OpenJDK中是找不到的。
	
	3.OpenJDK源代码不完整：这个很容易想到，在采用GPL协议的OpenJDK中，SUN JDK的一部分源代码因为产权的问题无法开放给OpenJDK使用，其中最主要的部份就是JMX中的可选元件SNMP部份的代码。
	
	4.部分源代码用开源代码替换：由于产权的问题，很多产权不是SUN的源代码被替换成一些功能相同的开源代码，比如说字体栅格化引擎，使用Free Type代替.
# mysql

```
1) 新建文件夹 mysql
   cd /usr/local
   mkdir mysql
2) 上传mysql 安装包至 新建文件夹
3) 解压 (注意: 这里的包没有压缩 所以无需-z 参数)
	tar -xvf MySQL-5.6.22-1.el6.i686.rpm-bundle.tar
4) 将系统自带的mysql卸载
    rpm -qa | grep mysql
    rpm -e --nodeps mysql-libs-5.1.73-5.el6_6.i686
5) 安装mysql 服务器端
	rpm -ivh MySQL-server-5.6.22-1.el6.i686.rpm
6) 	安装MYSQL客户端
     rpm -ivh MySQL-client-5.6.22-1.el6.i686.rpm 
7) 显示随机密码
	more /root/.mysql_secret
8) 启动服务
 service mysql start
9) 连接
	mysql -uroot -pxxxxx
10) 修改密码
	set password =password('root');
11) 开启允许远程登陆
   grant all privileges on *.* to 'root' @'%' identified by 'root';
   flush privileges;
12) 关闭防火墙(先退出MySQL 登陆 exit )
	service iptables stop

```

# tomcat

```
// 创建文件夹 /usr/local/tomcat
1.Tomcat上传到linux上
2.将上传的tomcat解压
	tar -zxvf apache-tomcat-7.0.57.tar.gz 
3.在tomcat/bin目录下执行 startup.sh（注意防火墙）
  
4.查看目标 tomcat/logs/catalina.out
```

# 部署应用

```
将项目打包成war 上传即可,不多提及
```

# redis

```
1) 安装 c 语言编译环境
	yum install gcc-c++
2) 下载redis
wget http://download.redis.io/releases/redis-3.0.4.tar.gz

3) 解压
tar -xzvf redis-3.0.4.tar.gz
4) 编译安装、
	切换至程序目录，并执行make命令编译：
	cd redis-3.0.4
	make

5) 执行安装命令
	make PREFIX=/usr/local/redis install 
6) 配置redis
   1.	复制配置文件到/usr/local/redis/bin目录
	cd redis-3.0.4  
	cp redis.conf /usr/local/redis/bin
7) 启动redis
 cd /usr/local/redis/bin
	7.1)启动redis服务端
	./redis-server redis.conf
	7.2)复制窗口 启动客户端
	./redis-cli
```

# nigx

```
1) 安装gcc (略)
	yum install gcc-c++
2) 安装第三方开发包
	yum install -y pcre pcre-devel
	yum install -y zlib zlib-devel
	yum install -y openssl openssl-devel
3) 上传压缩包
4) 解压
	tar -zxvf nginx-1.8.0.tar.gz
5) 进入nginx-1.8.0目录   使用 configure 命令创建一 makeFile 文件
./configure \
--prefix=/usr/local/nginx \
--pid-path=/var/run/nginx/nginx.pid \
--lock-path=/var/lock/nginx.lock \
--error-log-path=/var/log/nginx/error.log \
--http-log-path=/var/log/nginx/access.log \
--with-http_gzip_static_module \
--http-client-body-temp-path=/var/temp/nginx/client \
--http-proxy-temp-path=/var/temp/nginx/proxy \
--http-fastcgi-temp-path=/var/temp/nginx/fastcgi \
--http-uwsgi-temp-path=/var/temp/nginx/uwsgi \
--http-scgi-temp-path=/var/temp/nginx/scgi
6) 编译
make
7) 安装
make install
8) 创建目录
	mkdir /var/temp/nginx/client -p
9) 启动
  cd /usr/local/nginx/sbin
  ./nginx
-----
1)启动后查看进程
ps aux|grep nginx
2)关闭 nginx：
./nginx -s stop
	或者
./nginx -s quit
3) 重启 nginx：
/nginx -s reload
```

