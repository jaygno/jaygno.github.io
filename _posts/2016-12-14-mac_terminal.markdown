---
layout:     post
title:        "mac terminal 提示符配置"
date:       2016-12-12 12:00:00
author:     "Jay Guo"
header-img: "img/post-bg-06.jpg"
tags:       mac
---

#mac terminal 提示符配置
------
通过在配置文件里配置环境变量实现
>nano .bash_profile
>export PS1=" "

------
可用参数包括一下类型

	 \d     ｜  Current date
	 \t     ｜  Current time
	 \h     |   Host name
	 \#     |   Command number
	 \u     |   User name
	 \W     |   Current working directory (ie: Desktop/)
	 \w     |   Current working directory with full path (ie: /Users/Admin/Desktop/)


example
> export PS1="\u@\h\w $ "

>参考链接 http://osxdaily.com/2006/12/11/how-to-customize-your-terminal-prompt/



