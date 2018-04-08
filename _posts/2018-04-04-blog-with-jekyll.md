---
author: Wuk
date: 2018-04-04 11:42:32+00:00
layout: post
title: 利用github-pages和jekyll搭建自己的博客系统
subtitle: 免费且支持markdown语法的博客搭建
catalog: true
tags:
- github-pages
- jekyll
---

> programmer都喜欢各种折腾，不折腾，骨子里会难受

## blog
谈到blog，以前都是找一个比较权威的网站开通一个个人账户开始堆文字，常见的有新浪博客，那个时候微博还没发布，到后来程序员喜欢聚集的是[CSDN](https://www.csdn.net/)，[ITEYE](http://www.iteye.com/)等一些偏向技术性的网站，但你知道，用商业的不能灵活变通，尤其还夹杂着一堆乱七八糟的广告什么的，不清爽。那么就有很多人自己买空间自己搭建，wordpress等都是廉价搭建方案，主题也可以随时切换。

但是说到堆技术性的文章，尤其要频繁的插入一些代码，那么写过markdown的人就很清楚，用来写code类文章会越写越上瘾。现在国内支持markdown语法的信息分享网站也有很多，知名的有[简书](https://www.jianshu.com/)

## github-pages
自己搭建的选择也很多，wordpress也有支持md语法的插件，总所周知，github有一个pages功能，可以发布静态类的文章，发布成功后会议以`github.io`为结尾发布到英特网上，更加令人兴奋的是，他支持实时编译[Jekyll](https://jekyllrb.com/)系统，你只要commit你的markdown文件，就会自动生成html，这也是我选择Jekyll而没有选择[Hexo](https://hexo.io/)的原因。

pages是个什么东西，这是[官方说明](https://pages.github.com/)，简单点讲，就是你在你的账号下创建一个名字包含你的用户名的仓库username.github.io，然后在里面提交静态的html文件就访问https://username.github.io

```bash
git clone https://github.com/username/username.github.io

cd username.github.io
echo "Hello World" > index.html

git add --all
git commit -m "Initial commit"
git push -u origin master
```

打开浏览器访问地址https://username.github.io 就可以看到Hello World字样

## Jekyll
上述等于提供了一个免费的空间，但是我们写东西总不能自己去创建HTML文件，然后加CSS，写JS吧。即使懂得这些知识，周而复始的弄也会疲倦。我们的初衷不是专注写文章分享信息，记录自己的技术沉淀的吗，说好的写markdown的文章呢？

> Jekyll：别急，我来了



