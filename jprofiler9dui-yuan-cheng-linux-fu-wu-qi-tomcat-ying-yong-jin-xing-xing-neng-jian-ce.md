本地客户端：jprofiler\_windows-x64\_9\_2.zip

服务器端：jprofiler\_linux\_9\_2.sh

服务器端系统为：CentOS7  X64

**客户端安装（window）**

1.先去官网下载windows版安装文件

[http://www.ej-technologies.com/download/jprofiler/version\_92](http://www.ej-technologies.com/download/jprofiler/version_92)

2.安装，按照提示默认安装即可。这里不赘述。

3.配置注册码，这里给给几个9.2的注册码

```
L-Larry_Lau@163.com#23874-hrwpdp1sh1wrn#0620     {亲测可用}
L-Larry_Lau@163.com#36573-fdkscp15axjj6#25257 
L-Larry_Lau@163.com#5481-ucjn4a16rvd98#6038 
L-Larry_Lau@163.com#99016-hli5ay1ylizjj#27215 
L-Larry_Lau@163.com#40775-3wle0g1uin5c1#0674
```

**服务端安装（在服务器上执行）**

1.获取官网安装包

```
[root@localhost opt]# wget http://download-keycdn.ej-technologies.com/jprofiler/jprofiler_linux_9_2_1.sh
```

> 如果没有wget命令。可yum安装。直接`yum -y install wget`，如果   实在安装不好，可以直接window下载再传到服务器上去

2.到jprofiler\_linux\_9\_2\_1.sh存放的目录下执行安装。

```
[root@localhost opt]# chmod +x jprofiler_linux_9_2_1.sh
[root@localhost opt]# ./jprofiler_linux_9_2_1.sh
```

> 根据提示信息一路回车下去即可

**提示：**

（1）下载的服务器和客户端版本必须符合[操作系统](http://lib.csdn.net/base/operatingsystem)的类型，jprofiler支持操作系统类型为windows、MAC os、linux、Solaris、Aix、FreeBSD、HP-UX；

（2）客户端需要licence，可以通过在[http://www.ej-technologies.com](http://www.ej-technologies.com/)网站上输入用户名和邮箱来获取试用版licence，服务器端不需要licence；

（3）客户端和服务器端的版本号要一致，此例中均为9.2。



