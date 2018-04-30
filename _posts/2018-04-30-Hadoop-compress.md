---
layout: postcn
title: "Hadoop批量压缩文件"
date: 2018-04-30 21:25:00 +0800
lang: cn
nav: post
category: hadoop
tags: [hadoop]
stickie: true
---

* content
{:toc}

利用Hadoop自带jar包hadoop-streaming.jar流式压缩文件
<!-- more -->

## 压缩
```shell
yarn jar /home/zyh/apps/hadoop/share/hadoop/tools/lib/hadoop-streaming-2.7.2.jar streamjob \
	-D dfs.replication=2 \
	-D mapreduce.job.queuename=hwcdm \
	-D mapreduce.output.fileoutputformat.compress=true \   ---压缩
	-D mapreduce.output.fileoutputformat.compress.codec=org.apache.hadoop.io.compress.GzipCodec \
	-D mapreduce.output.fileoutputformat.compress.type=BLOCK \
	-D mapreduce.map.memory.mb=4096 \
	-D mapreduce.reduce.memory.mb=4096 \
	-D mapreduce.reduce.cpu.vcores=4 \
	-D mapreduce.input.fileinputformat.split.minsize=4048576000 \
	-D mapreduce.input.fileinputformat.split.maxsize=4048576000 \
	-D input $hdfsPath/*.* \
	-D output $compressPath \
	-D mapper `/bin/cat` \   ---不清楚作用
	-D numReduceTasks 50
````

## 解压
```
yarn jar /home/zyh/apps/hadoop/share/hadoop/tools/lib/hadoop-streaming-2.7.2.jar streamjob \
	-D dfs.replication=2 \
	-D mapreduce.job.queuename=hwcdm \
	-D mapreduce.output.fileoutputformat.compress=false \   ---解缩
	-D mapreduce.output.fileoutputformat.compress.codec=org.apache.hadoop.io.compress.GzipCodec \
	-D mapreduce.output.fileoutputformat.compress.type=BLOCK \
	-D mapreduce.map.memory.mb=4096 \
	-D mapreduce.reduce.memory.mb=4096 \
	-D mapreduce.reduce.cpu.vcores=4 \
	-D mapreduce.input.fileinputformat.split.minsize=4048576000 \
	-D mapreduce.input.fileinputformat.split.maxsize=4048576000 \
	-D input $hdfsPath/*.* \
	-D output $compressPath \
	-D mapper `/bin/cat` \   ---不清楚作用，解压要加上，要不每条记录前会多字符
	-D numReduceTasks 50
```
![](/img/hadoop-hive/hadoop-compress.jpg){:height="85%" width="85%"}

    
  
