１、查看已安装的ｇｃｃ和ｇ＋＋版本
ls /usr/bin/gcc*
ls /usr/bin/g++*

2、安装ｇcc和ｇ++（这里用版本５，原先系统是版本７）
sudo apt-get install gcc-5
sudo apt-get install g++-5

３、设置优先级，优先级高用哪个。还有要注意ｇｃｃ版本切换以后，对应的ｇ＋＋版本也要切换
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 40
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 50

４、最简单的切换方式
sudo update-alternatives --config gcc
sudo update-alternatives --config g++

切换的话，输入对应的编号即可。如果不换，直接回车。