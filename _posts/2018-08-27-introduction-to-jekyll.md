---
layout: blog  
title:  使用Jekyll 搭建你的个人站点
tags: Jekyll IT
---
### 使用Jekyll 搭建你的第一个 ***个人站点***

<center >
	<img src="/img/blog/jekyll-logo.png" width="80%"/>
</center>
#### Why?
 1. 简单
 - 如果你有一个github账号，那么直接创建一个新的仓库。
 - 去 Settings设置--》Pages 
 <center>
 	<img src="/img/blog/github-pages-settings.png" width="80%"/>
 	
	
</center>
 2. 灵活
 - Jekyll 有丰富的插件，主题，使得您只需要关注内容，从而省去了
 调整样式的烦恼。

 - Jekyl 支持的语法足够灵活，使得搭建个人博客异常轻松。

#### 帮助文档
1. 第一当然是查看[官方的站点帮助](https://jekyllrb.com)。<br/>
   官方文档简介明了的向您解释了jekyll 的种种有点以及您怎么使用它。

2. 这里还有一个关于Jekyll 讨论的社区，如果您有什么问题，可以在上面提问>>[Jekyll Talk][jekyll-talk].

3. 本地调试
   如果您需要本地调试，那么您就需要向官方文档说的那样，在本地安装执行环境了。

#### 关于主题
 - Jekyll 默认的主题是mimima,如果您想使用minima之外的其他主题，那么您需要在配置文件中指定。

   配置文件为：_confi.yml 中theme: minima 中把‘minima'替换为您需要的主题名称比如’jekyll-theme-cayman‘。


 - Jekyll 的主题是基于gem的，但是这些文件你不能在项目的目录中找到。如果你需要覆盖主题的一些内容。在具体操作之前，我们应该先学习一些，Jekyll 主题的一些约定。

 主题提供了layout,includes这些文件。如果我们需要覆盖一个layout，那么就需要 复制 一个对应的文件到自己的项目中。比如你想覆盖主题中一个叫page的布局，那么你就应该复制该文件到项目中，然后更改其内容。

 - 为了复制我们想要覆盖的主题文件，我们先找到这个文件。具体方法为使用命令：

 >```bundle show theme-name```, 

然后打开该文件夹，复制就可以了。

---

直接打主题所在的文件夹，请参考下面的命令。

 
#### On MacOS

<code>open $(bundle show minima)</code>

#### On Windows
<code>explorer /usr/local/lib/ruby/gems/2.3.0/gems/minima-2.1.0</code>

#### On Linux   
<code>xdg-open $(bundle show minima)</code>

[jekyll-talk]: https://talk.jekyllrb.com/


