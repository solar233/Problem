# 公司培训大数据 flume+kafka+hbase   

## 用到的软件:
1.[Hbase 下载地址](http://archive.apache.org/dist/hbase/)  
2.[hadoop-common-2.2.0-bin-master](https://coding.net/u/panchenri/p/dubbo-soft/git?public=true) (winutil)  

## windows 下安装 Hbas：
1.下载以上两个软件   

2.配置环境变量  
  JAVA_HOME  
  HADOOP_HOME D:\soft\hbase-1.4.2-bin
  PATH 加上 ;$HADOOP_HOME\bin;  

3.修改  habse conf/hbase-env.cmd  
   set JAVA_HOME=D:\jdk1.8.0_65  
   
4.修改 habse conf/hbase-site.xml    
    
    
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


5.cmd 启动 bin/start-hbase.cmd

## 参考文章：  

[参考1](https://blog.csdn.net/qq_16829555/article/details/50514650)  

[参考2](https://blog.csdn.net/qq_16829555/article/details/50514650)
