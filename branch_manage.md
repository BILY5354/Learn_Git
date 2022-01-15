# [分支管理](./branch_manage.md)
1. [基础分支操作](#1)
2. [不同的分支合并图](#2)
3. [](#3)
4. [](#4)  

# 本节命令

```
git branch											//查看分支
git branch <name>									//创建分支
git checkout <name>									//(方1)切换分支
git checkout -b <name>								//(方1)创建+切换分支
git switch <name>									//(方2)切换分支
git switch -c <name>								//(方1)创建+切换分支
git merge <name>									//合并某分支到当前分支
git merge --no-ff -m "----" <name>					//用普通模式合并，使历史有分支，能看出曾做过合并
git branch -d <name>								//删除分支
git log --graph										//----写信息，查看分支合并图
git log --graph --pretty=oneline --abbrev-commit	//查看分支合并图(一行显示)
git status											//把当前工作现场“储藏”起来，等以后恢复现场后继续工作
git stash list										//查看保存的工作现场
git stash apply										//恢复工作现场(现只有一个工作现场情况，多个需指定)
git stash drop										//删除工作现场(现只有一个工作现场情况，多个需指定)
git stash pop										//恢复工作现场同时将stash内容删除
git stash apply stash@{0}							//恢复指定工作现场
git cherry-pick <commit>							//把在一分支bug提交的修改“复制”到当前分支，避免重复劳动
```



## 1

### 创建与合并分支

- ```git checkout -b dev```相当于执行了```git branch dev```和```git checkout dev```,如果查看分支的话，会发现当前正在使用的分支会有一个```*```。
- **合并**```merge```要留意是什么分支合并什么。因为一般是```dev```分支跑```master```前面，所以在合并时，是**切换回**```master```**分支进行**```merge```命令。
- 总结：稳定分支在后，开发在前，合并时要回到稳定分支使稳定与开发同步。而**不是用**_```dev```去```merge``` ```master```_。

![](img/merge.jpg "切换到mater再merge")

- ```git checkout <branch>```与前面提到的撤销修改```git checkout -- <file>```是同一命令，可使用```git switch```代替。

### 解决冲突

解决冲突的方式就是手动解决。



```
```
## 2

_不同的分支合并图_

### 2.1 正常合并

合并分支时，如果可能Git会使用```Fast forward```模式，简单理解就是默认方式。使用这种模式合并会丢掉分支信息。上图是默认合并前的分支图。下图中在```dev```分支中执行力``` git commit -m "23:39" ```后的分支图。

![](img/merge_pic1.PNG)

![](img/merge_log1_1.PNG)

**默认合并好像就是正常的提交**，合并图并不会显示有合并过的迹象。

![](img/merge_log1_2.PNG )

### 2.2 有冲突的合并

冲突原因是：先在```dev```修改```add```并提交```commit```后在```master```修改并提交，这时候在```master```分支上合并```dev```。合并图与廖老师的为什么不同呢？因为刚刚我的```dev```分支是提交过的，而廖老师的分支是新建的，所以会混了普通模式合并的内容。

记住**有冲突的合并是在合并失败后，手动修改冲突文件再重新修改并提交**便可解决冲突。

![](img/merge_pic2.PNG)

![](img/merge_log2.PNG)

### 2.3 使用普通模式合并

**注意看红框**，合并信息一目了然，易看出分支是合并过的。

![](img/merge_pic3.PNG)

![](img/merge_log3.PNG)







```
```
## 3
```
```
## 4
```
```
