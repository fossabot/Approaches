### dos命令，有时还是要了解一下的，下面列举了一下自己常用的命令
### 还有常用的版本控制命令gitbash命令行的使用

#### ***cmd中：***

1. 查看系统版本
    `ver`
	
2. 清空命令
	`cls`
	
3. 更改文件名
	`ren 旧名 新名`（shell中 `mv 旧名 新名`）
	
4. 査看文本内容（gitbash中 cat 文本）
	`type 文件名`
	
5. 査看某个命令的帮助
	`命令 /?`
	
6. 新建文本
	`echo >xx.txt`
	
   补充内容
	`echo mmm>>xx.txt`
7. 退出cmd
	`exit`(shell中则是`quit`)
	
8. 直接进入别的盘
	`e:`
	
9. 复制文件到e盘（`hw.class在c:/Users/TGQ/Desktop里`）(输命令也要在Desktop里)
	`copy hw.class e:`
	
10. 屏幕键盘
	`osk`
11. 服务项（window.update系统更新设置）
	`services.msc`
	
12. 注册表
	`regedit.exe`


--------------------------------------------

##### *自制‘栗子’： 完全cmd命令编译HELLO WORLD!*
###### win+R调出命令提示符 键入cmd

```javascript 
echo class hw {public static void main(String[] args ){ System.out.println("HELLO WORLD!"); }}>>hw.txt
ren hw.txt hw.java
javac hw.java
java hw
//HELLO WORLD!
```

----------------------------------------------------------



#### ***cmd登录ftp中：***

1. 查看当下目录
	`lcd`
2. 更改下载目录
	`lcd c:/Users/TGQ/Desktop`
3. 退出ftp
	`quit或bye`



-------------------------------------------------------

#### ***xshell中：***
1. 清除屏幕命令
	`clear`
	
2. 复制
	`cp`
	
3. 查看文件内容
	`cat 文件名`
	
4. 用户登录信息
	`last`
	
5. 时间
	`date`
	
6. 查看系统版本
	`unname`
	
7. 删除非空文件
	`rm -rf 文件名`
	
8. 重命名文件夹
	`mv 旧名 新名`
	
9. 进入vi编辑
	`vi 文件（例如 hw.java）`
   不保存退出
	`：q`
   强制性退出
	`：q!`
   保存并退出
	`：wq`
	
10. 查看当前文件
	`ls`(或者`dir`)
	
11. 退出一级目录
	`cd ..`(cmd中有无空格都行)

--------------------------------------------------------


##### *自制‘栗子’： 综合应用cmd的登录ftp与xshell的vi编译*

- dos-->cmd-->ftp
  - `open  address`
  - `user-name`
  - `password`

- 之后上传压缩文件到阿里云服务器 
 - `put ds.zip`(或 ds.rar)
 - `get xx`(同理下载命令)

- xshell登录到阿里云服务器,并解压ds.zip到ds/list文件夹中
 - `rar x ds.rar (或 unzip ds.zip)`

- 若没有编译，则 
  - `javac -encoding GBK *.java`
  
- 回到根目录，执行java程序
  - `cd ~` （~表示根目录）
  - `java ds/list/TestList`


-------------------------------------------------------------


#### ***gitBash：***
1. 进入	
	`cd`  
	
2. 创建（win中还可用md） 
	`mkdir`
	
3. 删除（win中用rd删除）
	`rm `
	
4. 文件名.txt(bash中不能使用)
	`del	`
	
5. 误删除，恢复
	`git checkout -- 文件名`
	
6. 査看当前文件
	`dir`（或者ls）
	
7. 往文本添加内容
	`echo 内容>>文件名.txt`
	
8. 获取到版本号
	`git reflog`
	
9. 査看文件内容
	`cat 文本`
	
10. 命令是用于显示当前的目录
	`pwd `
	
11.  把当前目录变成git可以管理的仓库，如下：
     `git init`
	 
*这时候你当前testgit目录下会多了一个.git的目录，这个目录是Git来跟踪管理版本的，没事千万不要手动乱改这个目录里面的文件，否则，会把git仓库给破坏了*

------------------------------------------------------

##### *自制'栗子’: gitbash小实例*

    版本库创建成功后：
    把文件添加到版本库
    第一步：用命令git add告诉Git，把文件添加到仓库：
    $ git add readme.txt
    第二步：用命令git commit告诉Git，把文件提交到仓库。
    $ git commit -m "new file info"
   
######   * 下图是详细步骤：*

    1. cd e:\git_code 命令到版本库文件夹下（我是在e盘下创建了git_code文件夹，前面说过了）
    2. touch reader.txt 命令创建一个新的txt文本：reader.txt 。
    3. git add reader.txt 命令，告诉Git，把文件添加到仓库
    4.. echo "I love you">>reader.txt 命令往reader.txt文本中添加内容I love you 字符串。
      （查看修改的内容:git diff ）
    5. 查看reader.txt文本内容 :cat reader.txt 。
    6. 把所有文件添加到版本库(注意：add后+空格+ . ):  git add .
    7. 最后使用 git status 命令查看仓库当前状态。

###### *关于版本的回退与恢复：*
使用版本回退操作:`git reset –hard HEAD^`
版本号回退，使用命令方法：`git reset –hard 版本号`
获取版本号：`git reflog`










