# Learn_Git
记录我的常用Git命令与学习过程。教程参考自[廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)  
# 基础操作
```
pwd           //显示当前目录
ls -ah        //看隐藏文件
```
## [基础语法和时光穿梭机](./basic_grammer.md)

- [版本回滚（回退）](./basic_grammer.md#1)
- [工作区和暂存区](./basic_grammer.md#2)
- [两种撤销](./basic_grammer.md#3)
- [删除文件](./basic_grammer.md#4)  
## [远程仓库](./remote_repository.md)
- [远仓基本设置](./remote_repository.md#1)
- [推送本仓到远仓](./remote_repository.md#2)   *在本地新建了一个仓库想要推送到远程仓库的操作。*
- [从远程仓库克隆](./remote_repository.md#3) *在远仓已有仓库，现在需将其克隆到本地的操作*
- [从远仓更新本仓](./remote_repository.md#4) *已有远仓克隆在本地，现远仓更新了，想本仓更新的操作*
- [案例：从github更新本仓并推送到gitee](./remote_repository.md#5)  
## [分支管理](./branch_manage.md)
- [基础分支操作](./branch_manage.md#1)
- [不同的分支合并图](./branch_manage.md#2)
- [案例：如何先处理Bug再回到开发分支](./branch_manage.md#3)
- [](./branch_manage.md#4)    

## [标签管理](./label_manage.md)
- [](./label_manage.md#1)
- [](./label_manage.md#2)
- [](./label_manage.md#3)
- [](./label_manage.md#4)  



# 全部Git命令

- 基础语法

```
git init                      //初始化Git仓库
git add <file>                //添加文件
git commit -m <message>       //提交文件
git status                    //了解工作区的状态
git diff                      //查看修改内容（有什么不同）
git log --pretty=oneline      //使log的用一行显示
git log                       //可以查看提交历史，以便确定要回退到哪个版本
git reflog                    //记录我的每一次命令（查看版本号）
git reset --hard HEAD^        //回滚到上一个版本
git reset --hard commit_id    //回滚到指定版本，commit_id是可以通过git log查看（没必要写全）
git checkout -- <file>        //把<文件>在工作区的修改全部撤销(2)恢复一个手动删除但已添加到版本库的文件
git reset HEAD <file>         //将暂存区的修改撤销掉（unstage）,重新放回工作区
```

- 远程仓库

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

- 分支管理

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
git branch -D <name>								//强行删除分支
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

- 标签管理

```
git tag <tagname>									//新建一个标签，默认为HEAD
git tag -a <tagname> -m "blabla..."					//指定标签信息
git tag												//查看所有标签
git push origin <tagname>							//推送一个本地标签
git push origin --tags								//推送全部未推送过的本地标签
git tag -d <tagnanme>								//删除一个本地标签
git push origin :refs/tags/<tagname>				//删除一个远程标签
```



- 

