---
layout:     post
title:      "Ubuntu 下源码安装 R"
date:       2016-05-10 12:00:00
author:     "Jay Guo"
header-img: "img/post-bg-06.jpg"
---

一、 **源码下载**

<https://www.r-project.org/>

二、**解压**

tar xzvf R-3.2.4.tar.gz


三、**预编译**

./configure --enable-R-shlib

<small>enable-R-shlib可以保证lib目录下的动态库能够共享，这个选项一定不要忘记添</small>加，否则以后安装某些包的时候会出现Error in dyn.load的错误。

四、**报错**

<small>1、g77 编译器错误</small>

sudo apt-get install build-essential
sudo apt-get install gfortran

<small>2、readline error</small>

configure: error: –with-readline=yes (default) and headers/libs are not available
sudo apt-get install libreadline6-dev

<small>3、X11 error</small>

sudo apt-get install libxt-dev


五、**编译**

make && make install

六、**环境变量**  
        
可以打开.bashrc文件，添加R_HOME和R_LIBS变量，并修改PATH<small>


