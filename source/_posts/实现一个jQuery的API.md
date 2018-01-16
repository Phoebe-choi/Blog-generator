---
title: 实现一个jQuery的API
date: 2018-01-12 14:39:25
tags: jQuery
categories: jQuery
---
##### 实现一个jQuery的API
- 传一个选择器或节点
```
window.jQuery = function(nodeOrSelector) { 
  let nodes = {}    
  if (typeof nodeOrSelector === "string") {   
    let temp = document.querySelectorAll(nodeOrSelector)
    for (let i = 0; i < temp.length; i++) {   
      nodes[i] = temp[i]     
    }
    nodes.length = temp.length
  } else if (nodeOrSelector instanceof Node) {
    nodes = {
      0: nodeOrSelector,
      length: 1
    }
```
- 为nodes添加类，并且遍历nodes
```
  nodes.addClass = function(classes) {
     var classes = [classes] 
      classes.forEach((value) => {
        for (let i = 0; i < nodes.length; i++) { 
          nodes[i].classList.add(value)
        }
      })
    }
```
- 遍历nodes，并且改变类的文本
```
  nodes.setText = function(text) {
    for (let i = 0; i < nodes.length; i++) { 
      nodes[i].textContent =text
    }
  }
  return nodes
}
```
- 调用API操作nodes
```
window.$ = jQuery
var $div = $('div') 
$div.addClass('red') // 可将所有 div 的 class 添加一个 red
$div.setText('hi') // 可将所有 div 的 textContent 变为 hi
</script>
```
##### 完整代码
```
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>

<body>
  <div id="a">red</div>
  <div id="b">red</div>
  <div id="c">red</div>
  <div id="d">red</div>
  <div id="e">red</div>
</body>
</html>

<script>
window.jQuery = function(nodeOrSelector) {
  let nodes = {}      //用nodes把节点和选择器都装起来
  if (typeof nodeOrSelector === "string") {  //判断一下nodeOrSelector是节点还是一个选择器
    let temp = document.querySelectorAll(nodeOrSelector)
    for (let i = 0; i < temp.length; i++) {   //遍历所有的节点并且把它们都添加到nodes里
      nodes[i] = temp[i]     
    }
    nodes.length = temp.length
  } else if (nodeOrSelector instanceof Node) {
    nodes = {
      0: nodeOrSelector,
      length: 1
    }
  }

  nodes.addClass = function(classes) {
     var classes = [classes] 
      classes.forEach((value) => {
        for (let i = 0; i < nodes.length; i++) {   //遍历nodes
          nodes[i].classList.add(value)
        }
      })
    }
  
  nodes.setText = function(text) {
    for (let i = 0; i < nodes.length; i++) { 
      nodes[i].textContent =text
    }
  }
  return nodes
}

window.$ = jQuery
var $div = $('div') 
$div.addClass('red') // 可将所有 div 的 class 添加一个 red
$div.setText('hi') // 可将所有 div 的 textContent 变为 hi
</script>
  
```