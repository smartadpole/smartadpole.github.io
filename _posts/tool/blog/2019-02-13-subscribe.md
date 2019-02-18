---
layout: article
title:  "「工具」 使用 feed43 制作 RSS 源"
date:   2019-02-13 10:08:40 +0800
key: feed43-20190213
aside:
  toc: true
category: [Blog]
---

Feed43 <http://feed43.com/> DIY RSS 源非常简单；    

## 一、 基本操作
**1. 创建源**  
点击首页的「create your first RSS feed」创建一个源；   

**2. 输入你想订阅的地址**  
<img src="/assets/images/tools/work/feed43_src.png"/>  

**3. 解析网页**  
其中 { % } 为变量，即要提取的； { * } 占位符，放在空格或回车及无关内容上；  
<img src="/assets/images/tools/work/feed43_extract.png"/>  

**4. 组合信息**  
<img src="/assets/images/tools/work/feed43_group.png"/>  

**5. 订阅**  
成功后会生成两个链接 例如：
Feed URL:  <http://feed43.com/2738718687802442.xml> RSS 源；  
Edit URL: <http://feed43.com/feed.html?name=2738718687802442> 用于修改 RSS 源；  


## 二、 进阶操作
- 如果要换一个网站订阅，一定要重新打开 feed43 网页，因为一个网页只会生成一个订阅页面，如果重复编辑，则会发生覆盖；  
- feed43 RSS 只能抓取页面中的内容，如果想在 rss 展示全文，需要通过 [FeedEx](https://feedex.net/) 再转一次；     
- 加密：生成的链接不想让别人编辑   
  - 注册帐号，在帐号内创建 RSS 即可；如需编辑，则需输入该链接密码（默认是帐号密码）；
- 删除 RSS 源  
  前提是在个人账户下，在个人列表中找到他，然后点击标题左侧的小三角展开后，点击删除即可；  
- 将原有的「野生」RSS 纳入个人帐号下
  点击页面底端的「Add feeds to your account / Undelete feeds」，输入 RSS ID 即可；    
- 删除后的 RSS 如何恢复  
  同上一条一样，输入 RSS ID 即可；前提是你记得 ID ，且在删除后 30 天之内；

## 三、 会员的苦恼



## 附录
### A 推荐资料

[1].  少数派Matrix. 使用 RSS 可以做什么你未曾想过的事[EB/OL]. <https://sspai.com/post/34280>. 2016-05-18/2019-02-15.   

### B 参考资料

[1].  无双武士. FEED43新手教程：为任意网页定制RSS格式订阅源[EB/OL]. <https://post.smzdm.com/p/553684/>. 2017-04-24/2019-02-18.   
