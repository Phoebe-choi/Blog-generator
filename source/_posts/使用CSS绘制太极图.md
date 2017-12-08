---
title: 使用CSS绘制太极图
date: 2017-11-25 16:57:55
tags: CSS
categories: CSS
---

**首先画一下最外层的圆圈，并且左右两个半圆的背景设置成不同的颜色，分别代表阴阳。**

```css
.taiji{
    border-style:solid;
    width:0;
    height:201px;
    border-radius:100%;
    border-right: 105px solid black;
    border-left:105px solid white;
    box-shadow: 0 0 25px 0 #333;
    margin: auto;
  }
  ```
显示效果
![taiji](http://a1.qpic.cn/psb?/V149ONjw3gE9gi/*CTNunxM0qx.gfR0ux1fv8UgkLNtdQOMf8isFJpNNqY!/b/dPMAAAAAAAAA&bo=IgH8AAAAAAADAPo!&rf=viewer_4)


**然后画一个黑色的小空心圆，用`margin`对齐**

```css
.taiji .black{
  border:39px solid black;
  background-color: white;
  width: 25px;
  height: 25px;
  border-radius: 100%;
  margin-top: -3px;
  margin-left:-54px;
  }
  ```

 显示效果
 ![img](http://a3.qpic.cn/psb?/V149ONjw3gE9gi/Nsjy1pVX0R2MVbO0wrLnHy4JlagZo6OgULOJ9oq6*MQ!/b/dGoBAAAAAAAA&bo=NAH5AAAAAAADB.4!&rf=viewer_4)

  **最后把白色的空心圆也补上**

  ```css
  .taiji .white{
    display: block;
    background: black;
    border:39px solid white;
    width:25px;
    height:26px;
    border-radius:100%;
    margin-top:0px;
    margin-left:-56px;
  }
  ```
 完工！
 ![white](http://a3.qpic.cn/psb?/V149ONjw3gE9gi/HYcsZ1sDOHhaZhvX5XP5ZcCqelOJ1bIfnDkPCwOWkc8!/b/dPIAAAAAAAAA&bo=QwH8AAAAAAADB5w!&rf=viewer_4)

 >类似这种用CSS做出来的小玩意在这个网站上还有很多，非常有趣，打开看看吧 [Tricks](https://css-tricks.com/)