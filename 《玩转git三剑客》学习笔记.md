# 最小配置

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
-- online 简洁的信息
-nN 最新的N条提交
-all 查看所有的分支记录(默认只是当前分支)
--graph 使用图像显示分支
```

## 修改

``` shell
git commit --amend #修改最新的历史
git rebase -i 修改以前的commit
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
git branch -aV #查看所有分支
git checkout branch_name 切换到指定分支
git branch -d branch_name 删除分支
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



 