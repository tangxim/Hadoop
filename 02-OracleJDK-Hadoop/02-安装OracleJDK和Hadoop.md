# 安装OracleJDK和Hadoop
## 1 安装XShell5
**用XShell5将Windows上的文件传送到Linux上**<br>
* 下载XShell5 地址：https://www.netsarang.com/download/down_form.html?code=522<br>
* 虚拟机ip地址查询命令：ip addr<br>
![ip addr]()
* 新建连接<br>
 * 主机地址为虚拟机地址，端口号默认22<br>
 ![新建连接]()
 * 用户身份验证<br>
 设置用户名和密码，最好不用root当用户名。<br>
 * 上传文件<br>
 ![命令rz]()<br>
 在XShell5命令窗口输入命令rz，上传文件<br>
 ![上传中]()<br>
 ![上传成功]()<br>
 命令：sz{文件}   可以下载文件<br>
## 2 安装Oracle JDK
**两台虚拟机安装JDK并配置JAVA_HOME**<br>
下载jdk rmp包 地址：http://www.oracle.com/technetwork/java/javase/downloads/index.html<br>
## 3 建立信任关系
## 4 安装Hadoop-3.1.0
下载3.1.0 binary包：http://hadoop.apache.org/releases.html

***参考：<br>
Centos7安装Hadoop2.8步骤：https://blog.csdn.net/zzpzheng/article/details/73614526<br>
 史上最详细的Hadoop环境搭建：https://blog.csdn.net/hliq5399/article/details/78193113***<br>
