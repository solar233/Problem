# 公司培训大数据 flume+kafka+hbase   

## 用到的软件:
1.[Hbase 下载地址](http://archive.apache.org/dist/hbase/)  
2.[hadoop-common-2.2.0-bin-master](https://coding.net/u/panchenri/p/dubbo-soft/git?public=true) (winutil)  

## 一、windows 下安装 Hbase (单机版)：
### 1.下载以上两个软件   

### 2.配置环境变量  
 ``` JAVA_HOME  ```  
 
 ``` HADOOP_HOME  D:\soft\hbase-1.4.2-bin```  
 
 ``` PATH ```加上``` ;$HADOOP_HOME\bin;  ```

### 3.修改  habse conf/hbase-env.cmd  
   ```set JAVA_HOME=D:\jdk1.8.0_65  ```
   
### 4.修改 habse conf/hbase-site.xml    
    
 ```   
<configuration>
	<property>  
        <name>hbase.rootdir</name>  
        <value>file:///D:/tmp/hbase/root</value>  
    </property>  
    <property>  
        <name>hbase.tmp.dir</name>  
        <value>D:/tmp/hbase/tmp</value>  
    </property>  
    <property>  
        <name>hbase.zookeeper.quorum</name>  
        <value>127.0.0.1:2181</value>  
    </property>  
    <property>  
        <name>hbase.zookeeper.property.dataDir</name>  
        <value>D:/tmp/hbase/zoo</value>  
    </property>  
    <property>  
        <name>hbase.cluster.distributed</name>  
        <value>false</value>  
    </property>  
</configuration>
```

### 5.cmd 启动 bin/start-hbase.cmd

## 参考文章：  

[hbase windows 单机版安装](https://blog.csdn.net/qq_16829555/article/details/50514650)    




## 二、centos7 安装Hbase  

### 文件配置修改

1.hbase-site.xml
````
<configuration>
	<property>  
	 <name>hbase.rootdir</name>  
	 <value>hdfs://192.168.10.134:9000/hbase</value>  
	 <description>The directory shared byregion servers.</description>  
	</property>  
	<property>  
	 <name>hbase.zookeeper.property.clientPort</name>  
	 <value>2181</value>  
	 <description>Property from ZooKeeper'sconfig zoo.cfg. The port at which the clients will connect.  
	 </description>  
	</property>  
	<property>  
	 <name>zookeeper.session.timeout</name>  
	 <value>120000</value>  
	</property>  
	<property>  
	 <name>hbase.zookeeper.quorum</name>  
	 <value>192.168.10.134</value>  
	</property>  
	<property>  
	 <name>hbase.tmp.dir</name>  
	 <value>/home/hadoop/hbase/tmp</value>  
	</property>  
	<property>  
	 <name>hbase.cluster.distributed</name>  
	 <value>false</value>  
	</property>  
</configuration>
````  

2.hbase-env.sh   
`````
export JAVA_HOME=/home/hadoop/jdk1.8.0_161
export HADOOP_HOME=/home/hadoop/hadoop-2.6.5
export HBASE_HOME=/home/hadoop/hbase-1.2.6  
export HBASE_CLASSPATH=/home/hadoop/hadoop-2.6.5/etc/hadoop  
export HBASE_PID_DIR=/root/hbase/pids
`````

3.centos7 
命令：vim /etc/hosts  (/ 不要忘记)
`````
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
192.168.10.134 hserver1
`````

4.windows   
c:/windows/system32/drivers/etc  hosts文件
````
192.168.10.134 hserver1
````
### demo程序
 [hbase-demo](https://coding.net/u/panchenri/p/hbase-demo/git?public=true) 
 注意：1.master 别名， 需配置windows中的 hosts文件，否则将出现错误 无法解析（unkonwn hosts）  
 
## 参考文章：
[Linux安装Hbase(CentOS7+Hbase1.2.5+Hadoop2.8.0)](https://blog.csdn.net/pucao_cug/article/details/72229223)



