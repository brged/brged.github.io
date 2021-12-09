---
title: hexo搭建github pages博客
date: 2021-12-09 13:36:41
tags:
---
# 利用Hexo搭建github pages博客
hexo中文官网：[https://hexo.io/zh-cn/](https://hexo.io/zh-cn/)  
hexo中文文档：[https://hexo.io/zh-cn/docs/](https://hexo.io/zh-cn/docs/)  

## 环境依赖
* node.js
* git
## 下载hexo
运行命令:  
`npm install -g hexo-cli`  
等待下载安装完成  
## 使用
### 初始化站点文件夹
``` shell
$ hexo init <folder>  
$ cd <folder>  
$ npm install  
```
等待依赖包下载完成  

### 修改配置文件
6 title: 网站标题  
7 subtitle: 网站副标题  
设置后的呈现效果如下：
![](/images/set-title_and_subtitle.png)  
8 description: 主要用于SEO，一般是该描述该网站的一些关键字  
10 author: 你的名称
url: 该网站的网址
#### 网站部署配置  
使用git部署前，需要安装 hexo-deployer-git：  
`npm install hexo-deployer-git --save`  

104 deploy 
105 type: git（使用git方式部署站点）
106 repo: 你的github page仓库地址
107 branch: master(github使用master分支作为站点)

### 编写博客
在站点文件夹下，运行命令：`hexo new <title>`,这将会在source/_posts文件夹下生成标题为文件名的md文件  
在文件末尾（也就是 --- 下面）写入你的博客并保存修改  
更多的关于写作方面的疑问请参考官方文档：[https://hexo.io/zh-cn/docs/writing](https://hexo.io/zh-cn/docs/writing)  

### 查看效果
本地查看：  
`hexo server` （可能需要安装hexo-server: `npm install hexo-server --save`）  
你的网站可以通过[http://localhost:4000](http://localhost:4000)预览效果

### 部署站点
* 首先需要生成静态文件：  
`hexo generate`  
这将会将编写好的博客发布，并且在站点文件夹下会生成public文件夹  
* `hexo deploy`  
根据配置文件中的部署方式，文件将会提交到对应的仓库  
最后访问你的站点就可以看到你的博客页面了！

### 主题
访问网站：[https://hexo.io/themes/](https://hexo.io/themes/)这里有很多的主题共选择，如知名的[NexT](https://theme-next.js.org/)主题

### 建议将hexo源码保存到仓库另一个分支
``` shell
$ git branch source
$ git checkout source
$ git add .
$ git commit -m "更新信息"
$ git push origin source
```
