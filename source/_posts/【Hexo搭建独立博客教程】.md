---
title: 【Hexo搭建独立博客教程】
date: 2017-11-15 20:58:03
tags: Hexo
categories: Hexo
---

### 准备工作

- 在开始一切之前，你必须已经：

1. 有一个github账号，没有的话去注册一个；

2. 安装了node.js（官网下载安装），默认会安装npm。

3. 安装git（官网下载安装）

4. 安装hexo了，方法：打开git，输入cd运行npm install -g hexo（要翻墙）

### 开始搭建

1. 打开git，然后**cd~/Desktop**

2. 登录GitHub，在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」。（请将你的用户名替换成真正的用户名

3. 建立好空repo后，回到git命令行界面

4. 运行**npm install -g hexo-cli**，安装Hexo

5. 继续运行**hexo init myBlog**

6. 继续运行**cd myBlog**

7. 继续运行**npm i**

8. 运行**hexo new开博大吉**，你会看到一个md文件的路径

9. 运行**start xxxxxxxxxxxxxxxxxxx.md**，编辑这个md文件，内容自己想（Ubuntu系统用xdg-open xxxxxxxxxxxxxxxxxxx.md命令）

10. 继续运行**start _config.yml**，编辑网站配置

    - 把第 6 行的 title 改成你想要的名字 

    - 把第 9 行的 author 改成你的大名 

    - 把最后一行的 type 改成 type: git

    - 在最后一行，在 type 下面，加上一行 **repo: 仓库地址** ，  仓库地址改为「你的用   户名.github.io」，仓库地址以 git@github.com: 开头格式如下

                    > repo:  git@github.com:你的用户名.github.io

    - 第 4 步的 repo:  后面有个空格，不要眼瞎
11. 继续运行**npm install hexo-deployer-git --save**，安装git部署插件

12. 继续运行**hexo deploy**

13. 到这里博客已经搭建好了，打开Github，进入「你的用户名.github.io」对应的repo。

14. 你现在应该看到了你的博客了。

### 更换主题

1. [主题](https://github.com/hexojs/hexo/wiki/Themes)上面有主题合集

2. 随便找一个主题，进入主题的GitHub首页，比如我找的是                             [链接](https://github.com/iissnan/hexo-theme-next)

3. 复制它的SSH地址或HTTPS地址，假设地址为 git@github.com:iissnan/hexo-theme-next.git

4. 打开git命令行界面

5. 运行**cd themes**

6. 运行**git clone git@github.com:iissnan/hexo-theme-next.git**

7. 运行**cd ..**　(这里意思是返回上一层)

8. 将_config.yml的第75行改为**theme: hexo-theme-next**，保存

9. 运行**hexo generate**

10. 运行**hexo deploy**

11. 等一分钟，然后刷新你的博客页面，你会看到一个新的外观。如果不喜欢这个主题，就回到第1步，重选一个主题。

至此，博客已经搭建完成了！

