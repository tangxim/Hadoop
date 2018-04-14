# 安装
## 1 分区
**给软件新建分区，并命名为Linux。**<br>
此电脑 -> 管理 -> 磁盘管理 -> 选中某磁盘 -> 压缩卷 ->  ... <br>
![分区](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/1.png)<br>
分了50G差不多。<br>
## 2 安装VMware
**下载VMware pro 14**<br>
https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html<br>
**安装**<br>
![安装2-1](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-1.png)<br>
![安装2-2](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-2.png)<br>
无脑下一步，安装<br>
许可证 -> 密钥 CG54H-D8D0H-H8DHY-C6X7X-N2KG6
**创建虚拟机**
用管理员权限打开VMware<br>
新建虚拟机 -> 自定义 -> 稍后安装操作系统 -> 客户机操作系统Linux，版本CentOS 7 -> 处理器数量1，核心数量2 -> 虚拟机内存1G -> 下一步直到完成<br>
***注：<br>
处理器数量 ：是指CPU核数（例如：单核/双核），并不是指CPU颗数。<br>
每个处理的核心数量：是指CPU中的线程，并不是指核心（Core）。***<br>
![安装2-3](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-3.png)<br>
![安装2-4](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-4.png)<br>
![安装2-5](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-5.png)<br>
![安装2-6](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-6.png)<br>
![安装2-7](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-7.png)<br>
![安装2-8](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-8.png)<br>
我的计算机为4核<br>
XP最小配置为处理器数量1 核心数量2；win7最小为2 2。<br>
![安装2-9](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-9.png)<br>
![安装2-10](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-10.png)<br>
![安装2-11](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-11.png)<br>
## 3 安装CentOS7
**下载CentOS7**<br>
http://mirrors.163.com/centos/7/isos/x86_64/CentOS-7-x86_64-DVD-1708.iso<br>
**安装**<br>
点击tangximan虚拟机 -> CD\DVD(IDE) -> 使用ISO映像文件<br>
![安装2-12](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-12.png)<br>
确定
**等待安装**<br>
![安装2-13](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-13.png)<br>
![安装2-14](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-14.png)<br>
安装成功
**其他设定**<br>
语言支持【简体中文】<br>
![安装2-15](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-15.png)<br>
软件选择【GNOME桌面】<br>
安装位置【自动分区】<br>
![安装2-16](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-16.png)<br>
ROOT密码及创建用户<br>
![安装2-17](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-17.png)<br>
重启<br>
勾选许可证设置网络及主机名<br>
![安装2-18](https://github.com/tangxim/Linux-VMware-CentOS-/blob/master/01-VMware-CentOS/2-18.png)<br>
创建设置虚拟机成功。<br>
