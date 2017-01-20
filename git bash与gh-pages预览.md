
#### Git Bash软件基础命令:

##### 零、建立本地与远程仓库的连接

`$ ssh-keygen -t rsa -C "youremail@example.com"`
本地找到.ssh目录，有id_rsa和id_rsa.pub两个文件，SSH Key的秘钥对，id_rsa是私钥，id_rsa.pub是公钥，可以放心地告诉任何人。登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。


#####  一、创建空目录
- `mkdir newFile`    新建一个文件夹

- `cd newFile`      进入文件夹

`pwd`    显示当前目录


------------



##### 二、本地创建版本库（repository）
- `git init`    newFile文件夹内有一个.git的目录，这个目录是Git来跟踪管理版本库的

~~Initialized empty Git repository in /Users/TGQ/newFile/.git/~~

`ls -ah`     .git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见



------------


##### 三、提交文件到版本库

- `git add .`   （添加到工作区）

- `git commit -m "提交的备注"`   （提交到暂存区）

`git status`    掌握仓库当前的状态（文件被修改过）

`git diff`      查看修改内容

------------



##### 四、版本回退

- `git log `     提交日志

- ` git reset --hard HEAD^（或者是commit_id）`  回退上一个版本

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


##### 六、撤销修改

1. `git checkout -- file`  可以丢弃工作区的修改

1. `git reset HEAD file`   ==》 1     可以丢弃暂存区的修改

1. 版本回 退：提交了不合适的修改到版本库时，想要撤销本次提交


##### 七、删除文件
1. 从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`

1. `git checkout`   用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”

##### 八、远程库的管理
