---
layout: post
title: hexo和GitHub搭建个人博客
date: 2018-11-28 13:16:59
categories: 编程开发
tags:
    - blog
    - Hexo
---

### 一. GitHub创建仓库地址

1.在GitHub上Create a new repository

2.Repository name 填写 yourname.github.io (yourname与你的注册用户名一致, 这个就是你博客的域名了)

<!--more-->

### 二. 环境安装

1.安装node

[node官网](https://nodejs.org/en/, 'node官网')

2.安装git

3.安装Hexo

```
npm install -g hexo-cli
```

### 三. 博客搭建

1.进入到项目根目录

```
hexo init blog
```

2.成功后执行

```
hexo generate

hexo server
```

3.在浏览器输入 http://localhost:4000/ 就可以看见网页和模板了

4.接下来，把网页发布到GitHub上

```
ssh-keygen -t rsa -C "Github的注册邮箱地址"
```

5.配置博客

```
deploy: 
  type: git
  repo: https://github.com/xxx/xxx.github.io.git
  branch: master
```

### 四. 发表文章

```
hexo new 'test'
```

打开test.md编辑一些内容，保存

```
hexo clean

hexo generate

hexo server
```

打开http://localhost:4000/，发现刚才的文章已经成功了

### 五. 最后一步，发布

```
hexo deploy
```

现在打开https://yourname.github.io/ 就可以看到你的博客了

### 六. 错误指南

如果遇到 error deployer not found:git

执行
```
npm install hexo-deployer-git --save
```

> Google是你最好的老师