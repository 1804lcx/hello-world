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

2.到jprofiler\_linux\_9\_2\_1.sh存放的目录下执行安装，我的目录是`/opt`。

```
[root@localhost opt]# chmod +x jprofiler_linux_9_2_1.sh
[root@localhost opt]# ./jprofiler_linux_9_2_1.sh
```

> 根据提示信息一路回车下去即可

**提示：**

（1）下载的服务器和客户端版本必须符合[操作系统](http://lib.csdn.net/base/operatingsystem)的类型，jprofiler支持操作系统类型为windows、MAC os、linux、Solaris、Aix、FreeBSD、HP-UX；

（2）客户端需要licence，可以通过在[http://www.ej-technologies.com](http://www.ej-technologies.com/)网站上输入用户名和邮箱来获取试用版licence，服务器端不需要licence；

（3）客户端和服务器端的版本号要一致，此例中均为9.2。

**监控配置**

在客户端打开jprofiler，在弹出的JProfiler Start Center 框中选择New Remote Integration。

1.服务器选择Linux X86/AMD64

![](/assets/服务器选择.png)

2.Next选择服务端的java虚拟机版本。我的是jdk1.8，所以选择如下，根据实际版本选择

![](/assets/服务端java虚拟机配置.png)

3.Next选择默认，在Next，输入服务器的地址

![](/assets/服务器地址.png)

4.Next，选择服务器上的jprofiler安装后的目录，我的是在/opt安装的，安装后的目录就是/opt/jprofiler9

![](/assets/服务器上软件目录.png)

4.Next,配置服务器上的jprofiler的端口，一般保持默认就可以了

![](/assets/配置端口.png)

5.Next，生成了服务器上的配置信息，按照下面的提示是需要将“-agentpath:/opt/jprofiler9/bin/linux-x64/libjprofilerti.so=port=8849 ”加入到要监控的服务的启动参数的

![](/assets/配置信息.png)

6.Next，选择第二项，点击finish，完成客户端的配置

![](/assets/完成配置.png)

7.到入服务器的tomcat下修改启动参数

tomcat的启动文件一般是catalina.sh（如果自己定义了别的启动文件则在对应的启动文件中加），在文件最后加上带jprofiler的启动参数，即上面第5步分生成的那句

JAVA\_OPTS="$JAVA\_OPTS  -agentpath:/opt/jprofiler9/bin/linux-x64/libjprofilerti.so=port=8849,nowait"  ，我这里多加了nowait表示tomcat启动的时候无需等客户端连接后再启动，如果没有加则tomcat会在执行启动脚本后启动jprofiler后等客户端连接后再继续启动tomcat

8.服务器端tomcat启动后，在客户端的JProfiler Start Center 点击刚才配置的连接即可进入监控界面。具体监控数据自行配置

