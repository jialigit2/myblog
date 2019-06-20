---
layout: blog  
title:  git 常见问题解决办法总结
tags: Git IT
---
<br/>
> 更多关于 Git 的问题，请参考>> [Git 问答][Git-queestions&Answer]

[Git-queestions&Answer]:https://www.git-tower.com/learn/git/faq/ignore-tracked-files-in-git
###### 下面我罗列了一些平时项目中遇到的常见问题及其解答，希望对您有帮助。
1.Git 怎么跟踪或者不跟踪（忽略）文件？

	我们正常的操作流程是：
	1.新建一个库，初始化
	2.在开始第一次提交之前就编辑好gitignore，里面包含我们的需要忽略的文件夹/文件的模式。
	3.然后，我们开始提交变更。

那么，如果我们不小心一开始的模式定义有问题，漏了一些本该忽略的文件，结果把这些文件给提交到库里去了，怎么办呢，请参看下面问题3.


2.gitignore模式（pattern）有哪些？

	1. 具体的文件名如 secret.txt 忽略这一个文件
	2. 通配符 *.class 忽略所有的class文件
	3. 文件夹 如 target/ 忽略所有文件夹target下的所有文件




3.如果一个本不应该跟踪文件前面不小心提交到库上了，现在怎么让它在ignore生效？

	面对这个问题，我们需要做下面两个步骤：
	1.编辑 .gitignore文件，加入我们要忽略的文件pattern
	2.执行 git rm --cached  filepath 如:git rm --cached a.txt
	3.提交 git add .  ; git commit


更多请看[stackoverflow][stackoverflow_question]上的讨论。

[stackoverflow_question]:https://stackoverflow.com/questions/7527982/applying-gitignore-to-committed-files

4.怎么清理库中未跟踪的文件？

	git clean 命令
	有几个选项很有帮助,您可以通过git help clean来查看具体帮助信息：
	- 查看clean会清理哪些文件：git clean -dn 
	- 执行清理用这个命令：git clean -df

5.如何更快的克隆？
	请用
	···--depth=n ··· 选项，这样您就只会克隆最近的n次提交，而不是全部。