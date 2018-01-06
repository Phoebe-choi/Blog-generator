---
title: Js里的类型转换
date: 2018-01-01 16:16:31
tags: JavaScript
categories: JavaScript
---

### JS里的类型

##### 类型转换
- 基本类型
`number` `string` `boolean` `symbol` `null` `undefined` 
- 复砸类型
`object`

##### 转字符串string
- 方法1：使用toString()转换字符串，如图
![](http://upload-images.jianshu.io/upload_images/8532417-97e6f2b76dbca503.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/8532417-d4904b2aaac8a5c5.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


上图中可以看到，使用`toString()`方法把数据类型转换字符串，只有`number` `boolean` 可以转换成功，而`null`和`undefined` 则返回了一条**Cannot read property 'toString' of null** ，说明`null`和`undefined`无法使用toString()转换字符串，那么只能使用其它方法。

- 方法2：使用 `+ ''`或`'' +` 转换字符串**（推荐用此法来转换字符串）**，如图
![](http://upload-images.jianshu.io/upload_images/8532417-82cb876694ae939d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
图中可以看到，不管是哪一种类型，即使是用toString()转换失败的`null`和`undefined`，只要用`+ ''`或`'' +`，都可以把所有的类型都转换成字符串。`+`号的作用是：如果发现左右任意一边有字符串，它就会自动把另一边也变成字符串。
其实这种方法还有一种经常我们会碰见的奇怪现象，如图中最后几行：
在运行`1+1`的时候，运行结果等于2，而运行`1+'1'`的时候，结果为"11"，其实`1+'1'`等价于`(1).toString()+'1'`,运行出来的结果即为"11"。
- 方法3：使用全局方法`window.String()`，如图
![](http://upload-images.jianshu.io/upload_images/8532417-82607f25c2ee9209.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这三种方法都是可以使用的，但是我比较推荐用第二种，方便很多。

##### 转boolean（记住五个falsy值）
- 方法1，一般用法，直接使用boolean转换，如图
![](http://upload-images.jianshu.io/upload_images/8532417-4263f4d9d692654d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

-方法2，推荐用法，直接用`!!`转换，如图
![](http://upload-images.jianshu.io/upload_images/8532417-c944d77d8750a646.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在js里面，其它的值转换成布尔的时候，有五个特殊的值需要记住的，分别为：
- number
>0=false
>NaN=false
>
>number除了这两个值为false外，其余均为true
- string
>'' =false
>
>
>'' 为空字符串
- null 
>null=false
>
>null本身就为false
- undefined
>undefined=false
>
>undefined本身就为false

`0` `NaN` `''` `null` `undefined`  这五个值均为falsy值(关于falsy可以查阅MDN文档了解)，除了这五个值以外，其余的值转成boolean都为true.
还有一个object类型，这个类型的boolean值全部都是true，包括array和function，都为true.
 
##### 转number
- number('1')===1
- parseInt('1',10)     全局函数
- parsefloat('1.23')===1.23
- '1'-0===1  推荐此法
-  +'1' ===1或 +'-1'=== -1