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
PS：一直在纠结要不要装jre，查了下，说jdk就包含了jre，所以就不用安装啦。<br>
**检查JDK是否配置完成**<br>
 ![检查JDK](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/1-11.png)<br>
## 3 关闭防火墙
* 查看防火墙状态：systemctl status firewalld<br>
 ![查看防火墙状态](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/2-01.png)<br>
* 关闭防火墙：systemctl stop firewalld<br>
* 设置开机禁用防火墙：systemctl disable firewalld.service<br>
 ![关闭防火墙](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/2-02.png)<br>
## 4 建立信任关系
**master机创建密钥（之后截图中出现的空白方块都表示按了enter键）**<br>
* 查看master ip<br>
 ![查看master ip](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-01.png)<br>
* 切换为root用户<br>
 ![切换为root用户](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-02.png)<br>
* 创建密钥<br>
 ![创建密钥](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-03.png)<br>
**将master机的密钥拷贝到slave机器上**<br>
* 查看slave ip<br>
 ![查看slave ip](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-04.png)<br>
 从这里到后面一部分都是错的，ip找错了，原因是slave机器没联网。<br>
* 切换为root用户<br>
 ![切换为root用户](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-05.png)<br>
* 将master机的密钥拷贝到slave机器上<br>
 ![将master机的密钥拷贝到slave机器上](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-06.png)<br>
 本地主机的key发生了变化，因此每次SSH链接都会有提示。<br>
* 去掉对主机的验证检查并试图拷贝文件到slave机<br>
 ![去掉对主机的验证检查并试图拷贝文件到master机](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-07.png)<br>
* 再次尝试将master机的密钥拷贝到slave机器上<br>
 ![再次尝试将master机的密钥拷贝到slave机器上](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-08.png)<br>
* 将B机的密钥拷贝到文件中,将密钥文件再拷贝到A机器上<br>
 ![再次尝试将master机的密钥拷贝到slave机器上,将密钥文件再拷贝到A机器上](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-09.png)<br>
 结果发现还是错的，连不上。通过排查，发现是slave机没有联网导致的。<br>
 ![slave没联网](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-20.png)<br>
* 联网后查看slave机ip<br>
 ![联网后查看slave机ip](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-10.png)<br>
* 由于之前失败了，需要将/root/.ssh/known_hosts文件删除，再将密钥删除，重新再做一次<br>
 ![重做-master](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-12.png)<br>
 ![重做-slave](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-11.png)<br>
* 将master机的密钥拷贝到slave机器上<br>
 ![将master机的密钥拷贝到slave机器上](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-13.png)<br>
**输入密码后，拷贝完毕。slave机创建密钥**<br>
**将slave机的密钥拷贝到文件中**<br>
**将密钥文件再拷贝到master机器上**<br>
 ![slave机创建密钥](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-14.png)<br>
**完成配置之后重启服务sshd**<br>
 ![完成配置之后重启服务sshd](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-15.png)<br>
**尝试复制文件验证**<br>
 如果成功了，复制就不需要密码<br>
 ![尝试复制文件验证](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-16.png)<br>
**对2主机进行命名并配置hosts**<br>
* master命名<br>
 见命令第一条<br>
 ![对master机进行命名](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-17.png)<br>
* slave命名<br>
 见命令第一条<br>
 ![对slave机进行命名](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-18.png)<br>
* 配置hosts<br>
 在2台机器上执行vi /etc/hosts配置hosts，可以互相通过hostname进行访问。<br>
 见命令第二条<br>
 ![对master机进行命名](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-17.png)<br>
 ![对slave机进行命名](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-18.png)<br>
 hosts文件内容：<br>
 ![hosts文件内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/3-19.png)<br>
 就此完成了服务器的基础配置。<br>
## 5 安装Hadoop-3.1.0
* 下载3.1.0 binary包：http://hadoop.apache.org/releases.html<br>
* 解压<br>
 将安装包上传到机器。解压到/opt/hadoop目录下。<br>
 ![解压](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-01.png)<br>
 将hadoop-3.1.0目录下的所有文件移动到上级目录<br>
 ![移动](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-02.png)<br>
 删除hadoop-3.1.0目录<br>
 ![删除](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-03.png)<br>
