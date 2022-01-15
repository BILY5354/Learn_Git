# [分支管理](./branch_manage.md)
1. [创建与合并分支](#1)
2. [](#2)
3. [](#3)
4. [](#4)  

# 本节命令

```
git branch							//查看分支
git branch <name>					//创建分支
git checkout <name>					//(方1)切换分支
git checkout -b <name>				//(方1)创建+切换分支
git switch <name>					//(方2)切换分支
git switch -c <name>				//(方1)创建+切换分支
git merge <name>					//合并某分支到当前分支
git branch -d <name>				//删除分支
```



## 1

_创建与合并分支_

- ```git checkout -b dev```相当于执行了```git branch dev```和```git checkout dev```,如果查看分支的话，会发现当前正在使用的分支会有一个```*```。
- **合并**```merge```要留意是什么分支合并什么。

![](img/merge.jpg "切换到mater再merge")

- ```git checkout <branch>```与前面提到的撤销修改```git checkout -- <file>```是同一命令，可使用```git switch```代替。

```
```
## 2
```
```
## 3
```
```
## 4
```
```
