---
title: GitHub page + Hexo 搭建个人博客
date: 2023-05-30 14:33:50
tags:
- hexo
- git
- next
categories:
- blog
---
### 搭建

#### Hexo

1. 全局安装

   ```bash
   npm install -g hexo-cli
   ```

2. 相关命令

   ```bash
   hexo init   #初始化
   hexo g      #静态部署
   hexo s      #启动本地服务器
   hexo d      #部署到仓库
   hexo clean  #清楚缓存文件db.json和已生成的静态文件public
   ```

<!-- more -->

#### GitHub page

1. 新建仓库，仓库名格式：用户名.github.io
2. 关联 Hexo 在本地生成的仓库
3. Push 框架生成的静态资源到 GitHub 仓库
4. 访问 GitHub page 地址查看博客

#### Next

1. 下载 [Next](https://github.com/theme-next/hexo-theme-next) 主题至 blog/themes 目录下
2. 在根目录下的 _config.yml 配置文件中修改主题

#### 域名（可选）

1. 购买域名
2. 解析域名（可以通过 ping <用户名.github.io> 得到 ipv4 地址）
3. 替换访问地址

#### 添加本地搜索功能

1. 添加插件

   ```bash
   npm install hexo-generator-searchdb --save
   ```

2. 配置根目录下的 _config.yml

   ```yaml
   search:
     path: search.xml
     field: post
     content: true
     format: html
   ```

3. 配置主题文件根目录下的 _config.yml

   ```yaml
   local_search:
     enable: true
   ```

### 使用

1. 配置

   [Hexo 配置文档](https://hexo.io/zh-cn/docs/configuration)

2. 编辑

   ```bash
   #layout包含post、page、draft
   #post是新博客
   #page是新页面
   #draft是新草稿
   hexo new [layout] <title>
   ```

### BTW

1. 使用 Hexo 搭建的博客，远程仓库中只保存了 Hexo 发布后的静态文件，而书写博客的 markdown 文件和配置文件等储存在本地，一旦更换操作环境就没法继续书写博客，可以将源码上传的仓库的新分支中解决这一问题。

   ```bash
   git branch -a            # all 查看所有分支
   git branch -r            # remote 查看远程分支
   
   git branch [分支名]       # 新建分支
   git checkout [分支名]     # 切换分支
   
   git add .                # 添加所有文件到暂存区
   git add [文件名]          # 添加指定文件到暂存区
   git commit -m 'mark'     # 将暂存区内容添加到本地仓库
   git push origin [分支名]  # 推送本地仓库到远程仓库
   ```

2. 图片上传问题解决方法：[javascript - hexo 图片路径错误/.com// - SegmentFault 思否](https://segmentfault.com/q/1010000020310187)



​	参考链接：

​	[从零开始搭建个人博客](https://zhuanlan.zhihu.com/p/102592286)

​	[使用git分支保存hexo博客源码到github](https://zhuanlan.zhihu.com/p/71544809)

​	[文档 | Hexo](https://hexo.io/zh-cn/docs/)

​	[theme-next/hexo-theme-next: Elegant and powerful theme for Hexo. (github.com)](https://github.com/theme-next/hexo-theme-next)