* 配置hadoop<br>
 * 编辑/opt/hadoop/etc/hadoop/core-site.xml，在<configuration>节点中增加如下内容：<br>
 ![编辑core-site.xml](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-04.png)<br>
 ![core-site.xml内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-05.png)<br>
 * 编辑/opt/hadoop/etc/hadoop/hadoop-env.sh，将export JAVA_HOME=${JAVA_HOME}中的${JAVA_HOME}改成jdk安装路径。<br>
 ![编辑hadoop-env.sh](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-06.png)<br>
 ![hadoop-env.sh内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-07.png)<br>
 * 编辑/opt/hadoop/etc/hadoop/hdfs-site.xml，在<configuration>节点中增加如下内容：<br>
 ![编辑hdfs-site.xml](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-08.png)<br>
 ![hdfs-site.xml内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-09.png)<br>
 
 *注：<br>
 *dfs.replication的value要设为1<br>
 *dfs.permissions如果配置成true，则对dfs上的文件进行读写时，就需要检查权限。会更安全。如果该参数不配，则默认为校验权限。<br>
 
 * 编辑文件etc/hadoop/mapred-site.xml，添加下面内容由于etc/hadoop中没有mapred-site.xml，所以对mapred-queues.xml.template复制一份。<br>
 ![复制一份mapred-site.xml](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-10.png)<br>
 ![编辑mapred-site.xml](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-11.png)<br>
 ![mapred-site.xml内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-12.png)<br>
 * 编辑/opt/hadoop/etc/hadoop/slaves文件，删除缺省的localhost，将两个slave机器的hostname添加到其中。<br>
 ![编辑slaves](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-13.png)<br>
 ![slaves内容](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-14.png)<br>
 * 编辑/opt/hadoop/etc/hadoop/yarn-site.xml文件，在<configuration>节点上增加如下内容。<br>
 ![编辑yarn-site.xml](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-15.png)<br>
 ![yarn-site.xml内容1](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-16.png)<br>
 ![yarn-site.xml内容2](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-17.png)<br>
 ![yarn-site.xml内容3](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-18.png)<br>
 * 启动hadoop<br>
 根据上面的配置，我们将txm-master配置成了master，即namenode。那么只需要在该节点启动即可。<br>
 进入/opt/hadoop/bin，执行./hadoop namenode -format命令初始化该节点。<br>
 ![启动hadoop](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-19.png)<br>
 ![hadoop成功](https://github.com/tangxim/Hadoop/blob/master/02-OracleJDK-Hadoop/4-20.png)<br>
 
 
***参考：<br>
Centos7安装Hadoop2.8步骤：https://blog.csdn.net/zzpzheng/article/details/73614526<br>
史上最详细的Hadoop环境搭建：https://blog.csdn.net/hliq5399/article/details/78193113<br>
关于linux的SSH 无密码访问，按照网上攻略设置后的问题:https://zhidao.baidu.com/question/552731880118136852.html<br>
ssh-keygen删除旧密钥:https://blog.csdn.net/ivnetware/article/details/52490713<br>
SSH 出现 The authenticity of host xxx can't be established. 什么意思？:https://segmentfault.com/q/1010000006670515<br>
创建你的第一个Shell脚本:https://blog.csdn.net/shuaiby/article/details/46776033<br>
Linux中vi编辑器的使用详解:https://jingyan.baidu.com/article/59703552e2e1e38fc107405a.html<br>
《OD学hadoop》在LINUX下如何将tar压缩文件解压到指定的目录下：https://www.cnblogs.com/yeahwell/p/5623502.html<br>
linux怎么将一个文件移动到另一个目录下：https://blog.csdn.net/u010579482/article/details/72081996
Hadoop3.0 安装配置:https://www.linuxidc.com/Linux/2016-10/136166.htm<br>
hadoop2.7【单节点】单机、伪分布、分布式安装指导:https://www.cnblogs.com/yunkaifa/p/4470422.html***<br>

