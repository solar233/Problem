# Hadoop #
1.HDFS 分布式文件系统  2.日志分析（只能针对离线文件，需将文件拷贝入 hdfs中）  

## 安装Hadoop ##
按照文章照抄即可，首先要有虚拟机安装了linux系统，或者有台服务器

参考文章： 

 [1.spark单机版安装](https://www.cnblogs.com/luo-mao/p/5941708.html)  
 
[2.使用VMware安装CentOS7详请](https://blog.csdn.net/hui_2016/article/details/68927487)

## Tips ##  
1.关闭防火墙（centos7）:
systemctl stop firewalld.service

2.显示 hdfs 下的文件列表:
hadoop fs -ls /test/output7/

3.显示 hdfs 下的文件:
hadoop fs  -cat /test/output7/part-m-00000

4.获取root权限：  
sudo su
