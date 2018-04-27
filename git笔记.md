
# 文件的三种状态
对于任何一个文件，在 Git 内都只有三种状态：已提交（committed），已修改（modified）和已暂存（staged）。

已提交表示该文件已经被安全地保存在本地数据库中了；已修改表示修改了某个文件，但还没有提交保存；已暂存表示把已修改的文件放在下次提交时要保存的清单中。

文件流转的三个工作区域：Git 的工作目录，暂存区域，以及本地仓库。

基本的 Git 工作流程如下：
  1. 在工作目录中修改某些文件。
  2. 对修改后的文件进行快照，然后保存到暂存区域。
  3. 提交更新，将保存在暂存区域的文件快照永久转储到 Git 目录中。


# 1、git的安装
###     在Linux上安装Git：
        用Debian或Ubuntu Linux，通过一条sudo apt-get install git就可以直接完成Git的安装，非常简单

###     在Mac OS X上安装Git
    1.安装homebrew，然后通过homebrew安装Git，具体方法请参考homebrew的文档：http://brew.sh/。
    2.直接从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode，选择菜单“Xcode”->“Preferences”，在弹出窗口中找到“Downloads”，选择“Command Line Tools”，点“Install”就可以完成安装了。

###     在Windows上安装Git
        在Windows上使用Git，可以从Git官网直接下载安装程序，（网速慢的同学请移步国内镜像），然后按默认选项安装即可。

​        
# 2、git的配置

    **用户信息**

        $ git config --global user.name "John Doe"
        $ git config --global user.email johndoe@example.com
    
        如果用了 --global 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。
    
    **文本编辑器**
    
        $ git config --global core.editor emacs
    
    **差异分析工具**
    
        $ git config --global merge.tool vimdiff
    
    **查看配置信息**
    
        $ git config --list
    
    **获取帮助**
    
        $ git help <verb>

# 3、 取得项目的 Git 仓库

###     在工作目录中初始化新仓库

        要对现有的某个项目开始用 Git 管理，只需到此项目所在的目录，执行：

        $ git init

        初始化后，在当前目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。不过目前，仅仅是按照既有的结构框架初始化好了里边所有的文件和目录，但我们还没有开始跟踪管理项目中的任何一个文件。

        如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：

            $ git add *.c
            $ git add README
            $ git commit -m 'initial project version'

###     从现有仓库克隆

        克隆仓库的命令格式为 git clone [url]。比如，要克隆 Ruby 语言的 Git 代码仓库 Grit，可以用下面的命令：

        $ git clone git://github.com/schacon/grit.git

###     创建版本库

    第一步，选择一个合适的地方，创建一个空目录：

        $ mkdir learngit
        $ cd learngit
        $ pwd
        /Users/michael/learngit
    
        pwd命令用于显示当前目录。在我的Mac上，这个仓库位于/Users/michael/learngit。
    
        如果你使用Windows系统，为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文。
    
    第二步，通过git init命令把这个目录变成Git可以管理的仓库：
    
        $ git init
        Initialized empty Git repository in /Users/michael/learngit/.git/
    
        瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），细心的读者可以发现当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。
    
        如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。

# 4、git具体操作

####     （1）git status
        可以让我们时刻掌握仓库当前的状态

####     （2）git diff
        可以查看修改内容。

####     （3）git add
        这是个多功能命令，根据目标文件的状态不同，此命令的效果也不同：可以用它开始跟踪新文件，或者把已跟踪的文件放到暂存区，可反复多次使用，添加多个文件，还能用于合并时把有冲突的文件标记为已解决状态等

####     （4）git commit
            $ git commit -m "wrote a readme file"
        告诉Git，把文件提交到仓库，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录，git commit只负责把暂存区的修改提交了，所以每次修改后都要先git add到暂存区后再git commit

####     （5）git log
        显示从最近到最远的提交日志

####     （6）$ git reset --hard HEAD^
        把当前版本回退到上一个版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^,往上100个版本写100个^比较容易数不过来，所以写成HEAD~100

####     （7）git reflog
        用来记录你的每一次命令：通过这个命令你还可以找到回退前的commit id，然后通过$ git reset --hard commit id 回到未来版本

####     （8）git checkout -- file
        把file在工作区的修改全部撤销，是让这个文件回到最近一次git commit或git add时的状态

####     （9）git reset HEAD file
        可以把暂存区的修改撤销掉（unstage），重新放回工作区

####     （10）git rm file
        命令git rm用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容。

# 5、分支管理
####     1.创建dev分支，然后切换到dev分支
    $ git checkout -b dev

    git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
        $ git branch dev
        $ git checkout dev

####     2.用git branch命令查看当前分支
        $ git branch
        * dev
          master
    
        git branch命令会列出所有分支，当前分支前面会标一个*号。

####     3.可以在dev分支上正常提交

####     4.把dev分支的工作成果合并到master分支上
        先切换到master分支
            $ git checkout master
            Switched to branch 'master'
        再$ git merge dev

####     5.删除dev分支
        $ git branch -d dev
        Deleted branch dev (was fec145a).

####     6.遇到合并冲突后先git status定位冲突文件，然后再修改冲突再add,commit提交
        用git log --graph命令可以看到分支合并图

####     7.合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。

####     8.Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：
        $ git stash

        现在，用git status查看工作区，就是干净的（除非有没有被Git管理的文件）

####     9.可以用git stash list查看驻存的内容，用git stash apply或者 git stash pop恢复
        用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；

        用git stash pop，恢复的同时把stash内容也删了

####     10.如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

####     11.要查看远程库的信息，用git remote 或者，用git remote -v显示更详细的信息
        $ git remote
        origin
        
        $ git remote -v
        origin  git@github.com:michaelliao/learngit.git (fetch)
        origin  git@github.com:michaelliao/learngit.git (push)

####     12.推送分支，就是把该分支上的所有本地提交推送到远程库
        $ git push origin master

####     13.在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致

####     14.建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name

####     15.**多人协作的工作模式**(重点)

    a.首先，可以试图用git push origin branch-name推送自己的修改；
    b.如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
    c.如果合并有冲突，则解决冲突，并在本地提交；
    d.没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！
    e.如果git pull提示“no tracking f.information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

# 6.标签管理
##     1.创建标签
    1.切换到需要打标签的分支上：
        $ git branch
    2.敲命令git tag <name>就可以打一个新标签：
        $ git tag v1.0
    3.可以用命令git tag查看所有标签
        $ git tag
    
    如果是对之前的某次提交打标签，可以找到历史提交的commit id
        $ git tag <commit id>
    标签不是按时间顺序列出，而是按字母排序的。可以用git show <tagname>查看标签信息
    还可以创建带有说明的标签，用-a指定标签名，-m指定说明文字：
        $ git tag -a v0.1 -m "version 0.1 released" <commit id>

##     2.操作标签

    1.删除标签
        $ git tag -d v0.1
    2.推送某个标签到远程
        $ git push origin v1.0
    3.一次性推送全部尚未推送到远程的本地标签
        $ git push origin --tags
    4.要删除远程标签就麻烦一点，先从本地删除，然后，从远程删除
        $ git tag -d v0.9
        $ git push origin :refs/tags/v0.9


# 7.忽略特殊文件

    忽略某些文件时，需要编写.gitignore

    .gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理！

# 8.参考文献
	1.[廖雪峰的git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
	2.[菜鸟git教程](http://www.runoob.com/git/git-tutorial.html)
	