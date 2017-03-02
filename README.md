# hello-world
启动之前创建好的容器方法：
[root@d705a60535de /]# sudo docker start centos7
[root@d705a60535de /]# sudo docker attach centos7 

或者这种方式进入容器：
[root@k8s_slave1 ~]# docker exec -it 6b01cbe05186 /bin/bash
安装要创建镜像的软件
[root@d705a60535de /]# yum install sysbench

所以先用exit命令退出容器，再运行docker commit命令：

[root@localhost ~]# sudo docker commit -a "caixia.liu"   -m " mysql5.7.17 " ae0d3a08d535 registry.c2cloud.cn/gxqzh/mysql:5.7.17
