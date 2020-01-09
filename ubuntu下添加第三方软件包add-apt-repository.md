add-apt-repository

也许你早已注意到，我们在介绍软件的时候，在安装这块一般都提供 PPA 源安装方式，这是一种快速方便的软件安装方法，但对于一些新手来说，对 PPA 并不是很熟悉，下面我们就详细介绍一下。

# 我们先了解一下 PPA 的定义：

PPA 全称为 Personal Package Archives（个人软件包档案），是 Ubuntu Launchpad 网站提供的一项服务，当然不仅限于 Launchpad 。它允许个人用户上传软件源代码，通过 Launchpad 进行编译并发布为二进制软件包，作为 apt/新立得源供其他用户下载和更新。在Launchpad网站上的每一个用户和团队都可以拥有一个或多个PPA。

通常 PPA 源里的软件是官方源里没有的，或者是最新版本的软件。相对于通过 Deb 包安装来说，使用 PPA 的好处是，一旦软件有更新，通过 sudo apt-get upgrade 这样命令就可以直接升级到新版本。

# 如何通过 PPA 源来安装软件：

通常我们可以通过 Google 来搜索一些常用软件的 PPA 源，通常的搜索方法是软件名称关键字 + PPA ，或者也可直接到 launchpad.net 上去搜索，搜索到后我们就可以直接用 sudo apt-add-repository 命令把 PPA 源添加到 Source list 中了。

比如 FireFox PPA 源：<https://launchpad.net/~ubuntu-mozilla-daily/+archive/ppa> ，我们可以在这里找到 ppa:ubuntu-mozilla-daily/ppa 的字样，然后我们通过以下命令把这个源加入到 source list 中。

![这里写图片描述](https://img-blog.csdn.net/20160311154315422)

sudo apt-add-repository ppa:ubuntu-mozilla-daily/ppa

然后我们再从下面的 Packages 列表中找到适用于当前 Ubuntu 版的 FireFox 4.0 包名称，更新源并安装：

![这里写图片描述](https://img-blog.csdn.net/20160311154502753)

sduo apt-get update 
sudo apt-get install firefox-4.0