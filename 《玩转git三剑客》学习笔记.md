#  最小配置

``` bash
git config --global user.name 'your_name' #设置用户名
git config --global user.email 'your_email' #设置email地址
git config --global core.quotepath false #开启工作区的中文显示
```

config 的三个作用域：

--local(默认)当前仓库  --global 当前用户的所有仓库  --system系统的所有用户

```bash
git config --list (--local) #显示当前配置
```

# 建立仓库

``` bash
git init (repo_name)
```

# 添加文件至暂存区

``` bash
git add -u # 更新所有已纳入管理的文件加入暂存区
```

# 重置

``` bash
git reset --hard #把工作区和暂存区的所有修改全部重置
```

# 重命名文件

``` bash
git mv #重命名文件，省去了add和rm的操作
```



# 历史

## 查看

``` bash
git log #查看历史
-- oneline 简洁的信息
-nN 最新的N条提交
-all 查看所有的分支记录(默认只是当前分支)
--graph 使用图像显示分支
```

## 修改

``` shell
git commit --amend #修改最新的历史
git rebase -i 修改以前的commit
```

## 消除最近的几次提交

``` bash
git reset --hard <commit> # 将头指针指向指定的提交，丢弃之后的提交(工作区和暂存区都会被修改)
```

## rebase

``` bash
git rebase -i HEAD~4	# 合并最近四次提交记录
```



# .git 目录

- HEAD 当前工作分支

- config 当前仓库的配置

- refs/heads 所有分支

- refs/tags 所有标签

- object/所有的文件对象

  其中所有的完整hash值为目录加文件hash值

# 分支

``` bash
git branch -v #查看本地分支
git branch -av # 查看所有分支，包括远端仓库分支
git checkout branch_name #切换到指定分支
git branch -d branch_name #删除分支
```

## 合并分支

``` bash
git merge branch_name #合并指定的分支
git merge --allow-unrelated-histories	# 合并两个没有关联的分支
git rebase # 将指定分支的修改按提交顺序在当前分支重放，形成线性的历史。
```

## 创建分支

```bash
git checkout -b local_branch remote_branch # 基于远端分支，创建本地分支并切换到该分支
```



# git文件

``` bash
git cat-file -t  # 查看目标文件的类型
git cat-file -p  # 查看目标文件的内容
```

一个commit对应了一个tree(提交时间节点的仓库快照)。

tree对应文件夹

blob对象对应一个文件(文件内容相同，blob值相同，与文件名无关)

# 分离头指针

detach HEAD ：表示当前提交没有在任何分支中，不收仓库保护，切换到分支是会被清除。

# 差异

``` bash
git diff commit_a commit_b  # 比较两次提交的差异
# HEAD 表示当前提交，HEAD^ 表示HEAD的父提交简写为(HEAD~1) HEAD^^表示HEAD的父提交的父提交，可简写为(HEAD~2)
git diff #比较工作区和暂存区之间的差异
git diff --cached # 比较暂存区HEAD的差异
```

## 不同分支和commit的差异

```bash
git diff br_name1 br_name2 -- <file>	# 比较两个分支的指定文件的差异
```

# 取消暂存区

``` bash
git reset HEAD # 将暂存区保存的修改取消，工作区的修改不变。
git reset HEAD -- <file>	#恢复某个指定的文件
```

# 删除文件

```bash
git rm <file>	# 删除文件
```

# 缓存区

``` bash
git stash	# 将工作区的修改缓存至缓存区
git stash list # 查看缓存区列表
git stash apply # 将缓存区的内容放置工作区
git stash pop # 将缓存区的内容放置工作区，同时删除缓存区的内容
```

# 指定不需要git管理的文件

使用.gitignore 列举不需要改变的文件。文件名后接/，表示目录，如果不接/，如果为文件夹为同名，也不会被管理。

# git备份

##常用的协议有四种

- 本地协议(1)：/path/to/repo.git	哑协议
- 本地协议(2)：file:///path/to/repo.git	智能协议
- http/https协议:http://git-server.com:port/path/to/repo.git 智能协议
- ssh协议: user@git-server.com:path/to/repo.git 智能协议

##智能协议和哑协议

哑协议传输进度不可见；智能协议传输可见。

传输速度：智能协议比哑协议传输速度快。智能协议会压缩。

# 远程仓库

``` bash
git clone --bare 克隆仓库，不带工作区
```

## 添加远程仓库

``` bash
git remote -v	 # 查看远程仓库信息
git remote add # 添加远程仓库分支
git push remote_branch local_branch # 将本地分支推送至远程分支
```

## 拉取远程仓库

```bash
git fetch # 拉取远程仓库
git pull	# 拉取远程仓库，同时与关联的本地分支合并
```

## 推送分支

```bash
git push # 推送到远端仓库分支
git push -f # 强制推送修改到远程仓库
```

# github使用

## 搜索github

1. 搜索指定的文件

    “in:readme”。

2. star大于1000

   “stars:>1000"

3. 指定py文件后缀

   “extension: py"





