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
新建虚拟机 -> 自定义 -> 稍后安装操作系统 -> 客户机操作系统Linux，版本CentOS 7 -> 处理器数量1，核心数量2 -> 虚拟机内存1G -> 下一步直到完成<br>
*注：<br>
处理器数量 ：是指CPU核数（例如：单核/双核），并不是指CPU颗数。
每个处理的核心数量：是指CPU中的线程，并不是指核心（Core）。*
