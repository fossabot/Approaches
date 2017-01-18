#### git bash软件基础命令:

#####  一、创建空目录
`mkdir newFile`    新建一个文件夹
`cd newFile`      进入文件夹
`pwd`    显示当前目录

##### 二、本地创建版本库（repository）
`git init`    newFile文件夹内有一个.git的目录，这个目录是Git来跟踪管理版本库的
Initialized empty Git repository in /Users/TGQ/newFile/.git/

`ls -ah`     .git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见

##### 三、提交文件到版本库
`git add .`
`git commit -m "提交的备注"




`
git push
