# 20181009
2018年10月09月 -- git使用记录

1. 学习使用git -- 创建仓库、push代码

## push到master时报错：non-fast-forward

出现(non-fast-forward)的根本原因是repository已经存在项目且不是你本人提交（我知道是大概率你提交的，但是git只认地址），你commit的项目和远程repo不一样。这时该怎么办呢？很简单，把远端项目拉回本地：

>git pull

然而pull回来之后，你再push依旧会fail。
原因是他们是两个不同的项目，要把两个不同的项目合并，不能简单的git pull。而是

使用命令：
>git pull origin master --allow-unrelated-histories

可以完美解决问题这条命令允许了不同项目的合并

>git push origin master

可以成功
