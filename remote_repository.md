# [远程仓库](./remote_repository.md)
1. [远仓基本设置](#1)
2. [推送本仓到远仓](#2) 在本地新建了一个仓库想要推送到远程仓库的操作
3. [从远仓克隆到本地](#3) 在远仓已有仓库，现在需将其克隆到本地的操作
4. [从远仓更新本仓](#4) 已有远仓克隆在本地，现远仓更新了，想本仓更新的操作   
5. [案例：从github更新本仓并推送到gitee](#5)  
# 本节命令
```
git remote add origin git@server-name:path/repo-name.git              # 关联一个远程库,origin是默认习惯命名
git push -u origin master                                             # 第一次推送master分支的所有内容，<origin>是远仓，<master>是本仓
git push origin master                                                # 第一次提交后，就可以使用本命令推送最新修改
git clone git@github.com:BILY5354/hello-world.git                     # 远程库已经准备好后克隆一个本地库
git pull origin master                                                # 从远仓拉取到本地，即更新(需先克隆)，<origin>是远仓
git remote rm <name>                                                  # 解除了本地和远程的绑定关系，并不是物理上删除了远程库
git remote -v                                                         # 查看远程仓库的数量（简单信息）
git remote show origin                                                # 查看某个远程仓库的具体信息，以origin为例：
git branch                                                            # 查看分支信息
```
## 1
_远仓基本设置_
[直接回看教程](https://www.liaoxuefeng.com/wiki/896043488029600/896954117292416#0)，主要是添加公钥到github或gitee。
```cpp
```  
## 2
_推送本仓到远仓_，在本地新建了一个仓库想要推送到远程仓库的操作。  
- 首先在github(gitee也行)上创建一个仓库，注意**这个仓库一定是空的，不要初始化**，也就是readme这些都是没有的。再本地用```git remote add origin git@server-name:path/repo-name.git```创建关联，再用```git push -u origin master```第一次推送**orgin是刚刚创建的关联即远仓，而master是本仓**，以后再次推送就用```git push origin master```即可。
- 如果想既推github和gitee就需要设置多个关联了。
```cpp
```
### push解释
> Form github:
> Use git push to push commits made on your local branch to a remote repository.
> The git push command takes two arguments:
> - A remote name, for example, origin
> - A branch name, for example, master
> For example:  
``` git push <REMOTENAME> <BRANCHNAME> ```也就是git push **远仓** **本仓**   
> As an example, you usually run $ git push origin master to push your local changes to your online repository.  
  
## 3
_从远程仓库克隆_，在远仓已有仓库，现在需将其克隆到本地的操作。  
- 使用```git clone git@github.com:BILY5354/hello-world.git```克隆远仓(注意branch的变化) 。 
![](img/clone_repo1.PNG "克隆远仓")  
当然也可以使用```git branch```查看。
- **本**仓的**branch**别写错了，现在的本仓**branch**是```main```但写了```master```。
![](img/clone_repo2.PNG "写错远仓分支") 
- 远仓克隆下来想要推送**同样也需要创建关联**，否则错误提示：
![](img/clone_repo3.PNG "没有创建关联") 
- 最终顺顺利利。  
![](img/clone_repo4.PNG "") 
```cpp
```  
## 4
_从远仓更新本仓_，已有远仓克隆在本地，现远仓更新了，想本仓更新的操作。  使用```git pull  <REMOTENAME> <BRANCHNAME>```,也就是git push **远仓** **本仓**。
```cpp
```  
## 5  
_案例：从github更新本仓并推送到gitee_，**[确保github与gitee已经添加了SSH公钥](#1)**，**并且已经将远仓克隆到本地**，这个案例是如果远仓(github)修改了一些文件，则本地需要更新并推送到gitee远仓上。  
1. 查看本地与github、gitee的关联，如没有则添加
2. 使用```pull```拉取远仓更新本仓，可以看到修改的内容(新增了test.md，修改了两个文件)
3. 本仓更新成功后推送到gitee远仓
![](img/pull_push.PNG "案例过程")  
```cpp
``` 

