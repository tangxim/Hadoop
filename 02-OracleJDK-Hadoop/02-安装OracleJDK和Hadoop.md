# 安装OracleJDK和Hadoop
## 1 安装XShell5
**用XShell5将Windows上的文件传送到Linux上**<br>
* 下载XShell5 地址：https://www.netsarang.com/download/down_form.html?code=522<br>
* 虚拟机ip地址查询命令：ip addr<br>
![ip addr](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-01.png)
* 新建连接<br>
 * 主机地址为虚拟机地址，端口号默认22<br>
 ![新建连接](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-02.png)
 * 用户身份验证<br>
 设置用户名和密码，最好不用root当用户名。<br>
 * 上传文件<br>
 ![命令rz](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-03.png)<br>
 在XShell5命令窗口输入命令rz，上传文件<br>
 ![上传中](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-04.png)<br>
 ![上传成功](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-05.png)<br>
 命令：sz{文件}   可以下载文件<br>
## 2 安装Oracle JDK
**两台虚拟机安装JDK**<br>
* 下载jdk rpm包 地址：http://www.oracle.com/technetwork/java/javase/downloads/index.html<br>
* 用XShell5把jdk rpm上传到Linux后，用终端安装jdk。<br>
* 命令java -version查看当前jdk版本。<br>
* 然后用sudo -s 获取root权限<br>
* 再用rpm -ivh jdk-10_linux-x64_bin.rpm安装jdk10<br>
 ![安装jdk](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-06.png)<br>
* 最后用java -version检查是否安装成功<br>
 ![检查jdk版本](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-07.png)<br>
**配置JAVA_HOME**<br>
* 如图输入命令配置JAVA_HOME<br>
 ![vim](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-08.png)<br>
 ![export](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-10.png)<br>
 ![source](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-09.png)<br>
***输入  :wq  保存配置并敲  回车  退回终端。***<br>
PS：一直在纠结要不要装jre，查了下，说jdk就包含了jre，所以就不用安装啦。
**检查JDK是否配置完成**<br>
 ![检查JDK](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-11.png)<br>
## 3 关闭防火墙
* 查看防火墙状态：systemctl status firewalld<br>
 ![查看防火墙状态](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/2-01.png)<br>
* 关闭防火墙：systemctl stop firewalld<br>
* 设置开机禁用防火墙：systemctl disable firewalld.service<br>
 ![关闭防火墙](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/2-02.png)<br>
## 3 建立信任关系
## 4 安装Hadoop-3.1.0
下载3.1.0 binary包：http://hadoop.apache.org/releases.html

***参考：<br>
Centos7安装Hadoop2.8步骤：https://blog.csdn.net/zzpzheng/article/details/73614526<br>
 史上最详细的Hadoop环境搭建：https://blog.csdn.net/hliq5399/article/details/78193113***<br>
