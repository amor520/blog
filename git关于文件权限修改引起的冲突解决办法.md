---
title: git关于文件权限修改引起的冲突解决办法
categories:
- git
tags:
- git
- Mac
---
有些时候我们会对使用git管理代码进行权限修改，修改过后导致的结果就是本地==代码明明没有更改，却提示冲突==，这是为什么呢？原来git把文件权限也算作文件差异的一部分。
<!-- more -->
**解决办法** ：

git中可以加入忽略文件权限的配置,具体代码如下：

`git config core.filemode false`

`cat .git/config`

![](http://7xt252.com1.z0.glb.clouddn.com/Screen%20Shot%202016-06-01%20at%202.46.26%20PM.png)
