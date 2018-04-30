# Attention
Because of the server, a blog template.
# JOYTOU
blog

# Content

|  目录 | 
|:----------:|
| [简体中文](#cn) |
| [概述](#概述)   |
| [功能特色](#功能特色) |
| [服务版本](#服务版本) |
| [文件目录](Mainfest.md) |
| [配置](#配置) |
| [[写文章](#写文章) |
| [许可协议](#许可协议) |

-------

# cn

## 概述
JOYTOU(http://joytou.nets.hk) 是一款由Joytou Wu基于Bootstrap开发的博客模板。您可以通过fork或者复制本项目进行创建您的博客。JOYTOU集成了Git代码版本控制，用户可以选择 Coding、GitHub、BitBucket、GitLab 等任意的代码仓库。JOYTOU是免费的，您可以更改以适应您的主题。但不管如何您务必保留相关版权。

## 功能特色
1. BootStrap样式
2. 博客基本功能
3. 顶部导航栏
4. 自动Sitemap.xml
5. 通过日期、类别、标签等分类文章
6. 重要文章可置顶
7. 文章分享
8. 多语言
9. 文章评论
10. 全局搜索
11. JQuery响应式设计

## 服务版本
从Github克隆项目：

- 用SSH克隆：
```
git clone git@github.com:joytou/joytou.github.io.git
```

- 用HTTPS克隆：
```
git clone https://github.com/joytou/joytou.github.io.git
```

## 配置
_config.yml:

| 键 | 值 | 备注 |
|:----------:|:----------:|:----------|
|      email      |      1540294142@qq.com      |       您的电子邮件地址     |
|      author      |      Joytou Wu      |      文章作者名称      |
|       url     |     http://joytou.nets.hk       |      您的网址，末尾不能加上 `/`       |
|     github       |      https://github.com/joytou/      |      您的Github用户地址      |
|      github_username      |      joytou      |       您的Github用户名     |
|      repo      |      joytou.github.io      |      您的repository名字     |
|      owner_name      |      joytou      |      网站所有者名字      |
|     description       |      ---      |     网站的描述       |
|      keywords      |      ---      |      网站的关键词，必须以数组形式列出      |
|       remind     |      BOOL      |       是否提醒可升级新版本     |
|      BaiduSiteVerification      |      ---      |      百度网站的验证码。如果没有，请留空白      |
|      51la      |      ---      |      51.la网站的统计id。如果没有，请留空白       |
|       51lamb     |      ---      |      51.la数据引用的样式       |
> 其它变量请参考官网的介绍。

各个 /_data/(语言代码).yml 文件:

| 键 | 值 | 备注 |
|:----------:|:----------:|:----------|
| sitename | ssskming | 您的网站名称 |
| sitesubname | 有生以来，有生之年。 | 您的网站副名称 |
| sitedescription | 此博客模板由builder通过style创建 | 您的网站描述(请保留字符串：'builder'、'style') |
| siteabout |  999 | 一些关于您的网站或者您(们)的信息 |

## 写文章
文章格式：
```
--- 
layout: post 

title:  test       
#文章标题 

date:   2015-04-05 08:00:00 +0800     
#发布日期 

nav: post     

stickie: true         
#如果为true则文章置顶 

category: official         
#文章的分类 

tags: [log, bootstrap, joytou]     
#文章的标签，必须是数组 
--- 
* content 
{:toc} 

Summary Content
#摘要内容 

<!-- more --> 

Article mainly content
#在这儿写文章
```

## 许可协议
一旦您使用本服务，即表示[您同意遵循本协议的所有约定](https://github.com/joytou/joytou.github.io/raw/master/LICENSE)。

-------
