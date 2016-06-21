#DNS SPIDER 详细设计

------

[TOC]

##DNS SPIDER 简介
>后期补充

##DNS SPIDER 目录结构
>├── dns-spider 
>├── find_vip_visits 
>├── manager 
>├── ns
>├── ns_agent
>└── tags

###dns-spider
###find_vip_visits
###manager
>用于向探测节点下发实时任务，以及接受心跳包

-------
>├── bin
>│   ├── mailreport.pl ： 用于监控数据库心跳字段是否更新，发送报警邮件
>│   ├── mail.sh：运行mailreport.pl，被添加到crontab
>│   ├── manager：后台可执行程序
>│   └── managerd ：用于控制程序启动暂停的脚本，rpm安装在/etc/init.d/下

------
>├── build ：rpm包存放目录
>├── build.sh ：打包脚本 ， ./build.sh -rb
>├── conf
>├── doc
>├── managerd.spec : 控制rpm包文件
>├── sbin
>└── src
>部署在中心节点 60.210.10.51

###ns
>用于接收实时dns请求，部署在中心节点，60.210.10.51
>代码实现：asio模型 + recv 线程 + mysql 线程 （通过无锁队列）

------
>├── bin
>│   ├── ns
>│   └── nsd
>├── build
>├── build.sh
>├── conf
>│   ├── ldns_spider.sql :  建库sql
>│   └── ns.conf
>└── nsd.spec
###ns_agent
>程序部署在探测节点，包括探测程序，跟 ns 程序

------
>├── bin
>│   ├── dump.sh ： 定时导出数据库文件，rsync到中心点，/etc/cron.d/ 目录下
>│   ├── find_rip   ：
>│   ├── find_rs    ：
>│   ├── ns           ：解析本机发出的dns请求
>│   └── ns_agent ：控制整个程序的后台脚本/etc/init.d/下
>├── build
>├── build.sh        ： ./build.sh -rb
>├── conf
>│   ├── account.sql : 添加探测程序默认账号
>│   ├── find_rip.conf
>│   ├── find_rs.conf
>│   ├── ldns_spider.sql
>│   ├── ns.conf
>│   └── rsync.pas ：rsync 配置文件
>├── ns_agent.spec
>├── sbin
>└── src

参考链接：http://wiki.fastweb.com.cn/DNS_SPIDER%E5%AE%89%E8%A3%85%E6%89%8B%E5%86%8C (安装配置手册)

