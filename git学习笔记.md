# git学习笔记
---
根据[廖雪峰老师][1]教程学习整理的常用命令
---
## git版本库创建
    git init//初始化一个git仓库
    git add//添加文件到仓库
    git commit//提交文件到仓库
## 文件管理相关
    git status//查看仓库状态
    
    git reflog//查看命令历史（方便回退版本）
    
    git log//查看最近提交日志
    
    git log --pretty=oneline//一行显示
    
    git diff//工作区和暂存区区别
    
    git diff cached//暂存区和版本库比较
    
    git checkout -- file//丢弃工作区修改内容（未提交到暂存区）
    
    git reset --hard commit_id//回到指定id版本（git reflog命令查看commit_id）
    
    git reset HEAD file //回到工作区修改过后的状态（未提交到暂存区，此时可以git checkout -- file）
    
    git rm//删除文件
    /*
    可以理解为
    1.rm file
    2.git add file
    */
## 远程库
    git remote add origingit@server-name:path/repo-name.git//关联一个远程库
    
    git push -u origin master//第一次推送master分支所有内容
    
    git push origin master//最新推送
    
    git clone git@server-name:path/repo-name.git//克隆版本库(后面可以为多种协议)
## 分支管理
    git branch//查看分支

    git branch <name>//创建分支

    git checkout <name>//切换分支

    git checkout -b <name>//创建+切换分支

    git merge <name>//合并某分支到当前分支

    git branch -d <name>//删除分支
    
    git log --graph//查看分支合并图
    
    git merge --no-ff -m "merge with no-ff" dev//普通模式合并，可以看到分支合并图
### bug修复时
    git stash//保存现有工作状态（当前分支）
    
    git stash list//查看保留的工作区
    
    git stash pop//回复修复bug前的工作状态

-----

    git branch -D <name>//强行删除一个没有合并的分支
    
    git remote -v//查看远程库信息
    
    git push origin branch-name//推送本地分支
    
    git pull//抓取远程的新提交
    
    git checkout -b branch-name origin/branch-name//创建本地对应远程仓库的分支
    
    git branch --set-upstream branch-name origin/branch-name//建立本地与远程仓库的关联
    
    
## git标签
    git tag <name>//创建一个标签
    
    git tag -a <tagname> -m "内容"//指定标签内容
    
    git show <tagname>//查看标签说明文字
    
    git push origin <tagname>//推送本地标签
    
    git push origin --tags//推送本地所有未推送标签

    git tag -d <tagname>//删除本地标签
    
    git push origin :refs/tags/<tagname>//删除远程标签


  [1]: https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000
