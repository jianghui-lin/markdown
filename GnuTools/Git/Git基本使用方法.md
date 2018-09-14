# 查看版本(Cygwin版本的git)

git --version

```
$ git --version
git version 2.17.0
```

# Git配置

git config -l

```
$ git config -l
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
```

git config --global user.name "Linjianghui"

git config --global user.email "jianghui.lin@outlook.com"

```
$ git config -l
user.name=Linjianghui
user.email=jianghui.lin@outlook.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
```

# 生成SSH秘钥对

ssh-keygen      并将公钥id_rsa.pub内容添加到github账户上

```
$ ls -a ~/.ssh/
.  ..  id_rsa  id_rsa.pub
```

ssh -T git@github.com       测试ssh连接

# Git初始化

git init          -- Create an empty Git repository or reinitialize an existing one

```
$ ls ~/.git/
config  description  HEAD  hooks  info  objects  refs
```

# Git版本控制

![](.\pic\git_workspace_stage_repository.jpg)

## Workspace <--> Stage

Add changes to Stage/Remove changes from Stage.

```
git add _filepath_  
git rm --cached _filepath_
```

Discard changes in workspace.

```
git checkout -- _filepath_
```



## Stage <--> Repository

git commit -m "_message_"      -- Commit changes to Repository

## Repository <--> Remote

Create a repository on Github firstly.

Add a remote for the repository at url.

```
git remote add origin git@github.com:jianghui-lin/gitusage.git
git remote show
git remote show origin
```

Push changes to Remote

```
git push origin master
git remote show
git show
```



# Git版本比较

# Git查看log

```
git log
git log --pretty=oneline
git reflog
```

# 更多Git命令用法

## git add

- git add . 

  监控工作区的状态树，使用它会把工作时的**所有变化提交**到暂存区，包括文件内容修改(modified)以及新文件(new)，但不包括被删除的文件。

- git add -u 

  仅监控**已经被add的文件**（即tracked file），他会将被修改的文件提交到暂存区。add -u 不会提交新文件（untracked file）。（git add --update的缩写）

- git add -A 

  是上面两个功能的合集（git add --all的缩写）



