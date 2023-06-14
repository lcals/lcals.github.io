---
layout: post
title:  "游戏 客户端 虚拟文件系统"
date:   2023-06-14 17:33:57 +0800
categories: 客户端 虚拟文件系统
---
# 我对虚拟文件系统的需求

   1 检测是否需要更新

   2 读取网络资源 url 头像

   3 读取unity ab资源

   4 提供异步 同步两种接口

# 接口设计

   1  TryTestUpdateFile 是否更新
   
   2  UpdateFileAsync 更新

   3  LoadWebFile 读取网络资源

   4  LoadAsset 读取资源

   5  LoadNativeFile 读取原生文件

   6  LoadWebFileAsync 异步读取网络资源

   7  LoadAssetAsync 异步读取资源

   8  LoadNativeFileAsync 异步读取原生文件