---
layout: postcn
title: "Spark-sql启动"
date: 2018-04-30 23:25:00 +0800
lang: cn
nav: post
category: spark
tags: [spark]
stickie: true
---

* content
{:toc}

spark-sql启动（工作测试配置）
<!-- more -->
## 临时测试使用

    spark-sql  spark.kryo.registrationRequired=false
      --master yarn-client
      --conf
      --num-executors 130
      --executor-memory 10g
      --driver-memory 40g
      --queue hwvip
