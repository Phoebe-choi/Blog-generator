---
title: 如何预览Github上的页面
date: 2017-11-26 11:18:32
tags: Github
categories: Github
---

## 前言

很多新手把自己的网页上传到github仓库中却发现点进去相应的html文件显示出来的是下面代码，而不是自己想在网上看到自己仓库中的demo(也就是网页的效果) 

![img](http://a1.qpic.cn/psb?/V149ONjw3gE9gi/mzPvN6ToHGEKEzW7Lo1cJc94BtleaiIilue4rA45B6Q!/b/dD4BAAAAAAAA&bo=CQQuAgAAAAADBwM!&rf=viewer_4)

那么我们有没有办法预览项目中的html网页呢？好在github已经推出了 GitHub Pages 功能，让大家方便的预览自己的 HTML。下面就给大家做一个简易教程。

## 步骤
**1. 登入 GitHub，新建一个 repo，设置如下：**

![img1](http://a1.qpic.cn/psb?/V149ONjw3gE9gi/SbT1RAeZGsPCG1YHVWxHaqbJZb6iSyXu1aF0abmVxrE!/b/dPMAAAAAAAAA&bo=rgLXAQAAAAADAF8!&rf=viewer_4)

![img2](http://a3.qpic.cn/psb?/V149ONjw3gE9gi/iE72VmBjtSCkLPbsuxfFGBns4zEVnpbULxnVOjgnTZQ!/b/dPIAAAAAAAAA&bo=EgNsAgAAAAADAFo!&rf=viewer_4)

**2. 进入「settings」页面：**

![img3](http://a3.qpic.cn/psb?/V149ONjw3gE9gi/.YA.m6LqpFDfNqxbYG6I8SKkaGIq8FXvDYpL45*5t6E!/b/dGoBAAAAAAAA&bo=uQNpAAAAAAADAPY!&rf=viewer_4)

**3. 往下滚，按照图片中1-2-3的顺序，开启 GitHub Pages 功能，得到一个「预览地址」，我的「预览地址」是 `https://phoebe-choi.github.io/demo/.`**

![img5](http://a1.qpic.cn/psb?/V149ONjw3gE9gi/iVQXXnVQEnODR1AIQD8JHM4QSh8kGRrTkjtWo0*1oxk!/b/dPMAAAAAAAAA&bo=0AJpAQAAAAADAJ8!&rf=viewer_4)

**4. 以后你就用这个「预览地址」来预览你的 html，比如你的 html 路径是 test/index.html，那么预览链接就是 `https://phoebe-choi.github.io/demo/test/index.html` 步骤如下:**

![img6](http://a3.qpic.cn/psb?/V149ONjw3gE9gi/rRqj8jMKvhhsbjssi9zh9UiudPmTCDGv3qXodn4ei20!/b/dFsBAAAAAAAA&bo=0AOmAQAAAAADAFE!&rf=viewer_4)

- 新建 test/index.html

![img7](http://a1.qpic.cn/psb?/V149ONjw3gE9gi/KxFqGmwEyONrHng5kS986J8QtrjFiHVpyxBRibZgcNc!/b/dPMAAAAAAAAA&bo=HQILAgAAAAADADM!&rf=viewer_4)

- 编辑好后点击下方的create new file即可创建文件，根据刚才创建的文件名称的相对路径就可以用「预览地址」来预览html文件了

- 在浏览器输入: `https://phoebe-choi.github.io/demo/test/index.html`进行预览

这样，你就能自己随时预览 GitHub 里的页面了！

以后，**你只需要用 git 上传代码到这个仓库**，就可以拿到作业的预览链接了！
