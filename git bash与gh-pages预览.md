
#### Git Bash软件基础命令:

#####  一、创建空目录
`mkdir newFile`    新建一个文件夹

`cd newFile`      进入文件夹

`pwd`    显示当前目录


------------



##### 二、本地创建版本库（repository）
`git init`    newFile文件夹内有一个.git的目录，这个目录是Git来跟踪管理版本库的

~~Initialized empty Git repository in /Users/TGQ/newFile/.git/~~

`ls -ah`     .git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见



------------


##### 三、提交文件到版本库

`git add .`

`git commit -m "提交的备注"`

`git status`    掌握仓库当前的状态（文件被修改过）

`git diff`      查看修改内容

------------



##### 四、版本回退

`git log `     提交日志

` git reset --hard HEAD^（或者是commit_id）`  回退上一个版本

`git reflog`  命令历史

`cat  readme.txt`   查看txt文件内容

在Git中，用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`


------------


##### 五、工作区与暂存区

工作区（**文件夹**）有一个隐藏目录**.git**，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为**stage**（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支**master**，以及指向master的一个指针叫HEAD。

![](picture/提交.jpg)


`git add`命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行`git commit`就可以一次性把暂存区的所有修改提交到分支。

一旦提交后，如果你又没有对工作区做任何修改，那么工作区就是“干净”的`git status`：

![](picture/stage空.jpg)
