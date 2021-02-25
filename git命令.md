# Git命令

## 1.仓库初始化

```shell
git init
```

## 2.添加到暂存区

```shell
git add 文件名字
git add .  //添加多个文件到暂存区
```

## 3.提交到仓库

```shell
git commit -m '文件描述'
```

## 4.查看状态

```shell
git status 
git status -s //精简信息
```

## 5.撤销对文件的修改

```shell
git checkout -- 文件名
```

## 6.取消暂存的文件

```shell
git reset HEAD 文件名
git reset HEAD . //全部移除
```

## 7.跳过暂存区

```shell
git commit -a -m "文件描述"
```

## 8.移除文件

从 Git 仓库中移除文件的方式有两种：

① 从 Git 仓库和工作区中**同时移除**对应的文件

② 只从 Git 仓库中移除指定的文件，但保留工作区中对应的文件

```shell
# 从 Git仓库和工作区中同时移除 index.js 文件
git rm -f 文件名字
# 只从 Git 仓库中移除 index.css，但保留工作区中的 index.css 文件
git rm --cached 文件名字
```

## 9.查看历史记录

```shell
# 按时间先后顺序列出所有的提交历史，最近的提交在最上面
git log

# 只展示最新的两条提交历史，数字可以按需进行填写
git log -2

# 在一行上展示最近两条提交历史的信息
git log -2 --pretty=oneline

# 在一行上展示最近两条提交历史信息，并自定义输出的格式
# &h 提交的简写哈希值  %an 作者名字  %ar 作者修订日志  %s 提交说明
git log -2 --pretty=format:"%h | %an | %ar | %s"
```

## 10.回退到指定的版本

```shell
# 在一行上展示所有的提交历史
git log --pretty=oneline

# 使用 git reset --hard 命令，根据指定的提交 ID 回退到指定版本
git reset --hard <CommitID>

# 在旧版本中使用 git reflog --pretty=oneline 命令，查看命令操作的历史
git reflog --pretty=onelone

# 再次根据最新的提交 ID，跳转到最新的版本
git reset --hard <CommitID>
```

