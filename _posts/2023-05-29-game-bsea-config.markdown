---
layout: post
title:  "游戏 公共基础 配置"
date:   2023-05-29 17:33:57 +0800
categories: 公共基础 配置
---

## 我对配置的需求

  1 使用类来表示硬编码类型，例如 Item 表，以便更好地读取和写入配置信息。

  2 使用容器类，例如 List 和 Dictionary，来方便查询和写入配置信息。

  3 在需要自定义配置信息时，使用自定义类，以便更好地自定义配置。

  4 集成和测试配置模块。

  5 提供两种模式，一种输出文本文件方便了解内容，一种输出二进制文件提供高性能。

  6 使用 Excel 文件来方便策划来配置表格。

  7 在转化表格时，不需要关闭表格。

  8 在设计和开发表格属性时，应该避免过于复杂和多重定义的情况。

  9 需要一个独立的命令行工具，不需要依赖其他库或程序。

  10 客户端，服务器共享配置，输出不同的语言绑定。

## 表设计
 
### 单条属性
   
   假设 有一个Item表

   有 id 属性 定义为单条属性

{% highlight csharp %}

   public class Item
   {

       public int id;
   
   }
{% endhighlight %}

### 复合属性

   假设 有一个Item表

   有 价格 属性  价格1 价格2 价格3  定义为复合属性

{% highlight csharp %}

   public class Item
   {

       public list<int> price;
   
   }
{% endhighlight %}

### 引用属性
 
   A表有个道具叫 奖励的复合属性

   B表也需要这个结构 直接添加引用 属性

  {% highlight csharp %}

   public class A
   {

       public list<Reward> Reward;
   
   }

   public class B
   {

       public list<Reward> Reward;
   
   }

{% endhighlight %}



## 使用

 提供一个工具，可以读取相同目录下的配置档，如果没有配置档就生成默认配置，并让使用者修改配置。工具可以读取 Excel 文件，并输出我们使用的配置文件，同时输出日志。  