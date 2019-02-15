---
layout: article
title:  "「工具」 订阅博客"
date:   2019-02-13 10:08:40 +0800
key: subscribe-blog-20190213
aside:
  toc: true
category: [Blog]
---

Feed43  <http://feed43.com/>  
其中 { % } 为变量，即要提取的； { * } 占位符，放在空格或回车及无关内容上，

<https://post.smzdm.com/p/553684/>   
成功后会生成两个链接 例如：
Feed URL:  http://feed43.com/2738718687802442.xml
Edit URL: http://feed43.com/feed.html?name=2738718687802442

- 如果要换一个网站订阅，一定要重新打开 feed43 网页，因为一个网页只会生成一个订阅页面，如果重复编辑，则会发生覆盖；  
- 生成订阅源之后，若再修改，也不会生效；（Inoreader 订阅），显示信息不会再更新，但是设置会更新；    

打造个人 RSS <https://www.ifanr.com/app/770271>   

InoReader 可设置文件夹，多个订阅源一直在一起，用 iPad 上的 Reeder 软件阅读时，有个弊端，就是，当前层级下的所有文章都显示在一起，也就是如果你不用文件夹包裹，那么可以看到当前订阅源下的文章，如果组织在文件夹中，看到的就是文件夹下所有源的订阅文章，此时无法把同一订阅源下的文章聚合在一起；  

## 生成 RSS
##dapper使用最简单 , 适合做一个只有标题的源地址是 http://open.dapper.net##FEED43小众有一篇介绍 , 你可以去 小众软件 搜索一下相对简单 , 我只试用过, 就不乱说了##YAHOO PIPEShttp://pipes.yahoo.com我认为是同类最强神器做一个只有标题的订阅源很简单 , 一般就两步1. "xpath fetch page" 模块 填上页面地址 , 和 xpath2. "rename" 模块 , 比如修改 href 为 link , 修改 content 为title3. 输出 , 保存就可以了好吧 . 是3步傻瓜式的, page2rss , 填上地址 , 自动生成 , 至于能不能成功还得看人品 !!

在rss展示全文，需要通过FeedEx再转一次 <https://feedex.net/>  
DIY 抓取 RSS：Huginn <https://zhuanlan.zhihu.com/p/46216545>

## 附录
### 1. 推荐资料

[1].  少数派Matrix. 使用 RSS 可以做什么你未曾想过的事[EB/OL]. <https://sspai.com/post/34280>. 2016-05-18/2019-02-15.   
