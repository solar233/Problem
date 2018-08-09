# Hadoop #
1.HDFS 分布式文件系统  2.日志分析（只能针对离线文件，需将文件拷贝入 hdfs中）  

## 安装Hadoop ##
按照文章照抄即可，首先要有虚拟机安装了linux系统，或者有台服务器  

##配置文件 core-site##  
主机hostname 应该配置为内网ip(ifconfig inet)，不能使用外网ip
````
<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<!--
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

<!-- Put site-specific property overrides in this file. -->

<configuration>

	<property>
		<name>fs.default.name</name>
		<value>hdfs://hserver1:9000</value>
	</property>

</configuration>
````
hostname 配置 : vim /etc/hosts
````
# The following lines are desirable for IPv4 capable hosts
127.0.0.1  localhost.localdomain localhost
132.232.23.187 localhost4.localdomain4 localhost4
172.27.0.10  hserver1

# The following lines are desirable for IPv6 capable hosts
::1 localhost.localdomain localhost
::1 localhost6.localdomain6 localhost6
````
参考文章： 

 [1.spark单机版安装](https://www.cnblogs.com/luo-mao/p/5941708.html)  
 
[2.使用VMware安装CentOS7详请](https://blog.csdn.net/hui_2016/article/details/68927487)  

[3.Linux上安装Hadoop集群(CentOS7+hadoop-2.8.0)](https://blog.csdn.net/pucao_cug/article/details/71698903)

## Tips ##  
1.关闭防火墙（centos7）:
systemctl stop firewalld.service

2.显示 hdfs 下的文件列表:
hadoop fs -ls /test/output7/

3.显示 hdfs 下的文件:
hadoop fs  -cat /test/output7/part-m-00000

4.获取root权限：sudo su
