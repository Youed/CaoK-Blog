---
title: Hexo + Github Pages搭建个人博客 
date: 2017-07-28 20:33:55
tags: [Github,Hexo]
---

之前博客都是在cnblogs，心血来潮想要自己搭建个人博客，前后花了大半天时间，看了很多相关教程。作为一个Developer，有一个自己的博客，写下自己的经验，写下自己的生活必不可少，积累是一个人一生最宝贵的财富。    
首先我们先了解一下Github，GithubPages，以及hexo。  
**GitHub**    
GitHub是基于git实现的代码托管。  
**GithubPages**  
用户编写的，托管在GitHub上的静态网页。  
**Hexo**   
A fast, simple & powerful blog framework。  
**系统环境配置**  
要使用Hexo，需要在你的系统中支持Nodejs以及Git。   

----------

#### Step1:安装Node.js ####
[下载Node.js](https://nodejs.org/download/ "Step1:安装Node.js")  
参考地址：[安装Node.js](http://www.runoob.com/nodejs/nodejs-install-setup.html "安装Node.js")**（注意node需安装6.2版本以上的，否则不兼容Yilia）**  

----------


#### Step2：安装Git ####
[下载Git](http://git-scm.com/download/ "下载Git")  
这里附一个Git的入门教程。[廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/ "Git教程")  

----------

#### Step3:安装hexo ####  
 ``` shell
$ cd d:/hexo
$ npm install hexo-cli -g  
$ hexo init blog
$ cd blog
$ npm install
$ hexo g # 或者hexo generate
$ hexo s # 或者hexo server，可以在http://localhost:4000/ 查看
 ```

**如果你想折腾，给自己的blog疯狂加插件，这里最好安装cnpm**（[https://npm.taobao.org](https://npm.taobao.org)）防止被墙（我已遇到过），以后将npm换成cnpm即可。命令:  
  ``` shell
$ cd d:/hexo  //进自己的root目录
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
$ cnpm install hexo --save
$ hexo -v 
 ```  
![](http://i.imgur.com/NHajyOH.png)  
Hexo常用的几个命令：  
hexo generate (hexo g) 生成静态文件，会在当前目录下生成一个新的叫做public的文件夹  
hexo server (hexo s) 启动本地web服务，用于博客的预览  
hexo deploy (hexo d) 部署播客到远端（比如github, heroku等平台）  
另外还有其他几个常用命令:  
   ``` shell
$ hexo new "postName" #新建文章 $ hexo new page "pageName" #新建页面
$ hexo n == hexo new 
$ hexo g == hexo generate 
$ hexo s == hexo server
$ hexo d == hexo deploy
$ hexo d -g          #生成部署 
$ hexo s -g          #生成预览
$ hexo s -p 3600     #换端口号。当hexo s -g不起作用主要是2个问题，1.端口冲突，用此命令换端口 2，修改host文件
 ```  
现在我们打开http://localhost:4000/ 已经可以看到一篇内置的blog了。  
#### Step4:安装主题 ####  
Github上最火的主题有NexT与Yilia。想折腾的这里选NexT（官网：[http://theme-next.iissnan.com/](http://theme-next.iissnan.com/)）  
安装主题  
    `$ git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia`  
在Root有两份主要的配置文件，其名称都是 _config.yml。 其中，一份位于站点根目录下主要包含 Hexo 本身的配置，称为**站点配置文件**；另一份位于主题目录下，这份配置由主题作者提供，主要用于配置主题相关的选项，称为**主题配置文件**。
想要搭配自己的插件即配置这2个文件。  
#### Step5:发布Blog ####  
第一次登录需要验证身份信息:  
   ``` shell
$ git config --global user.name "你的用户名"
$ git config --global user.email "你的邮箱"
$ cnpm install hexo-deployer-git --save  //安装Git插件
$ hexo new "hello"  #生成一个md文件(/blog/source/_posts/),用编辑器打开hello.md文件,编写完后保存
$ hexo s -g   # 一般先在本地预览
$ hexo d -g   #发布成功后，访问yourname.github.io看下成果
 ``` 
 





