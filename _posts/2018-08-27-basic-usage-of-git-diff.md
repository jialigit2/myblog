---
layout: blog  
title:  git diff 命令的基本用法
category:  IT
---
### git diff 命令的基本用法

![](/img/blog/git-cartoo.jpeg)

1.比较工作树和缓存之间的差别

```git diff ```

2.查看已经暂存起来的文件(staged)和上次提交时的快照之间(HEAD)的差异

```git diff --cached```

3.显示工作版本(Working tree)和HEAD的差别

```git diff HEAD```

4.直接将两个分支上最新的提交做diff

```git diff topic master```

5.查看简单的diff结果，可以加上--stat参数

```git diff --stat```

6.查看本地库和远程仓库的差别

```git diff master origin/master```

