# git
git相关

# git
git相关


git init : 将当前目录初始化为一个git可以管理的仓库，并在当前文件夹下创建一个.git文件夹.

git clone [url] 从指定目录克隆一个项目到当前目录，自动变成git可以管理的仓库，clone下来的repo会以url最后一个斜线后面的名称命名,创建一个文件夹,如果想要指定特定的名称,可以git clone [url] newname指定.

git config [--global] user.name ""   git config [--global] user.emailn ""
顾名思义设置一个用户名和邮箱,主要用于在提交代码时显示,方便别人知道这个代码是谁提交的,但只在当前仓库中起作用,如果加上----global参数 则会在所有仓库都显示这个用户名和邮箱.

git add filename 将文件添加到暂存区

git add -A  添加当前工作区所有修改文件到暂存区

git commit -m "" 将暂存区的文件都提交到本地仓库， 加-m 是对本次提交的注释 ，在后面的双引号里面填写

git status 查看本地仓库的状态，可以看到那些文件被修改，那些在暂存区，git status -s s是short ,-s的输出标记会有两列,第一列是对staging区域而言,第二列是对working目录而言.

git diff 文件名 :如果文件修改了,已经添加到暂存区,我们希望看一下文件具体哪些内容被修改了,可以使用此命令,能够看到具体修改了的内容,
此命令比较的是工作目录中当前文件和暂存区域快照之间的差异,也就是修改之后还没有暂存起来的变化内容.

git diff –cached:若要看已经暂存起来的文件和上次提交时的快照之间的差异

git diff [version tag] 查看某个版本之后修改了什么，可以加上-stat,简化输出



git log 查看项目的提交日志,包含一个版本号,提交者的名称和邮箱,提交日期,以及提交时添加的注释.
show commit history of a branch.
git log –oneline –number: 每条log只显示一行,显示number条.
git log –oneline –graph:可以图形化地表示出分支合并历史.
git log branchname可以显示特定分支的log.
git log –oneline branch1 ^branch2,可以查看在分支1,却不在分支2中的提交.^表示排除这个分支(Window下可能要给^branch2加上引号).
git log –decorate会显示出tag信息.
git log –author=[author name] 可以指定作者的提交历史.
git log –since –before –until –after 根据提交时间筛选log.
–no-merges可以将merge的commits排除在外.
git log –grep 根据commit信息过滤log: git log –grep=keywords
默认情况下, git log –grep –author是OR的关系,即满足一条即被返回,如果你想让它们是AND的关系,可以加上–all-match的option.
git log -S: filter by introduced diff.
比如: git log -SmethodName (注意S和后面的词之间没有等号分隔).
git log -p: show patch introduced at each commit.
每一个提交都是一个快照(snapshot),Git会把每次提交的diff计算出来,作为一个patch显示给你看.
另一种方法是git show [SHA].
git log –stat: show diffstat of changes introduced at each commit.
同样是用来看改动的相对信息的,–stat比-p的输出更简单一些.





　　git reset --hard HEAD^ :回退到上一个版本,如果使用两个^就是回退到上上个版本

 　  git reset --hard 76786554  :根据版本号回退到指定版本,版本号可以通过git log 查看,版本号很长,取前几位即可 

 　  git checkout --a.txt    :撤销对a.txt的修改,这里分两种情况,1 如果a.txt已修改,但未提交到暂存区,则会将a.txt撤销到和版本库相同的状态. 2 如果a.txt已经添加到暂存区又做了修改,则会将a.txt撤销到刚添加到暂存区时候的状态.

　　git reset HEAD a.txt   :如果a.txt已经修改并添加到暂存区,但我们希望将它撤回到工作区,使用此命令 

　　git rm a.txt   :从版本库中删除a.txt

　　git pull <远程主机名> <远程分支名>:<本地分支名>:   取回远程主机某个分支的更新，再与本地的指定分支合并

　　git pull origin develop:master: 取回远程主机的develop分支与本地的master分支合并

　　git push <远程主机名> <本地分支名>:<远程分支名>: 将本地指定分支的更新,推送到远程主机的指定分支

 　  git push origin master  :将本地库的master分支项目push到远程库中

　　git branch   :查看当前分支

　　git branch -r:查看远程分支

　　git branch -a: 查看所有分支

　　git branch develop:从当前分之中创建一条名为develop的分支

　　git checkout develop:从当前分支跳转到名为develop的分支上去

　　git checkout -b develop :从当前分支创建一条名为develop的分支并且跳转到该分支上去,相当于上面两条命令的简化

　　git merge develop:将名为develop的分支合并到当前分支上来

　　git branch -d develop: 将名为develop的分支删除
