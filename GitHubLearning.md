# 创建版本库

```
mkdir learninggit
cd learninggit
pwd ....
```

```
git init
// Initialized empty Git repository in /Users/younggg/Documents/.git/
ls -ah // show .git file
```





git init

git status

git add FriendlyEats/

git add .

git commit -m "FriendlyEats Assignment"

git log 查看历史记录

git remote add origin git@github.com:younggg96/CS6392019.git

git push -u origin master

yangguaengdeMBP:CS6392019 younggg$ git branch -a 

​       master

* origin/master
  remotes/origin/master
  remotes/upstream/master

git checkout -b origin/master

git push origin origin/master



# 删除Branch

**1. 本地分支重命名(还没有推送到远程)**

```
git branch -m oldName newName
```

**2. 远程分支重命名 (已经推送远程-假设本地分支和远程对应分支名称相同)**
 a. 重命名远程分支对应的本地分支

```
git branch -m oldName newName
```

b. 删除远程分支

远程分支如果是default的话不可删除

```
git push --delete origin oldName
```

c. 上传新命名的本地分支

```
git push origin newName
```

d.把修改后的本地分支与远程分支关联

```
git branch --set-upstream-to origin/newName
```

git pull origin + github上的分支名（如：origin/master， master）



remotes/origin/master

git remote rm origin

git checkout -b dev 创建并切换branch

git merge origin/master

git branch -d 删除branch

git branch -d origin/master



# 删除git

```
$ ls -a
=> ./  ../  .git/

$ rm -rf .git // 删除

$ git branch
=> fatal: not a git repository (or any of the parent directories): .git
```





# 删除github 上的文件

在github上只能删除仓库,却无法删除文件夹或文件, 所以只能通过命令来解决



首先进入你的master文件夹下, Git Bash Here ,打开命令窗口

$ git pull origin master                    # 将远程仓库里面的项目拉下来

$ git rm -r --cached target              # 删除target文件夹

$ git commit -m '删除了target'        # 提交,添加操作说明

git push -u origin master

```text
git rm -r --cached .idea  #--cached不会把本地的.idea删除
git commit -m 'delete .idea dir'
git push -u origin master
```



# Git 合并远程分支

步骤
假设你本地在使用的分支为a(master也是一样的)，需要合并的远程分支为b

第一步
在本地新建一个与远程的分支b相同(被合并的版本)的分支b

git checkout -b b origin/b

该指令的意思：创建一个本地分支，并将远程分支放到该分支里面去。

第二步
将远程代码pull到本地

git pull origin b


第三步
返回到你的分支a

git checkout a

第四步
合并分支a与分支b

git merge b

该指令的意思：当前所在分支与b进行合并。

第五步
把本地的分支a同步到远程

git push origin a

第五步
如果你不需要本地或者远程的分支，你可以查询并删除多余分支。

本地
查询本地分支：

git branch
1
删除本地分支:

git branch -D br
1
远程
查询远程分支：

git branch

删除远程分支:

git push origin :br  (origin 后面有空格)
修改本地分支与远程分支的关联：

git branch --set-upstream-to=origin/remote_branch  your_branch



# 开源使用github

Fork 

git clone git@github.com:michaelliao/bootstrap.git





# Vim进入和退出命令

**按ESC键跳到命令模式，然后：**

1. :w 保存文件但不**退出**vi.
2. :w file 将修改另外保存到file中，不**退出**vi.
3. :w! 强制保存，不推出vi.
4. :wq 保存文件并**退出**vi.
5. :wq! 强制保存文件，并**退出**vi.
6. q: 不保存文件，**退出**vi.
7. :q! 不保存文件，强制**退出**vi.
8. :e! 放弃所有修改，从上次保存文件开始再编辑