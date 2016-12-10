rtlwifi_new
===========

A repo for the newest Realtek rtlwifi codes.

This code will build on any kernel 3.0 and newer as long as the distro has not modified
any of the kernel APIs. It includes the following drivers:

rtl8192ce, rtl8192se, rtl8192de, rtl8188ee, rtl8192ee, rtl8723ae, rtl8723be, and rtl8821ae.

Added March 16, 2016: All branches of this repo now support the ant_sel module option
for rtl8723be. In addition, patches to implement this feature have been submitted
to the linux-wireless repo. If accepted, they should appear in kernel 4.7; however,
they will be backported to kernels 4.0 and newer when they reach mainline.
linux下对于rtl系列的无线网卡，大多数网友都在吐槽，总是频繁的掉网，就此将自己在网上安装时的经验写下。

1.下载网卡驱动，其中包含rtl的大多数包

　　sudo apt-get install linux-headers-generic build-essential git

　　git clone https://github.com/lwfinger/rtlwifi_new

　　cd rtlwifi_new

　　sudo make install

　　sudo modprobe rtl8723be

2.网卡安装好了，设置一下网络信号问题

　　sudo vim /etc/modprobe.d/rtl8723be.conf

　　options rtl8723be ant_sel=2   将这句添加在末尾

3.无线网总掉解决

　　sudo vim /etc/modprobe.d/rtl8723be.conf

　　在该文件添加以下语句：

       options rtl8723be ips=0

 

       options rtl8723be fwlps=0

 

       options rtl8723be swenc=1

4.重启系统解决

