# Git命令

## git常用命令

* ```git branch``` 查看本地仓库

* ```git branch -a   ``` 查看全部分支

* `git branch -r`  查看远程仓库

* `git branch 分支名 `  创建本地分支

* `git branch -d 分支名 `  删除本地仓库

* `git checkout -b 分支名` 复制当前所在分支创建新分支

* `git checkout -b 本地分支名 origin/远程分支名 ` 复制指定远程分支并创建本地分支

* ` git merge 分支名 `  合并分支（将当前分支合并到指定分支）

* `git reset` 撤销全部标记文件( *  或者 .  全部)

* `git reset --head 文件名` 撤销指定标记文件

* **情况一：撤销指定文件到指定版本**

  ```reStructuredText
  查看指定文件的历史版本
  git log <filename>
  回滚到指定commitID
  git checkout <commitID> <filename>
  ```

* **情况二：删除最后一次远程提交**(回滚版本)

  * *方式一：使用revert*

  ```reStructuredText
  git revert HEAD
  git push origin master
  ```

  - *方式二：使用reset*

  ```reStructuredText
  git reset --hard HEAD
  git push origin master -f
  ```

  *二者区别：*

  - **revert**是放弃指定提交的修改，但是会生成一次新的提交，需要填写提交注释，以前的历史记录都在；
  - **reset**是指将HEAD指针指到指定提交，历史记录中不会出现放弃的提交记录。

* 回滚merge操作后版本

  ```java
  ⑴ 查看merge操作的上一个提交记录的版本号
  git reflog
  ⑵ 回滚到merge之前的状态
  git reset --hard 版本号
  ```

  

* ```git pull``` 拉取最新代码

* `git add 文件名 `  标记文件(*或者. 全部)

* `rm 文件名`  删除本地未被追踪文件

* `git rm 文件名`  删除文件

* `git rm -r 文件夹名 ` 删除文件夹

* ```git commit -m '注释'```  提交文件

* ```git push```  提交文件推送到远程

* `  git push origin 分支名 `  将新分支发布到远端仓库

* `git push origin 分支名 --force` 强制推送

* ` git push origin :分支名 `  删除远端一个分支   (分支名前的冒号代表删除) 

* `git remote -v` 查看远程仓库地址

* `git show <commitID> ` 查看指定log日志

## 代码冲突解决

1. `git stash` 本地备份
2. `git pull` 更新代码
3. `git stash pop` 将备份代码跟更新代码合并