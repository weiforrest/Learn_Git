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

# 查看历史

``` bash
git log #查看历史
-- online 简洁的信息
-nN 最新的N条提交
-all 查看所有的分支记录(默认只是当前分支)
--graph 使用图像显示分支
```





 