# HBaseClient
HBase客户端数据管理软件


![image](images/HBaseClient_Main.png)

* [概要说明](#概要说明)
* [下载](#下载)
* [安装运行 for linux](#安装运行linux)
* [安装运行 for window](#安装运行window)



概要说明
------
* 类似PL/SQL，是一个HBase数据库的客户端数据管理软件。是免费开源的软件。
* 基于XJava，使用xml配置文件绘制可视化界面。
* 可视化界面操作
	* 表
		* 表的定义、编辑、删除；
	* 数据
		* 数据的添加、编辑、删除；
		* 数据的全部清空、多条删除、多条复制；
	* 查询
		* 主键的精确；
		* 关键字的模糊查询
		* 关键字的模糊查询过滤显示;
		* 数据查询结果的分页显示操作，并且对查询关键字高亮显示；
	* 导出
		* 表结构的导出；
		* 表结构及数据的导出；
	* 导入
		* 文件批量put命令导入(支持中文)
		* 批量put命令执行(支持中文)
* 非可视化界面的命令操作
	* HBase命令的执行
	* 导入
		* 文件批量put命令导入(支持中文)
		* 批量put命令执行(支持中文)



下载
------
| date | version | size | support |
|:----------:|:------ |:------:|:-------- |
| 2018-05-24 | [v1.6.1 for linux](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6.1/HBaseClient_1.6.1.zip)     | 65.9M | 支持HBase 1.x |
| 2018-05-24 | [v1.6.1 for Window 32](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6.1/HBaseClient_1.6.1_32.exe) | 70.1M | 支持HBase 1.x |
| 2018-05-24 | [v1.6.1 for Window 64](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6.1/HBaseClient_1.6.1_64.exe) | 70.2M | 支持HBase 1.x |
| 2017-06-19 | [v1.6.0 for linux](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6/HBaseClient_1.6.tar.gz)     | 75.7M | 支持HBase 1.x |
| 2017-06-20 | [v1.6.0 for Window 32](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6/HBaseClient_1.6_32.exe) | 83.5M | 支持HBase 1.x |
| 2017-06-20 | [v1.6.0 for Window 64](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.6/HBaseClient_1.6_64.exe) | 83.5M | 支持HBase 1.x |
| 2014-06-12 | [v1.5.0 for linux](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.5/HBaseClient_1.5.tar.gz)     | 22.7M | 支持HBase 0.98.x |
| 2014-06-12 | [v1.5.0 for Window 32](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.5/HBaseClient_1.5_32.exe) | 24.9M | 支持HBase 0.98.x |
| 2014-06-12 | [v1.5.0 for Window 64](https://github.com/HY-ZhengWei/HBaseClient-Download/blob/master/%E5%8F%91%E5%B8%83%E7%89%88%E6%9C%AC/v1.5/HBaseClient_1.5_64.exe) | 24.9M | 支持HBase 0.98.x |



安装运行linux
------
1. 运行要求
   * HBaseClient 1.6.0：Java 1.7+
   * HBaseClient 1.5.0：Java 1.6+
   
2. 设置系统环境变量
   
   在文件 vi ~/.profile 中添加如下内容：
```sh
   export HBASE_CLIENT_HOME=安装HBaseClient所有主目录路径
   export PATH=$PATH:$HBASE_CLIENT_HOME
```

3. 设置Hosts文件
   
   在文件 vi /etc/hosts 中添加HBase集群中所有服务器的名称与IP地址
```sh
   127.0.0.1   master
   127.0.0.1   slave01
   127.0.0.1   slave02
```

4. 运行HBaseClient
```sh
   # ip为管理HBase数据库的Zookeeper的IP地址，一般情况就是HBase数据库的IP地址。
   hbaseclient ip=127.0.0.1 -window
```

5. HBaseClient显示帮助信息
```sh
   hbaseclient /?
```
显示如下帮助信息
* HBaseClient -- 客户端工具
	* 1: put支持中文
	* 2: 支持文件形式的批量put命令执行
	* 3: 支持扫描目录下所有文件的批量put命令执行
	* 4: 支持put命令字符的执行
	* 5: 支持文件编码自动识别
	* 6: 支持图形化界面管理

* 命令格式：
	* HBaseClient <IP=xxx> <[File=xxx [FileType=UTF-8]] | [cmd=xxx]> [-window]

* 命令参数说明：
	* IP         HBase数据库地址
	* File       加载命令文件的路径或目录的路径
	* FileType   加载命令文件的编码格式。可自动识别。当识别不到时，默认为GBK
	* CMD        加载命令字符
	* Language   选择语言。cn:简体中文、 en:English
	* -window    启动图形化管理界面
	* /v         显示版本信息
	* /?         显示帮助信息



安装运行window
------
1. 运行要求
   * HBaseClient 1.6.0：Java 1.7+
   * HBaseClient 1.5.0：Java 1.6+
   
2. 设置Hosts文件
   
   在文件 c:\windows\System32\drivers\etc\hosts 中添加HBase集群中所有服务器的名称与IP地址
```sh
   127.0.0.1   master
   127.0.0.1   slave01
   127.0.0.1   slave02
```

3. 创建快捷方式
   
   创建一个HBaseClient.exe的快捷方法，并按下图设置IP
   
![image](images/HBaseClient_ForWindow_Shortcut.png)
   
   ip为管理HBase数据库的Zookeeper的IP地址，一般情况就是HBase数据库的IP地址。


4. 运行HBaseClient
   
   双击上面创建好的快捷方式运行HBaseClient


---
#### 本项目引用Jar包，其源码链接如下
引用 https://github.com/HY-ZhengWei/hy.common.base 类库

引用 https://github.com/HY-ZhengWei/hy.common.file 类库

引用 https://github.com/HY-ZhengWei/hy.common.hbase.1.x 类库

引用 https://github.com/HY-ZhengWei/hy.common.ui 类库

引用 https://github.com/HY-ZhengWei/XJava 类库