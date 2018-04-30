---
layout: postcn
title: "Hive基础操作(一)"
date: 2018-04-30 10:25:00 +0800
lang: cn
nav: post
category: hive
tags: [hive]
---

* content
{:toc}

# hive CLI
  >在shell环境下执行一次hive命令：
  <!-- more -->
    hive -e   select * from dual;
    hive -S -e select * from dua;
    **-S**  是为了开启静默模式，除去类似OK等字样

**例子**
```sql
hive -S -e "set"  | grep warehouse

hive.metastore.warehouse.dir=/user/hive/warehouse
hive.warehouse.subdir.inherit.perms=true
```
**在shell环境下从文件中执行hive查询**
```mysql
hive -f  /home/hadoop/h.hql
```
**在hive CLI下从文件执行hive查询**
```sql
souce /home/hadoop/h.hql
```
**预处理文件**
```sql
1. hive -i   文件名    会在启动hive时自动加载文件中的预处理命令
2. 在当前用户家目录中创建   .hiverc文件，hive启动时会自动加载 .hiverc文件。
例如：set hive.cli.print.current.db=true
```
**hive模式下执行shell和hadoop命令**

    hive>  ! mkdir testdir;
    hive> ! pwd;
    hive>   dfs -ls /;    -- 相询速度会更快，因为这样不会新启动一个JVM。

***
**PS:**
HQL文件中注释用   -- 
设置查询时显示字段名：

        set hive.cli.print.header=true;
可以将上述语句放到  home目录下的 .hiverc文件中自动加载。




