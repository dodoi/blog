---
title: github + hexo 快速搭建博客
date: 2017-01-19 11:02:57
tags: [github,blog]
---
作为一个技术同学，搭建一个github博客是很有必要的，博客可以帮助我们技术很好的积累，也是一个很好展示自己的方式。

## 开始搭建

### 环境准备
1.安装git
2.安装nodejs
3.安装hexo

利用npm安装hexo即可
```
npm install -g hexo
```
如果安装不成功，设置一下代理即可
```
npm config set registry http://registry.cnpmjs.org
```
### 创建hexo文件夹
在你的博客开发目录（如 D:/workspak/dodoi.github.io）下，执行命令(在Git bash下执行)
```
hexo init
```
安装依赖包
```
npm install
```
### 本地查看
执行命定，本地查看博客  localhost:4000
```
hexo generate
hexo server
```

## 发布到github

Hexo 提供了快速方便的一键部署功能，让您只需一条命令就能将网站部署到服务器上。
```
hexo deploy
```

### 全局配置 _config.yml

``` bash
# Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/
# Site #站点信息
title:  #标题
subtitle:  #副标题
description:  #站点描述，给搜索引擎看的
author:  #作者
email:  #电子邮箱
language: zh-CN #语言
# URL #链接格式
url:  #网址
root: / #根目录
permalink: :year/:month/:day/:title/ #文章的链接格式
tag_dir: tags #标签目录
archive_dir: archives #存档目录
category_dir: categories #分类目录
code_dir: downloads/code
permalink_defaults:
# Directory #目录
source_dir: source #源文件目录
public_dir: public #生成的网页文件目录
# Writing #写作
new_post_name: :title.md #新文章标题
default_layout: post #默认的模板，包括 post、page、photo、draft（文章、页面、照片、草稿）
titlecase: false #标题转换成大写
external_link: true #在新选项卡中打开连接
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
highlight: #语法高亮
  enable: true #是否启用
  line_number: true #显示行号
  tab_replace:
# Category & Tag #分类和标签
default_category: uncategorized #默认分类
category_map:
tag_map:
# Archives
2: 开启分页
1: 禁用分页
0: 全部禁用
archive: 2
category: 2
tag: 2
# Server #本地服务器
port: 4000 #端口号
server_ip: localhost #IP 地址
logger: false
logger_format: dev
# Date / Time format #日期时间格式
date_format: YYYY-MM-DD #参考http://momentjs.com/docs/#/displaying/format/
time_format: H:mm:ss
# Pagination #分页
per_page: 10 #每页文章数，设置成 0 禁用分页
pagination_dir: page
# Disqus #Disqus评论，替换为多说
disqus_shortname:
# Extensions #拓展插件
theme: landscape-plus #主题
exclude_generator:
plugins: #插件，例如生成 RSS 和站点地图的
- hexo-generator-feed
- hexo-generator-sitemap
# Deployment #部署，将 lmintlcx 改成用户名
deploy:
  type: git
  repo: 刚刚github创库地址.git
  branch: master
```
需要安装 hexo-deployer-git
```
$ npm install hexo-deployer-git --save
```
修改配置
```
deploy:
  type: git
  repo: <repository url>
  branch: [branch]
  message: [message]
```
|参数	|描述|
|-----|-----|
|repo	|库（Repository）地址|
|branch	|分支名称。如果您使用的是 GitHub 或 GitCafe 的话，程序会尝试自动检测。|
|message	|自定义提交信息 (默认为 Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }}|
|More info: |[Deployment](https://hexo.io/docs/deployment.html)|
