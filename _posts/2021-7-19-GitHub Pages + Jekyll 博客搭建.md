---
layout:     post   #使用布局
title:      "GitHub Pages + Jekyll博客" #文章标题
subtitle:   "博客搭建"  #文章副标题
date:       2021-07-19    #文章时间
author:     "Audrey"     #作者
header-img: "img/post-blog-2021.jpg" #此篇文章背景图
catalog: true  #是否显示分类
# hidden: true  #true则不显示在主页，false或者不设置则显示在主页
tags:   #标签
    - Web前端
    - Blog
---

## GitHub Pages + Jekyll 博客搭建
开始之前请在电脑上配置好jekyll相关插件，具体可百度对应电脑安装jekyll方法
### Github

##### 1.注册github

<img src="/img/post/blog/1.jpg" alt="创建页面"  />

##### 2.创建blog关联仓库

*Repository name 格式必须是：*`你的用户名 . github . io`（例如我的Audrey-Huang.github.io）

<img src="/img/post/blog/2.jpg" alt="在左上角可以看到按钮"  />



### 域名

##### 1.网上有很多域名注册的方法，我选择的是阿里云

##### 2.对域名进行解析

*选择 “ 添加记录 ” 。添加两条：两个都是记录类型 A；一个主机记录 @ ，另一个主机记录 www ；在命令行窗口 ping 要建立博客的 GitHub 仓库名，可以得到一个 IP 地址，示例例如下：*

<img src="/img/post/blog/3.jpg"/>
<img src="/img/post/blog/4.jpg"/>

### 网站统计

*两大统计网站* [Baidu Analytics](https://tongji.baidu.com/web/welcome/login?castk=LTE%3D) *和* [Google Analytics](https://analytics.google.com/analytics/) *，到各个网站按照流程注册得到相对应的* `track_id` *，后续在《博客改造》的 _config.yml 中填入。*

### GIT和SSH配置

Mac配置方法：[mac配置](https://www.jianshu.com/p/7edb6b838a2e)

windows配置方法：[windows配置](https://blog.csdn.net/jal517486222/article/details/79967632)

### 博客模板下载

基于jekyll封装了多种多样的模板，可以去jekyll查看，这里强推Hux封装好的模板，好看且好用！

##### 1.将HUX代码clone到本地

```shell
git clone https://github.com/Huxpro/huxpro.github.io
// 其实可以直接clone我的代码，因为我把无关紧要的展示都已经删除了，这样不会有显示问题
git clone https://github.com/Audrey-Huang/Audrey-Huang.github.io
```

代码结构如下，真正需要我们写的内容都放在**_posts**里面，建议根据原始页面多点点，熟悉整个代码结构。

<img src="/img/post/blog/5.jpg" style="zoom:50%"/>

##### 2.将相应配置修改成自己的信息

**修改_config.yml**

<img src="/img/post/blog/6.jpg"/>

<img src="/img/post/blog/7.jpg"/>

<img src="/img/post/blog/8.jpg"/>
**修改about.html**

将抬头标题部分修改成自己对应的信息。

可以尝试理解下面代码，其实就是把每个小的模块已经封装好了，然后通过{}引用的方式堆叠到about页面上。

<img src="/img/post/blog/9.jpg"/>
about页面显示的文案存放在"_includes/about/zh.md"下，本来有英文版，可以删除，并在about.html源码里面将英文部分删除。

<img src="/img/post/blog/10.jpg"/>
**修改archive.html**

修改header部分信息

代码堆叠方式同上，可适当先了解一下html和css的知识，有助于理解整个blog的封装方法。

<img src="/img/post/blog/11.jpg"/>

**修改index.html**

同样修改header部分信息。

<img src="/img/post/blog/12.jpg"/>

**新建CNAME文件，写上域名**

<img src="/img/post/blog/13.jpg"/>

#### 3.撰写文章

*_posts 存放你写的文章，至于格式，可以上网查阅或是参照我的模板里的文章*

<img src="/img/post/blog/14.jpg"/>

### 博客上传

此步骤即为将本地代码上传到github上main分支内，需提前学习git的命令。
上传时请将jekyll serve启动生成的_site、.jekyll-cache文件删除。
其实生成的文件(即_site,.jekyll-cache文件夹下)都是依据先前配置好的文件，修改生成的文件是没有用的。

```shell
git init                        # 建立一个仓库 

git add .                       # 选择要添加进库的文件（用 . 表示添加该文件夹所有文件）

git commit -m 'upload'          # 添加进入仓库（-m 后面 ' ' 相当于解释提交的内容或是目的）

git remote add origin git@github.com:XXX/XXX.git        # 仓库的SSH地址
                     
                 # 例如我的： git@github.com:Audrey-Huang.github.io.git

git pull origin main         # 多人协同开发下，远程主机分支更新和本地指定分支的合并 

git push -u origin main       # push上传本地文件
```

如有其他问题可百度解决，本人只能做到这里了：）
