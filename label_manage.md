# [标签管理](./label_manage.md)
1. [](#1)
2. [](#2)
3. [](#3)
4. [](#4)  

为啥要用标签？因为原始的版本号根本就不方便查看，所以就用一个标签和一个号对应。

# 本节命令

```
git tag <tagname>									//新建一个标签，默认为HEAD
git tag -a <tagname> -m "blabla..."					//指定标签信息
git tag												//查看所有标签
git push origin <tagname>							//推送一个本地标签
git push origin --tags								//推送全部未推送过的本地标签
git tag -d <tagnanme>								//删除一个本地标签
git push origin :refs/tags/<tagname>				//删除一个远程标签
```



## 1

###　创建标签

**标签总是和某个commit挂钩。如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。**

```
```
## 2

### 操作标签



```
```
## 3
```
```
## 4
```
```