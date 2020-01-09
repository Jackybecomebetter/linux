1、当运行sudo apt-get install/update/或其他命令时，由于各种说不清的原因有时会出现如下提示：

> E: 无法获得锁 /var/lib/dpkg/lock-frontend - open (11: 资源暂时不可用)
> E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?

出现问题的原因：有另一个程序正在占用apt-get install进程，由于它在运行时，会占用软件源更新时的系统锁（简称‘系统更新锁’），此时资源被锁。

解决办法：

```
1）ps -e|grep apt-get	找到进程号 
   sudo kill pid号
2）sudo rm /var/cache/apt/archives/lock
	sudo rm /var/lib/dpkg/lock
```

如果一次不行的话，重复以上方法多次，一定ok的。



2、使用apt-get或者apt安装软件的时候，有的时候需要安装一堆依赖项。非常麻烦，要手动安装。

解决办法：

``` 
使用aptitude工具自动进行安装依赖包
例如：sudo aptitude install wireshark
	然后他会给一个解决方案给你，你可以试一下输入y看能不能安装，如果不行的话，就重新输入命令，然后输入n选择其他安装方案，重复以上直到可以安装为止。
```



3、ubuntu 系统出现 仓库 “http://ppa.launchpad.net/fcitx-team/nightly/ubuntu xenial Release“ 没有Release文件

问题：Ubuntu系统在安装了谷歌浏览器后，执行sudo apt-get update 后出现仓库 “http://ppa.launchpad.net/fcitx-team/nightly/ubuntu xenial Release“ 没有Release文件的错误

解决办法：

``` 
在etc/apt/sources.list.d 目录中删除对应的ppa，在软件与更新其他软件中把谷歌浏览器的对勾去掉
当然，这有代价，就是对应的软件不再进行自动更新。
然后执行sudo apt-get update ，问题即可解决
```



