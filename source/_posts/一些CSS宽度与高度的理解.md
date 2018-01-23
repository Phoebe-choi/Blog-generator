---
title: 一些CSS宽度与高度的理解
date: 2018-01-17 15:02:47
tags: CSS
categories: CSS
---

### 宽度与高度
- 如果div里面有一个内联元素，那么这个div的高度就是内联元素的这一行的行高决定的。
>当我们写一个div并且不给任何样式的时候，div的高度为0.但是当我们给这个div添加一个字并且给CSS样式加一句`font-size：20px;`的时候，div的高度却并不是20px，而总是要多几像素，这时就变成了一个不确定的值。这是因为每个字体的设计师都给每一个字体建议了一个字体默认的行高。当然，再给div添加完样式后，行高也可以自己写死(不是绝对的)。
当在div里添加字体的时候，其高度是有行高加字体的建议高度确定的，而不是字体的高度确定的。
- span 是inline元素，是不支持用width来设置宽度的，所以要给span设置宽度的时候要添加`display:inline-block`使span变成`display:inline-block`元素。

- --webkit--  //Chrome、safiri、opera都支持，Firefox和IE不支持


- 实现姓名和联系方式左右对齐效果
```
span::after{
    content:'';
    display:inline-block;
    width:100%;
}
```
![image](https://i.loli.net/2018/01/16/5a5dfc676f2ad.jpg)

- 只要是inline元素，不管是`inline-blok`还是`inline`，两个元素之间有任何看不见的字符，那就是空格![image](https://i.loli.net/2018/01/16/5a5dff8fe2e08.jpg)

- 若是想要把`<li>`之间的缝隙去掉
![image](https://i.loli.net/2018/01/16/5a5e011fd5fb1.jpg)

- 多行文字溢出

[使一段文字变成一行或多行并且多余部分用...显示](https://css-tricks.com/line-clampin/)

![image](https://i.loli.net/2018/01/16/5a5e0571dcead.jpg)

![image](https://i.loli.net/2018/01/16/5a5e06d0a3358.jpg)

- 文字垂直居中

在一个div里把文字垂直居中，不要同时用height设置高度又用line-height设置居中!!!不要同时用height设置高度又用line-height设置居中!!!会造成Bug!

请用下面方案实现
```
line-height
padding
```

- margin
>如果一个div里面还有div，那么这个div的高度就是由它里面div高度的margin+padding+高度决定的。

- div的高度由什么决定的？
>div的高度是由它内部文档流中元素的总和决定的。

- 脱离文档流的办法
```
float:left;
position:absolute;
position:fixed;
```

- div里面的div如何绝对居中(绝对居中就是上下居中，左右居中)？
实现高度不确定，宽度不确定，全屏的居中
![image](https://i.loli.net/2018/01/17/5a5eeed4a4bc5.png)

- 总结
>`margin`和`padding`、`border`可以影响内联元素的宽度，但不影响高度。内联元素的高度是由行高决定的，宽度是由`margin`和`padding`、`border`影响的。

>div的宽度是默认自适应它父元素的宽度。尽量不要去更改一个div的宽度。
>
>div的高度:如果div里面是内联元素，那么div的高度就是内联元素所有的行高加起来。如果是块级元素，就是由它内部的文档流元素高度的总和决定的。

- 实现宽高1比1的自适应div
![image](https://i.loli.net/2018/01/17/5a5ef29e49565.png)

