作为Linux小菜，使用Linux终端命令时总是不知到如何使用相关的参数，如-p ，-r ，使用-和不使用-，一个-和两个--，有时能够在网上查询别人的使用方法，可是使用一次，第二次又忘记了，所以自己还是得掌握查看帮助文档的方法。

查看帮助：

1、命令 -- help

2、man 命令

后者更加详细

首先帮助中尖括号<>和方括号[]以及省略号...的含义：
[] 表示是可选的;
<> 表示是可变化的;
x|y|z 表示只能选择一个;
-abc 表示三个参数(或任何二个)的混合使用

在方括号内的表达式(“[” 和 “]”之间的字符)是可选的（写命令时要去掉括号）。
在尖括号内的表达式(“<” 和 “>”之间的字符)是必须替换的表达式(而且要去掉括号)。
省略号表示该选项可以单个或多个

Linux命令格式：
command [options] [arguments]
command：命令
options： --单词 或 -单字

帮助命令：
whatis : 显示简短功能描述

--help： 显示使用摘要和参数列表(可以查看大多数命令的用法)

man [] ：查看命令描述或手册页(Manual)
man -k 列出包含keyword关键字的手册页
注：说明文件被划分为不同的页，man命令就是查看这些页

Manual sections
1:user commands(*) 4:special files 7:miscellaneous2:system calls 5:file formats 8:administrative commands(*)
3:library calls 6:games

在man命令下底行模式：
/ 查找关键字
n/N 下一个/上一个
q 离开

Info ：查看命令详细的说明文件
注：info查看的是比man更详细的说明，也就是把man的页再划分为更小的章节
同时这个命令还可以链接到相似主题
info命令底行模式：
arrows.pageUp.pageDown 切换
Tab 跳往下一个链接(有*的地方)
Enter 进入链接
n/p/u 跳往下一个(上一个)小节,上一层章节
s[] 查找关键字
q 离开

--?

usr/share/doc/ 说明文件目录
<http://www.redhat.com/docs/> 在线说明文件