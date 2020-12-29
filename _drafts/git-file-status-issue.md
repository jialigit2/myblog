Git 基础知识

文件的状态

1. 未被跟踪的文件 (untracked file)
		git status
		git log --graph
		git log -3
2.   已经跟踪但是未暂存的文件 (unstaged file)
	     git add 将未被跟踪和未暂存的文件加入暂存区
	     git checkout 将丢弃对工作区的改动
3.   已暂存未提交( uncommited file)
	
		git reset HEAD <文件>..." 以取消暂存
		git commit 提交暂存区的文件
	（使用 "git rm --cached <文件>..." 以取消暂存
	
	
	
4.   已提交文件  (comitted file)

追加提交 --amend
变基 rebase--合并提交
对比 diff
重置reset --soft/--hard/--mixed
检出checkout
标签 tag
其他： init/clone/push/pull/remote/branches





   

         
      
      


