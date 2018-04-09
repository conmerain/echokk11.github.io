---
author: Wuk
date: 2018-04-09 21:22:00+00:00
layout: post
title: 在vultr上搭建科学上网工具shadowsocks
subtitle: 畅游互联网世界
catalog: true
tags:
- vps
- shadowsocks
---

> 上个网都禁锢，什么鬼？

## 硬需求
尤其是编程人员，需要经常用到google搜索信息，也会经常用到国外一些技术网站。

## 方式
翻墙方法也很多，以前的goagent，购买vpn等，考虑到稳定性和个性化需求，完全可以自己在国外买一个VPS配合开源的shadowsocks，在任何端都能实现轻松翻墙。

## vultr
国外VPS选择很多，如linode等。[vultr](https://www.vultr.com/?ref=6891563)是后来建立的公司，性价比很不错，最低配置的主机才2.5刀一个月，但是经常缺货，推荐买5美元的。甚至可以在上面搭建jdk，mysql，tomcat等其他东西也足够自己玩耍。我除了搭建ss翻墙外，还自己搭建了一个[wordpress](https://wordpress.org/)用nginx转发，当作个人博客玩耍，还搭建了[frp](https://github.com/fatedier/frp/blob/master/README_zh.md)做映射工具。

## shadowsocks
