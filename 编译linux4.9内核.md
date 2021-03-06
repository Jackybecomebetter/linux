### 一、下载linux内核（我用的是linux4.9.208）

下载地址：https://mirrors.edge.kernel.org/pub/linux/kernel/v4.x/

###二、开始编译

1、进入超级用户，把linux-4.9.208.tar.xz/usr/src中

2、解压

```
 xz -d linux-4.9.208.tar.xz
 tar –zxvf linux-4.9.208.tar
```

3、安装环境

```
apt-get update
apt-get install build-essential
apt-get install kernel-package
apt-get install gcc
apt-get install libncurses5
apt-get install libncurses5-dev
apt-get install libqt4-dev
apt-get install libssl-dev

```

4、配置Linux内核

先执行以下命令，用以清除目录下所有配置文件和以前生成内核时所产生的中间文件。

```
cd linux-4.9.208
make mrproper	//清除目录下所有配置文件和以前生成内核时所产生的中间文件。
cp /usr/src/linux-headers-‘`uname -r‘`/.config ./	// 把当前系统的配置文件复制到linux-4.13.1目录下
make menuconfig
```

选择load→OK→Save→OK→EXIT→EXIT

5、编译及安装Linux内核

```
make-kpkg clean

make-kpkg -j8 --initrd kernel_image kernel_headers
```

```
cd /usr/src/
dpkg –i *.deb

sudo vim /etc/default/grub
把GRUB_HIDDEN_TIMEOUT=0注释掉，这样开机的时候才能进入grub界面
update-grub
```

6、重启进入新内核