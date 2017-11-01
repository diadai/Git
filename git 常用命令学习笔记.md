以下总结是学习[廖雪峰git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)。写的很好，很浅显易懂，适合新手，推荐大家学习。
####**初始化一个仓库**
```
$ mkdir learngit
$ cd learngit
$ pwd               //显示当前目录
$ git init          //把文件变成git可管理文件
```
####**提交文件到仓库**

```
$ git add 文件名
$ git commit -m "文件的描述"
```
可以add多个文件,commit一次。
####**查看当前状态**

```
$ git status
```
####**查看与之前的不同**

```
$ git diff +文件名
```
注意修改文件后还是要再次commit，步骤和之前提交一样
####**查看从最近到最远的提交日志情况**

```
$ git log
$ git log --pretty=oneline   //查看精简的信息
```
####**退回上一个版本（状态）**

```
$ git reset --hard HEAD^
$ git reset --hard id      //id是commit id（版本号）
$ git reset HEAD 文件名     //把暂存区的修改撤掉
```
HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，以此类推......
####**记录你的每次命令**

```
$ git reflog      //退回到上一个版本还能再返回来
```
####**撤销在工作区的修改**

```
$ git checkout -- 文件名
```
####**删除文件**

```
$ rm 文件名       //在文件管理器中删除文件
$ git rm 文件名   //从版本库中删除文件
```
####**关联远程库**
```
$ git remote add origin git@github.com:name/文件名.git
```
origin 是默认叫法，也可以是其他的，但是这个一看就知道是远程库
####**推送到远程库**

```
$ git push -u origin master   // -u：是第一次推送
```
实际是把分支 master推送到远程，后面就用$ git push  origin master推送更新修改
####**从远程库克隆**
```
$ git clone git@github.com:name/文件名.git
```
####**分支管理**

```
$ git checkout -b 分支名 //创建并切换分支

$ git branch 分支名      //创建
$ git checkout 分支名    //切换
$ git branch            //查看当前分支
$ git merge 分支名       //合并指定分支到当前分支
$ git branch -d 分支名   //删除分支
$ git branch -D 分支名   //强行删除
$ git log --graph       //查看分支合并图
$ git merge --no-ff -m "描述" 分支名  //合并禁用Fast forward
```
####**当前工作暂存**
```
$ git stash
$ git stash pop        //回到工作现场，恢复的同时把stash内容也删了
$ git stash apply  + $ git stash drop  //恢复 删除
```
####**多人合作**
```
$ git remote -v              //显示远程库信息
$ git push origin 分支名      //从本地推送分支
$ git checkout -b branch-name origin/branch-name
                             //创建与远程库同名分支
$ git branch --set-upstream branch-name origin/branch-name
                             //建立本地分支和远程分支的关联
$ git pull                   //从远程抓取分支
```
####**标签管理**

```
$ git tag <name>             //创建标签
$ git tag                    //查看所有标签
$ git tag -a <tagname> -m "描述"  //指定标签信息
$ git show <tagname>         //查看PGP签名信息
$ git push origin <tagname>  //推送一个本地标签
$ git push origin --tags     //推送全部未推送过的本地标签
$ git tag -d <tagname>       //删除一个本地标签
$ git push origin :refs/tags/<tagname>  //删除一个远程标签
```

