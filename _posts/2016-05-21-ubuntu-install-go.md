---
layout:     post
title:      "Ubuntu 下安装 GO"
date:       2016-05-21 16:00:00
author:     "Jay Guo"
header-img: "img/post-bg-06.jpg"
---

虽然可以通过apt-get、yum等命令直接安装，但是由于源一般不能及时更新，版本比较落后，所以我们采用源码安装。

#下载
>http://www.golangtc.com/download

#安装
*  **1.4及以下版本**
>1、sudo apt-get install gcc libc6-dev
2、tar xzvf go.version.tgz -C /usr/local 解压到/usr/local/下
3、cd /usr/local/go/src
4、./all.bash


* **配置环境变量**
>export GOROOT=/usr/local/go 安装目录
 export GOARCH=amd64               
 export GOPATH=       设置一个go目录用于go get第三包时的工作目录
 export GOOS=linux
 export GOBIN=\$GOROOT/bin           
 export PATH=.:\$PATH:$GOBIN

* **1.4以上版本**
>go从1.5开始用go 编译 go，需要先装1.4，才能再装更高版本
>1.5以上版本./all.bash 时默认依赖\$HOME/go1.4，所以我们把前面安装的1.4 版本直接mv 到 \$HOME下
>mv /usr/local/go \$HOME/go1.4
>tar go.1.5version+.tgz -C /usr/local
>cd /usr/local/go/src
>./all.bash
> *API CHECK时报错不影响使用忽略掉或者从1.4目录下copy api目录到报错目录下*




     
 


